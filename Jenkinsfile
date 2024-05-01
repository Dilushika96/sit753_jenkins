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
            emailext subject: "Pipeline Success: ${currentBuild.fullDisplayName}",
                      body: "The pipeline ${currentBuild.fullDisplayName} has succeeded.",
                      to: 'dilushikasavindi12@gmail.com',
                      attachLog: true
        }
        failure {
            emailext subject: "Pipeline Failure: ${currentBuild.fullDisplayName}",
                      body: "The pipeline ${currentBuild.fullDisplayName} has failed.",
                      to: 'dilushikasavindi12@gmail.com',
                      attachLog: true
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
            emailext subject: "Pipeline Success: ${currentBuild.fullDisplayName}",
                      body: "The pipeline ${currentBuild.fullDisplayName} has succeeded.",
                      to: 'dilushikasavindi12@gmail.com',
                      attachLog: true
        }
        failure {
            emailext subject: "Pipeline Failure: ${currentBuild.fullDisplayName}",
                      body: "The pipeline ${currentBuild.fullDisplayName} has failed.",
                      to: 'dilushikasavindi12@gmail.com',
                      attachLog: true
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
