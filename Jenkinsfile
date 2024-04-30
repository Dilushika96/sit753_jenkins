pipeline {
    agent any
    

    
    stages {
        stage('Build') {
            steps {
                echo "Build "
               
                
            }
        }
        stage('Test') {
            steps {
                echo "Running unit tests"
                
            }
        }
        stage('Code Quality Check') {
            steps {
                echo "Checking the quality of the code"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying the application "
            }
        }
        stage('Approval') {
            steps {
                echo "manual approval..."
                
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to the production environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline successfully completed!'
            
        }
        failure {
            echo 'Pipeline failed!'
            
        }
    }
}
