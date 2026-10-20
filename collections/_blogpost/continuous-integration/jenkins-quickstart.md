---
layout: blog
permalink: /blogpost/continuous-integration/jenkins-quickstart/
title: "Minimal quick start guide for Jenkins for researchers"
category: Tutorial
subtitle: ""
author: "Andrew Naden"
author_image: ""
hero_image: "" 
date: 2026-10-19
social_links:
  - title: LinkedIn
    url: "https://www.linkedin.com/company/shareing/"
  - title: Bluesky
    url: "https://bsky.app/profile/shareing.bsky.social"
  - title: Email
    url: "mailto:shareing@durham.ac.uk"
id: 20261019115409
---
# Minimal quick start guide for Jenkins for researchers

<!--toc:start-->
- [Minimal quick start guide for Jenkins for researchers](#minimal-quick-start-guide-for-jenkins-for-researchers)
  - [Getting Jenkins up and running](#getting-jenkins-up-and-running)
  - [Creating a pipeline for Jenkins](#creating-a-pipeline-for-jenkins)
<!--toc:end-->

> [!ALERT]
> This document serves as a bare bones, quickstart for Jenkins CI on Durham compute hardware.
> It does not require administrator privileges, or sudo, and it can run indefinitely if allowed to do so. 
> It should not be taken as a robust example of using Jenkins to faciliate CI. The default result for following this guide is similar to a `cron` job, repeatedly checking a github repository, checking out the main branch, and building the program.
>Similarly, this workflow does not address multiple agents for building, or how to design tests or implement a testing matrix. The related documents can be found in [[self-hosted-runners|Continuous Integration - Self Hosted]] and [[test-matrix|Continuous Integration - The Test Matrix]] respectively.

## Getting Jenkins up and running
1. `mkdir -p ci ci/java/ ci/jenkins`

>[!note] in the java folder - > `cd ci/java`

1. Download [openjdk 27](https://jdk.java.net/27/) [e.g. java 27 for Linux/x64](https://download.java.net/java/GA/jdk27/55ce5470a6294008af0057ff4626d0e5/35/GPL/openjdk-27_linux-x64_bin.tar.gz) and the corresponding sha256 sum file.
  a. check sha256sum of downloaded archive; append the archive name after 2 spaces after the sum. (This matches the expected format of the sha256sum check subcommand).
  ```bash
  sed -i 's/$/  openjdk-27_linux-x64_bin.tar.gz/' openjdk-27_linux-x64_bin.tar.gz.sha256
  sha256sum -c openjdk-27_linux-x64_bin.tar.gz.sha256'
  ```
  b. unpack the archive
  ```
  tar -xvf openjdk-27_linux-x64_bin.tar.gz
  ```

>[!note] In the jenkins folder -> `cd ../jenkins`

1. Download and unpack Jenkins, repeating the sha256sum check
  1. [Downlaod the standalone jenkins.war file](https://www.jenkins.io/doc/book/installing/war-file/)
  2. copy the corresponding sha256 from [the website](https://www.jenkins.io/download/) into a file (jenkins.sha256)
      ```bash
      sed -i 's/$/  jenkins.war/' jenkins.sha256
      sha256sum -c jenkins.sha256'
      ```
2. Run Jenkins.war initial setup
  1. java/jdk-27/bin/java -jar ../jenkins/jenkins.war --enable-future-java
  2. take note of the admin password (also present in ~/.jenkins/secrets/initialAdminPassword)
  3. Open a browser and navigate to [http://localhost:8080](http://localhost:8080)
  4. Install suggested plugins
  5. Create an admin user
## Creating a pipeline for Jenkins
3. Create a New Item from the Jenkins main page
4. Select Pipeline and give it a name (e.g. "TEST")
5. Add a github url
6. Choose build conditions
    1. Build periodically (with a cron equivalent expression e.g. every 30 mins -> H/30 * * * * )
    2. Poll SCM to check for changes in the repository repeatedly.
    3. Add a URL to check for changes.
7. Switch the pipeline tab
8. Add a git checkout and any build requirements e.g.:
```java
    pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                checkout scmGit(
                branches: [[name: 'main']],
                userRemoteConfigs: [[url: 'https://github.com/richard-evans/vampire.git']])
                // Run the build on a Unix agent.
	              sh "make 'serial'"
                sh "file vampire-serial"

            }
        }
    }
}
```
>[!note]
>This quick configuration will run local to the Jenkins instance, other agents should be added for consistency. (Agents are the runners for each job, they are not related to agents in the Large Language Model sense.)
