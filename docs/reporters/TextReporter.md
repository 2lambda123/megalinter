---
title: Text Reporter for MegaLinter
description: Generate error logs for each linter, including specific error messages to be checked in case of a failure
---
# Text Reporter

Generate error logs for each linter, including specific error messages to be checked in case of a failure

- General execution log `mega-linter.log` (same as [ConsoleReporter](ConsoleReporter.md) log)
-__Note__: Generate error logs for each linter, including specific error messages to be checked in case of a failure
- A separate log file for each processed linter

## Usage Instructions
-To access the error logs and specific error messages, please check the GitHub Comment Reporter in the related pull request.
+To access detailed error logs and specific error messages, please navigate to the GitHub Comment Reporter in the related pull request.
+Note: You can click on hyperlinks to access detailed logs.
+In case of failure, please check the GitHub Comment Reporter in the related pull request for specific error logs.

### Get Artifacts on GitHub Actions

- Access GitHub action run

![Screenshot](../assets/images/AccessActionRun.jpg)

- Click on Artifacts then click on [**MegaLinter reports**](#report-folder-structure)

![Screenshot](../assets/images/TextReporter_1.jpg)

### Get Artifacts on GitLab CI

- Access GitLab CI job page

![Screenshot](../assets/images/TextReporter_gitlab_1.jpg)

- In **Job Artifacts** section, click on [**Download**](#report-folder-structure)

### Other CI tools

- You can export `mega-linter.log` and folder `<WORKSPACE>/report` as external artifacts

- You can also use [File.io Reporter](https://megalinter.io/reporters/FileIoReporter/) or [E-mail Reporter](https://megalinter.io/reporters/EmailReporter/)

## Report folder structure

- Open the downloaded zip file and browse **linters_logs** folder for reports

![Screenshot](../assets/images/TextReporter_2.jpg)

![Screenshot](../assets/images/TextReporter_3.jpg)

![Screenshot](../assets/images/TextReporter_4.jpg)

## Configuration

| Variable                 | Description                                       | Default value  |
|--------------------------|---------------------------------------------------|----------------|
| TEXT_REPORTER            | Activates/deactivates reporter                    | `true`         |
| TEXT_REPORTER_SUB_FOLDER | Sub-folder of reports folder containing text logs | `linters_logs` |
