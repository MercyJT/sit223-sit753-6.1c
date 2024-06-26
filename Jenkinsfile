pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building code using npm...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests with Jest'
                echo 'Running integration tests with Cypress'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code with ESLint'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning for vulnerabilities with Node Security Project (NSP)'
            }
            post {
                success {
                    mail to: 'terermercyline@gmail.com',
                            subject: 'sit223-sit753-6.1c - Security Scan Stage - Successful!',
                            body: '$DEFAULT_CONTENT'
                }
                failure {
                    mail to: 'terermercyline@gmail.com',
                            subject: 'sit223-sit753-6.1c - Security Scan Stage - Failed!',
                            body: '$DEFAULT_CONTENT'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to staging using PM2'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment with JEST'
            }
            post {
                success {
                    mail to: 'terermercyline@gmail.com',
                            subject: 'sit223-sit753-6.1c - Test Stage - Successful!',
                            body: '$DEFAULT_CONTENT'
                }
                failure {
                    mail to: 'terermercyline@gmail.com',
                            subject: 'sit223-sit753-6.1c - Test Stage - Failed!',
                            body: '$DEFAULT_CONTENT'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to PM2 production server'
            }
        }
    }
}
