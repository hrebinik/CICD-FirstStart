# Introduction

This is a [template](https://gitlab.chisw.us/artem.hrebinik/cicdprocess.git) for getting started with iOS development using GitLab and [fastlane](https://fastlane.tools/) and [firebase app distribution](https://firebase.google.com/docs/app-distribution/ios/distribute-console).
This report dedicated to CI/CD concepts and how we can automate and simplify the deploy process!

# Reference links

- [GitLab CI Documentation](https://docs.gitlab.com/ee/ci/)
- [Blog post: Android publishing with iOS and fastlane](https://about.gitlab.com/2019/03/06/ios-publishing-with-gitlab-and-fastlane/)

# Getting started

You'll need a working MacOS development environment with XCode 10 to use this
template. You can find instructions to get up and running on the Apple [XCode website](https://developer.apple.com/xcode/).

If you want to use GitLab CI with your own MacOS runners (a requirement since we
do not currently yet offer shared MacOS runners - follow [infrastructure#5294](https://gitlab.com/gitlab-com/gl-infra/infrastructure/issues/5294) for
updates on that front) please read through the blog post above which will walk 
you through everything you need to get up and running.

## What's contained in this project

this project contains

-swift lint scripts

-fastlane scripts for process automation and distribution in firebase builds

-gitlab file containing steps and jobs to run with the local gitlab-runner.

# Useful Links
[PDF Report](http://surl.li/cmayg)

[Video Report](http://surl.li/cmaxe)

Enjoy! :smile: 

Developed By
------------

* Hrebinik Artem, CHI Software
* Kosyi Vlad, CHI Software

License
--------
Copyright 2020 CHI Software.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
