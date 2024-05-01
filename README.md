## TASK: SIT223_SIT753-6.1C

A Jenkins pipeline that integrates with GitHub, with email notifications to inform developers about build status and deployment events.

### SETUP (with Docker setup)
- Setup Jenkins GUI via Docker:
    - `docker pull jenkins/jenkins:lts-jdk17`
    - `docker run -p 8080:8080 -p 50000:50000 --restart=on-failure jenkins/jenkins:lts-jdk17`

- Setup pipeline from GUI:
    - SCM as `git`
    - Add title
    - description
    - git URL as `https://github.com/MercyJT/sit223-sit753-6.1c`
    - Branches to build as `*/main`
    - Script Path as `Jenkinsfile`
    - Hit Save