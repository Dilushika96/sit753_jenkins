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
                echo "JUnit Tool Used"
            }
            post {
                success {
               
        
                    mail to: "dilushikasavindi12@gmail.com",
                    subject: "Test status success",
                    body: "Test was success"
        }
        failure {
             mail to: "dilushikasavindi12@gmail.com",
                    subject: "Test status success",
                    body: "Test was failure"
                    
        }
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
                echo "JMeter Tool Used"
            }
            post {
                success {
                    emailext(
                        attachLog: true,
                        to: 'dilushikasavindi12@gmail.com',
                        subject: "Security Scan - Success",
                        body: "Security scan completed successfully.",
                         mimeType:'text/html'
                    )
                }
                failure {
                    emailext(
                        attachLog: true,
                        to: 'dilushikasavindi12@gmail.com',
                        subject: "Security Scan - Failure",
                        body: "Security scan failed. Please check the log for details.",
                         mimeType:'text/html'
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
                echo "JMeter Tool Used"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deployed to Production"
            }
        }
    }
}
