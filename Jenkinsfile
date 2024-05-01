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
    
    post {
        success {
            emailext subject: "Pipeline Success: ${currentBuild.fullDisplayName}",
                      body: "The pipeline ${currentBuild.fullDisplayName} has succeeded.",
                      to: 'dilushikasavindi12gmail.com',
                      attachLog: true
        }
        failure {
            emailext subject: "Pipeline Failure: ${currentBuild.fullDisplayName}",
                      body: "The pipeline ${currentBuild.fullDisplayName} has failed.",
                      to: 'dilushikasavindi12gmail.com',
                      attachLog: true
        }
    }
}
