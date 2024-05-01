pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package' 
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                sh 'mvn test' 
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
        stage('Code Analysis') {
            steps {
                 sh 'sonar-scanner' 
            }
        }
        stage('Security Scan') {
            steps {
              post {
        success {
            emailext subject: "Pipeline Success: ${currentBuild.fullDisplayName}",
                      body: "The pipeline ${currentBuild.fullDisplayName} has succeeded.",
                      to: 'your_email@example.com',
                      attachLog: true
        }
        failure {
            emailext subject: "Pipeline Failure: ${currentBuild.fullDisplayName}",
                      body: "The pipeline ${currentBuild.fullDisplayName} has failed.",
                      to: 'your_email@example.com',
                      attachLog: true  
            }
        }
        stage('Deploy to Staging') {
            steps {
                sh 'ansible-playbook deploy-staging.yml'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                // Run integration tests on staging environment
            }
        }
        stage('Deploy to Production') {
            steps {
                 sh 'ansible-playbook deploy-production.yml'
            }
        } 
    }
}
