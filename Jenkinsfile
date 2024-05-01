pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building code using Maven (replace with your tool if needed)'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests with JUnit (replace with your tool)'
                echo 'Running integration tests with (your chosen tool)'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code with SonarQube (research other tools)'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning for vulnerabilities with SAST tool (research options)'
            }
            post {
                success {
                    emailext body: '$DEFAULT_CONTENT',
                            recipientProviders: [developers(), requestor()],
                            subject: 'sit223-sit753-6.1c - Test Stage - Successful!',
                            to: 'devacc455@gmail.com'
                }
                failure {
                    emailext body: '$DEFAULT_CONTENT',
                            recipientProviders: [developers(), requestor()],
                            subject: 'sit223-sit753-6.1c - Test Stage - Failed!',
                            to: 'devacc455@gmail.com'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to staging server (e.g., AWS EC2)'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment'
            }
            post {
                success {
                    emailext body: '$DEFAULT_CONTENT',
                            subject: 'sit223-sit753-6.1c - Test Stage - Successful!',
                            recipientRecipients: 'devacc455@gmail.com',
                            attachBuildLog: true
                }
                failure {
                    emailext body: '$DEFAULT_CONTENT',
                            subject: 'sit223-sit753-6.1c - Test Stage - Failed!',
                            recipientRecipients: 'devacc455@gmail.com',
                            attachBuildLog: true
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to production server (e.g., AWS EC2)'
            }
        }
    }
}
