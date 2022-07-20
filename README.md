# Introduction

This is a [template](https://gitlab.chisw.us/artem.hrebinik/cicdprocess.git) for getting started with iOS development using GitLab and [fastlane](https://fastlane.tools/) and [firebase app distribution](https://firebase.google.com/docs/app-distribution/ios/distribute-console).
This report dedicated to CI/CD concepts and how we can automate and simplify the deploy process!

<img width="848" alt="Снимок экрана 2022-07-20 в 19 33 57" src="https://user-images.githubusercontent.com/77230603/180035700-7e7864fd-38b3-4f9c-93bc-0bd472e18345.png">

# The content of the presentation:
What is CI/CD?  

What is Continuous integration?

What is Continuous delivery?

What is Continuous deployment?

A deeper look into the CI/CD workflow

Comparison of deployment cycles

When to use ci/cd processes?

The top benefits of CI/CD for iOS

Best practices to remember for iOS CI/CD

Some Tips

Main advantages/disadvantages of CI/CD

Platform selection

Introducing the Fastlane automation tool

Introducing the basic features of Fastlane

GitLabCI teory/concepts

Pipeline Rules

Gitlab-runner set up

Step-by-step instructions for deploying ios app with gitlab-runner and Fastlane and uploading the app to FirebaseAppDistribution

# Reference links

- [GitLab CI Documentation](https://docs.gitlab.com/ee/ci/)
- [Blog post: Android publishing with iOS and fastlane](https://about.gitlab.com/2019/03/06/ios-publishing-with-gitlab-and-fastlane/)

# Getting started

You'll need a working MacOS development environment with XCode 10 to use this
template. You can find instructions to get up and running on the Apple [XCode website](https://developer.apple.com/xcode/).
You can find instructions to get up gitlab-runner on the report and offitial documentation. 

## What's contained in this project

-swift lint scripts

-fastlane scripts for process automation and distribution in firebase builds

-gitlab file containing steps and jobs to run with the local gitlab-runner.

# Useful Links
[PDF Report](http://surl.li/cmayg)

[Video Report](http://surl.li/cmaxe)

Enjoy! :smile: 

### Step-by-step instructions for getting up simple pipline

**Install gitlab-runner on mac:**
```
brew install gitlab-runner
```

**Making mac a CI runner:**
```
gitlab-runner register
```

**Launching the runner:**
```
gitlab-runner install
```
```
gitlab-runner start
```

**Status::**
```
gitlab-runner status
```
<img width="529" alt="Снимок экрана 2022-07-20 в 19 28 47" src="https://user-images.githubusercontent.com/77230603/180034640-4bef5d80-9c1a-4d79-b64a-c5384a356828.png">


### Configure gitlab-runner.yml:
**Rules:**
```
The file name should always be .gitlab-ci.yml with a dot at the beginning.

If you accidentally named the file incorrectly, then this file will not be recognized, and the runner will not execute the script.

This file must be created in the root folder of the project.

Tags are also defined in the .yml file. These tags correspond to the tags that were defined during the setup of the runners.

After calling the yml file, the runner with the same tag as specified in the yml file will take the job and execute it through the pipeline.

A pipeline is a set of tasks/stages defined in a yml file for execution.

Each task/stage defined in the yml file is a job.

A pipeline only succeeds if all the jobs associated with it succeed.

If at least one job fails, the pipeline will not throw an error message in the Gitlab console.
```
<img width="481" alt="Снимок экрана 2022-07-20 в 19 29 10" src="https://user-images.githubusercontent.com/77230603/180034729-60ff0aed-a5c0-43fb-9b22-0fd985337aa6.png">

### Check pipline status:
<img width="876" alt="Снимок экрана 2022-07-20 в 19 32 15" src="https://user-images.githubusercontent.com/77230603/180035328-a2370431-205a-4d4e-877e-6d90f620c9b8.png">

Developed By
------------

* Hrebinik Artem, CHI Software
* Kosyi Vlad, CHI Software

## License

Copyright 2022 CHI Software.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
