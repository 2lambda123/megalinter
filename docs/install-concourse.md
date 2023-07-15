---
title: Install MegaLinter on Concourse
description: Manual instructions to setup MegaLinter as a Concourse job
---
<!-- markdownlint-disable MD013 -->
<!-- @generated by .automation/build.py, please don't update manually -->
<!-- install-concourse-section-start -->

# Concourse

## Pipeline step

Use the following `job.step` in your pipeline template

Note: make sure you have `job.plan.get` step which gets `repo` containing your repository as shown in example

```yaml
---

  - name: linting
    plan:
      - get: repo
      - task: linting
        config:
          platform: linux
          image_resource:
            type: docker-image
            source:
              repository: oxsecurity/megalinter
              tag: v7
          inputs:
            - name: repo
          run:
            path: bash
            args:
            - -cxe
            - |
              cd repo
              export DEFAULT_WORKSPACE=$(pwd)
              bash -ex /entrypoint.sh
              ## doing this because concourse doesn't work as other CI systems
          # params:
            # PARALLEL: true
            # DISABLE: SPELL
            # APPLY_FIXES: all
            # DISABLE_ERRORS: true
            # VALIDATE_ALL_CODEBASE: true
```

OR

## Use it as reusable task

Create reusable concourse task which can be used with multiple pipelines

1. Create task file `task-linting.yaml`

```yaml
---
platform: linux
image_resource:
  type: docker-image
  source:
    repository: oxsecurity/megalinter
    tag: v7

inputs:
- name: repo

## uncomment this if you want reports as task output
# output:
# - name: reports
#   path: repo/megalinter-reports

run:
  path: bash
  args:
  - -cxe
  - |
    cd repo
    export DEFAULT_WORKSPACE=$(pwd)
    bash -ex /entrypoint.sh
```

2. Use that `task-linting.yaml` task in pipeline

Note:

  1. make sure `task-linting.yaml` is available in that `repo` input at root

  2. task `output` is **not** shown here

```yaml
resources:

  - name: linting
    plan:
      - get: repo
      - task: linting
        file: repo/task-linting.yaml
        # params:
        #   PARALLEL: true
        #   DISABLE: SPELL
        #   APPLY_FIXES: all
        #   DISABLE_ERRORS: true
        #   VALIDATE_ALL_CODEBASE: true
```


<!-- install-concourse-section-end -->