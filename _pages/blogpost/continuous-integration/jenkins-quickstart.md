---
title: steps for jenkins
date: 2026-10-19
id: 20261019115409
author: A Naden
---

# steps for jenkins


1. mkdir ci, ci/java/ and ci/jenkins
>[!note] in the java folder
1. Download [openjdk 27](https://jdk.java.net/27/) [e.g. java 27 for Linux/x64](https://download.java.net/java/GA/jdk27/55ce5470a6294008af0057ff4626d0e5/35/GPL/openjdk-27_linux-x64_bin.tar.gz) and the corresponding sha256 sum file.
  a. check sha256sum of downloaded archive; append the archive name after 2 spaces after the sum.
  ```
  sed -i 's/$/  openjdk-27_linux-x64_bin.tar.gz/' openjdk-27_linux-x64_bin.tar.gz.sha256
  sha256sum -c openjdk-27_linux-x64_bin.tar.gz.sha256'
  ```
  b. unpack the archive
  ```
  tar -xvf openjdk-27_linux-x64_bin.tar.gz
  ```

>[!note] In the jenkins folder
1. Download and unpack Jenkins, repeating the sha256sum check
  2. [Downlaod the standalone jenkins.war file](https://www.jenkins.io/doc/book/installing/war-file/)
3. Run Jenkins.war initial setup
  4. java/jdk-27/bin/java -jar ../jenkins/jenkins.war --enable-future-java
  5. take note of the admin password (also present in ~/.jenkins/secrets/initialAdminPassword)
6. Open a browser and navigate to [http://localhost:8080](http://localhost:8080)
7. Install suggested plugins
8. Create an admin user
9. Create a New Item from the Jenkins main page
10. Select Pipeline and give it a name (e.g. "TEST")
11. Add a github url
12. Choose build conditions
    1. Build periodically (with a cron equivalent expression e.g. every 30 mins -> H/2 * * * * )
    2. Poll SCM to check for changes in the repository
13. Switch the pipeline tab
14. Add a git checkout and any build requirements e.g.:
```
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
>[!note] This quick configuration will run local to the Jenkins instance, other agents should be added for consistency.