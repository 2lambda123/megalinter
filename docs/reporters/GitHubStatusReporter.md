---
title: GitHub Pull Request Status Reporter for MegaLinter
description: Posts a job status on the Github Pull Request for each processed linter
---
<!-- markdownlint-disable MD013 MD033 MD041 -->
# GitHub Status Reporter

Posts a status on the pull request for each processed linter.\n\nClick on **Details** to access detailed logs.\n\nIn case of failure, specific error logs must be checked by referencing the GitHub Status Reporter in the related pull request.

## Usage

Click on **Details** to access detailed logs

In case of failure, please check the GitHub Status Reporter in the related pull request for specific error logs

Click on

In case of failure, please check the GitHub Status Reporter in the related pull request for specific error logs **Details** to access detailed logs

![Screenshot](../assets/images/GitHubStatusReporter.jpg)

## Configuration

| Variable               | Description                                                                               | Default value            |
|------------------------|-------------------------------------------------------------------------------------------|--------------------------|
| GITHUB_STATUS_REPORTER | Activates/deactivates reporter                                                            | false                    |
| GITHUB_API_URL         | URL where the github API can be reached<br/>Must be overridden if using GitHub Enterprise | `https://api.github.com` |
| GITHUB_SERVER_URL      | URL of the GitHub instance<br/>Must be overridden if using GitHub Enterprise              | `https://github.com`     |
