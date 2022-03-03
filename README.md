# Nuke.Build and Github Actions

### Description

* Nuke.Build is a build tool that enables the build of .Net applications. Because it's just a console application that lives within the repository, it comes with intellisense and version control.
* Github Actions is a workflow executor. Workflows are triggered by events which execute workflows which are made up of actions.

### Nuke.Build

* Nuke.Build has an attribute call GithubActions which supports generating the Github Actions workflow yaml file for you based on the parameters you provide and the requirements of Targets.

### Dependencies

* Nuke.Common

### Workflow Statuses

[![CI](https://github.com/Jarryd460/NukeBuildWithGithubActions/actions/workflows/ci.yml/badge.svg)](https://github.com/Jarryd460/NukeBuildWithGithubActions/actions/workflows/ci.yml)
[![NukeBuildWithGithubActions](https://github.com/Jarryd460/NukeBuildWithGithubActions/actions/workflows/dotnet.yml/badge.svg)](https://github.com/Jarryd460/NukeBuildWithGithubActions/actions/workflows/dotnet.yml)
