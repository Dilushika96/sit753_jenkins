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
            
                    mail to: "dilushikasavindi12@gmail.com",
                    subject: "Build status Email"
                    build: "Build was success"
        }
        failure {
                    mail to: "dilushikasavindi12@gmail.com",
                    subject: "Build statu Email"
                    build: "Build was failure"
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
                    mail to: "dilushikasavindi12@gmail.com",
                    subject: "Build statu Email"
                    build: "Build was success"
        }
        failure {
                    mail to: "dilushikasavindi12@gmail.com",
                    subject: "Build statu Email"
                    build: "Build was failure"
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
}
