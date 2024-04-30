pipeline {
    agent any
    
    environment {
        DIRECTORY_PATH = "code directory" 
        TESTING_ENVIRONMENT = "Testing Environment"
        PRODUCTION_ENVIRONMENT = "Dilushika" 
    }
    
    stages {
        stage('Build') {
            steps {
                echo "Fetching the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compiling the code and generating any necessary artifacts"
                
            }
        }
        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"
            }
        }
        stage('Code Quality Check') {
            steps {
                echo "Checking the quality of the code"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval') {
            steps {
                echo "manual approval..."
                sleep(time: 10, unit: 'SECONDS') // Simulate manual approval with a 10-second pause
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