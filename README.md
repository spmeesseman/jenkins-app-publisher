# Jenkins App Publisher Utility

[![authors](https://img.shields.io/badge/authors-scott%20meesseman-6F02B5.svg?logo=visual%20studio%20code)](https://www.littlesm.com)
[![app-category](https://img.shields.io/badge/category-jenkins%20plugins-blue.svg)](https://github.com/spmeesseman/jenkins-app-publisher)
[![app-lang](https://img.shields.io/badge/language-java%20maven-blue.svg)](https://github.com/spmeesseman/jenkins-app-publisher)
[![app-publisher](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-jenkins--mantisbt--plugin-e10000.svg)](https://github.com/spmeesseman/jenkins-app-publisher)
[![PayPalDonate](https://img.shields.io/badge/paypal-donate-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=YWZXT3KE2L4BA&item_name=taskexplorer&currency_code=USD)

[![GitHub issues open](https://img.shields.io/github/issues-raw/spmeesseman/jenkins%2dmantisbt%2dplugin.svg?logo=github)](https://github.com/spmeesseman/jenkins-app-publisher/issues)
[![GitHub issues closed](https://img.shields.io/github/issues-closed-raw/spmeesseman/jenkins%2dmantisbt%2dplugin.svg?logo=github)](https://github.com/spmeesseman/jenkins-app-publisher/issues)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/spmeesseman/jenkins%2dmantisbt%2dplugin.svg?logo=github)](https://github.com/spmeesseman/jenkins-app-publisher/pulls)
[![GitHub last commit](https://img.shields.io/github/last-commit/spmeesseman/jenkins%2dmantisbt%2dplugin.svg?logo=github)](https://github.com/spmeesseman/jenkins-app-publisher)

- [Jenkins App Publisher Utility](#jenkins-app-publisher-utility)
  - [Introduction](#introduction)
  - [Getting Started](#getting-started)
  - [Global Configuration](#global-configuration)
  - [Project Configuration](#project-configuration)
  - [Build Steps](#build-steps)
    - [Build Steps - appPublisherGetVersions](#build-steps---apppublishergetversions)
    - [Build Steps - appPublisherSetVersion](#build-steps---apppublishersetversion)
  - [Issues](#issues)
  - [Contributing](#contributing)
  - [Development Notes](#development-notes)
  - [License Information](#license-information)

## Introduction

Jenkins App-Publisher Integration (Artifact ID **app-publisher**).

TODO

## Getting Started

TODO

## Global Configuration

TODO

## Project Configuration

TODO

## Build Steps

The following build steps are available for both Freestyle and Pipeline builds using declarative or classic scripting:

- appPublisherGetVersions
- appPublisherSetVersion

Exmaple usage in a Jenkinsfile:

    steps { 
      script {
        env.CURRENTVERSION = bat(returnStdout: true,
                script: """
                    @echo off
                    app-publisher --task-version-current
                """)
        env.NEXTVERSION = bat(returnStdout: true,
                script: """
                    @echo off
                    app-publisher --task-version-next
                """)
      }
    }

### Build Steps - appPublisherGetVersions

TODO

### Build Steps - appPublisherSetVersion

TODO

## Issues

Report issues and enhancements in the project's [Github issue tracker](https://github.com/spmeesseman/jenkins-app-publisher/issues).

## Contributing

Refer to the [Jenkins Contribution Guidelines](https://github.com/jenkinsci/.github/blob/master/CONTRIBUTING.md)

## Development Notes

To validate Jenkinsfile syntax, use curl:

    curl -X POST -L -H "Authorization: basic ...base64encoded_user:token" -F "jenkinsfile=<Jenkinsfile" https://jenkins.development.pjats.com/pipeline-model-converter/validate

To get a csrf crumb:

    curl -d "" -X POST -L -H "Authorization: basic ...base64encoded_user:token" -H "Content-Type:text/plain;charset=UTF-8" https://jenkins.development.pjats.com/crumbIssuer/api/json

## License Information

Licensed under MIT, see the [LICENSE](LICENSE.md)
