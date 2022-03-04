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

### Github Actions

* To test Github Actions locally, you will need Docker installed locally.
* Once installed, install chocolate and run "choco act-cli" to install act.
* Run act -W ./github/workflows/{workflow}.yml. It only supports jobs that run on linux. When running for the first time, act will ask you about the image you would like to use (micro, medium and large). 
* Depending on your choice, it will determine how  many Github Actions will be supported. I suggest that the largest image be chosen. Once selected, a .actrc will be created under your username (c:\Users\jondoe\.actrc). This is where configuration for act is stored.
    * With trigger: act push -W ./github/workflows/{workflow}.yml
    * With Job: act pull_request -j {job name} -W ./github/workflows/{workflow}.yml
* To enable verbose logging in Github Actions, add the following to settings -> secrets -> actions:
    * ACTIONS_RUNNER_DEBUG=true
    * ACTIONS_STEP_DEBUG=true
* TMate is a tool for debugging Github Actions on Github.
    * Add the action to your workflow to enable debugging. To make debugging with tmate configurable, you should add a input paramter (example: debug_enabled) and provide it's value
* Workflows can be disabled by going to the Actions tab and selecting the workflow. There should be a "..." button which has the option to disable workflow.


### Workflow Statuses

[![CI](https://github.com/Jarryd460/NukeBuildWithGithubActions/actions/workflows/ci.yml/badge.svg)](https://github.com/Jarryd460/NukeBuildWithGithubActions/actions/workflows/ci.yml)
[![NukeBuildWithGithubActions](https://github.com/Jarryd460/NukeBuildWithGithubActions/actions/workflows/dotnet.yml/badge.svg)](https://github.com/Jarryd460/NukeBuildWithGithubActions/actions/workflows/dotnet.yml)

* The above workflow badges were copied from the Github Actions pages for each workflow.

### References

* Nuke setup with Github Actions: https://dev.to/damikun/the-cross-platform-build-automation-with-nuke-1kmc
* Nuke with Github: https://www.ariank.dev/create-a-github-release-with-nuke-build-automation-tool/amp/
* GitVersion: https://github.com/GitTools/GitVersion
* Github Action cache: https://github.com/actions/cache
* Act: https://github.com/nektos/act
* Tmate: https://github.com/marketplace/actions/debugging-with-tmate