pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build was successful"
                echo "Maven Tool Used"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Unit and Integration Tests passed"
                echo "Junit Tool Used"
            }
            post {
                success {
                    emailext(
                        attachLog: true,
                        to: 'dilushikasavindi12@gmail.com',
                        subject: "Unit and Integration Tests Success",
                        body: "Unit and integration tests were successful",
                        mimeType: 'text/html'
                    )
                }
                failure {
                    emailext(
                        attachLog: true,
                        to: 'dilushikasavindi12@gmail.com',
                        subject: "Unit and Integration Tests Failure",
                        body: "Unit and integration tests failed",
                        mimeType: 'text/html'
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Code Analysis completed"
                echo "SonarQube Tool Used"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Security Scan completed"
                echo "OWASP Tool Used"
            }
            post {
                success {
                    emailext(
                        attachLog: true,
                        to: 'dilushikasavindi12@gmail.com',
                        subject: "Security Scan Success",
                        body: "Security scan was successful",
                        mimeType: 'text/html'
                    )
                }
                failure {
                    emailext(
                        attachLog: true,
                        to: 'dilushikasavindi12@gmail.com',
                        subject: "Security Scan Failure",
                        body: "Security scan failed",
                        mimeType: 'text/html'
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deployed to Staging"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Integration Tests on Staging passed"
                echo "Jmeter Tool Used"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deployed to Production"
            }
        }
    }
}
