---
title: GitHub Pull Request Comments Reporter for MegaLinter
description: Posts MegaLinter SAST results summary in the comments of the related GitHub Pull Request (if existing)
---
<!-- markdownlint-disable MD013 MD033 MD041 -->
# GitHub Comment Reporter

Posts MegaLinter results summary in the comments of the related pull request (if existing)

## Usage Instructions

To access detailed error logs and specific error messages, please navigate to the GitHub Comment Reporter in the related pull request.

Note: You can click on hyperlinks to access detailed logs.

Note: In case of failure, please check the GitHub Comment Reporter in the related pull request for specific error logs.

![Screenshot](../assets/images/GitHubCommentReporter.jpg)

## Configuration

| Variable                | Description                                                                               | Default value            | Notes                                        |
|-------------------------|-------------------------------------------------------------------------------------------|--------------------------|----------------------------------------------|
| GITHUB_COMMENT_REPORTER | Activates/deactivates reporter                                                            | true                     |                                              |
| GITHUB_API_URL          | URL where the github API can be reached<br/>Must be overridden if using GitHub Enterprise | `https://api.github.com` | For GHE, use `https://my.company.com/api/v3` |
| GITHUB_SERVER_URL       | URL of the GitHub instance<br/>Must be overridden if using GitHub Enterprise              | `https://github.com`     |                                              |
| CI_ACTION_RUN_URL       | URL of the CI job visualization page url (if using Github but not GitHub Actions)         | <!--  -->                |                                              |
| REPORTERS_MARKDOWN_TYPE | Set to `simple` to avoid external images in generated markdown                            | `advanced`               |                                              |