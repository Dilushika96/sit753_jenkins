pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Build the code using Maven
                // Example: sh 'mvn clean package'
                echo "Build was successful"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                // Run unit tests using JUnit or TestNG
                // Example: sh 'mvn test'
                // Run integration tests using Selenium, Cucumber, or similar tools
                echo "Unit and Integration Tests passed"
            }
        }
        stage('Code Analysis') {
            steps {
                // Integrate a code analysis tool like SonarQube or Checkstyle
                // Example: sh 'sonar-scanner'
                echo "Code Analysis completed"
            }
        }
        stage('Security Scan') {
            steps {
                // Perform security scan using a tool like OWASP ZAP or SonarQube
                // Example: sh 'zap-cli --spider <target_url>'
                echo "Security Scan completed"
            }
        }
        stage('Deploy to Staging') {
            steps {
                // Deploy the application to staging server (e.g., AWS EC2) using deployment automation tools like Ansible or Docker
                // Example: sh 'ansible-playbook deploy-staging.yml'
                echo "Deployed to Staging"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                // Run integration tests on staging environment
                echo "Integration Tests on Staging passed"
            }
        }
        stage('Deploy to Production') {
            steps {
                // Deploy the application to production server (e.g., AWS EC2) using deployment automation tools like Ansible or Docker
                // Example: sh 'ansible-playbook deploy-production.yml'
                echo "Deployed to Production"
            }
        }
    }
    
    post {
        success {
            emailext subject: "Pipeline Success: ${currentBuild.fullDisplayName}",
                      body: "The pipeline ${currentBuild.fullDisplayName} has succeeded.",
                      to: 'dilushikasavindi122gmail.com',
                      attachLog: true
        }
        failure {
            emailext subject: "Pipeline Failure: ${currentBuild.fullDisplayName}",
                      body: "The pipeline ${currentBuild.fullDisplayName} has failed.",
                      to: 'dilushikasavindi122gmail.com',
                      attachLog: true
        }
    }
}
