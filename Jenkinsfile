pipeline {
    agent any
    
    environment {
        SOURCE_CODE_PATH = '/path/to/source/code'
        TESTING_ENVIRONMENT = 'staging'
        PRODUCTION_ENVIRONMENT = 'production'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    echo "fetch the source code from the directory path specified by the environment variable: ${env.SOURCE_CODE_PATH}"
                    echo "compile the code and generate any necessary artifacts"
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    echo "unit tests"
                    echo "integration tests"
                }
            }
        }
        
        stage('Code Quality Check') {
            steps {
                script {
                    echo "check the quality of the code"
                }
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    echo "deploy the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
                }
            }
        }
        
        stage('Approval') {
            steps {
                script {
                    echo "Waiting for manual approval..."
                    sleep(time: 10, unit: 'SECONDS')
                }
            }
        }
        
        stage('Deploy to Production') {
            steps {
                script {
                    echo "deploy the code to the production environment using the environment variable specifying the environment name: ${env.PRODUCTION_ENVIRONMENT}"
                }
            }
        }
    }
}
