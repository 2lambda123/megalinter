---
title: MegaLinter configuration file
description: Use config file with auto-completion to customize MegaLinter behaviour
---
<!-- markdownlint-disable MD013 -->
<!-- @generated by .automation/build.py, please don't update manually -->
<!-- config-file-section-start -->

# .mega-linter.yml file

MegaLinter configuration variables are defined in a **.mega-linter.yml** file at the root of the repository or with **environment variables**.
You can see an example config file in this repo: [**.mega-linter.yml**](https://github.com/oxsecurity/megalinter/blob/main/.mega-linter.yml)

Configuration is assisted with autocompletion and validation in most commonly used IDEs, thanks to [JSON schema](https://megalinter.io/json-schemas/configuration.html) stored on [schemastore.org](https://www.schemastore.org/)

- VSCode: You need a VSCode extension like [Red Hat YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)
- IDEA family: Auto-completion natively supported

You can also define variables as environment variables.
- In case a variable exists in both ENV and `.mega-linter.yml` file, priority is given to ENV variable.

![Assisted configuration](https://github.com/oxsecurity/megalinter/raw/main/docs/assets/images/assisted-configuration.gif)


<!-- config-file-section-end -->
