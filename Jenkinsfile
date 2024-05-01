pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                
                echo "Build was successful"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                
                echo "Unit and Integration Tests passed"
            }
           post {
        success {
            
                    to: "dilushikasavindi12@gmail.com",
                    subject: "Build status success",
                    body: "Build was success"
        }
        failure {
                       mail to: "dilushikasavindi12@gmail.com",
                        subject: "Build status success",
                      body: "Build was failure"
        }
        }
        }
        stage('Code Analysis') {
            steps {
               
                echo "Code Analysis completed"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Security Scan completed"
            }
            post {
        success {
                        mail to: "dilushikasavindi12@gmail.com",
                        subject: "Build status success",
                        body: "Build was success"
        }
        failure {
                        mail to: "dilushikasavindi12@gmail.com",
                        subject: "Build status success",
                        body: "Build was failure"
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
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deployed to Production"
            }
        }
 
    }
}
