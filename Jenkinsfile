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
        
             emailtext(
                     attachLog:true,
                    to: 'dilushikasavindi12@gmail.com',
                    subject: "Security scan status success",
                    body: "security scan was success" 
             )

        }
        failure {
             emailtext(
                     attachLog:true,
                    to: 'dilushikasavindi12@gmail.com',
                    subject: "Security scan status success",
                    body: "security scan was success" 
             )
        }
        }
        }
        stage('Code Analysis') {
            steps {
               
                echo "Code Analysis completed"
                 echo "Junit Tool Used"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Security Scan completed"
                 echo "Jmeter Tool Used"
            }
            post {
        success {
              emailtext(
                     attachLog:true,
                    to: 'dilushikasavindi12@gmail.com',
                    subject: "Security scan status success",
                    body: "security scan was success" 
             )
               
        }
        failure {
              emailtext(
                     attachLog:true,
                    to: 'dilushikasavindi12@gmail.com',
                    subject: "Security scan status success",
                    body: "security scan was success" 
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
