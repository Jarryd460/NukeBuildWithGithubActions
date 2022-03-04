# Nuke.Build and Github Actions

### Description

* Nuke.Build is a build tool that enables the build of .Net applications. Because it's just a console application that lives within the repository, it comes with intellisense and version control.
* Github Actions is a workflow executor. Workflows are triggered by events which execute workflows which are made up of actions.

### Dependencies

* Nuke.Common

### Nuke.Build

* Nuke.Build has an attribute call GithubActions which supports generating the Github Actions workflow yaml file for you based on the parameters you provide and the requirements of Targets.
* IsLocalBuild is what determines whether to build in Debug or Release mode. IsLocalBuild is set internally by the IsServerBuild variable which is set by the Host class which automatically picks up the environment it's executing in.
* Nuke has an extension for running Targets in Visual Studio but currently only exists for 2019. A version for Visual 2022 is yet to be released. 

### GitVersion

* To install GitVersion command line tool run "dotnet tool install --global GitVersion.Tool --version 5.* --ignore-failed-sources".
* Once installed run dotnet-gitversion in a Git directory to ensure the install was successful. It must be run in a git directory to generate the version for the repository.
* Run "dotnet-gitversion init" and go through the wizard to setup GitVersion which will generate a GitVersion.yml file once you have finished wizard and saved changes.

### Workflow Statuses

[![CI](https://github.com/Jarryd460/NukeBuildWithGithubActions/actions/workflows/ci.yml/badge.svg)](https://github.com/Jarryd460/NukeBuildWithGithubActions/actions/workflows/ci.yml)
[![NukeBuildWithGithubActions](https://github.com/Jarryd460/NukeBuildWithGithubActions/actions/workflows/dotnet.yml/badge.svg)](https://github.com/Jarryd460/NukeBuildWithGithubActions/actions/workflows/dotnet.yml)

* The above workflow badges were copied from the Github Actions pages for each workflow.

### References

* Nuke setup with Github Actions: https://dev.to/damikun/the-cross-platform-build-automation-with-nuke-1kmc
* Nuke with Github: https://www.ariank.dev/create-a-github-release-with-nuke-build-automation-tool/amp/
* GitVersion: https://github.com/GitTools/GitVersion