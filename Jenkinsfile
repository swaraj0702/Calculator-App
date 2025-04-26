pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clone the GitHub repository
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add build commands if needed, for example:
                // sh 'python setup.py install'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Run tests using pytest
                sh 'pytest test_calculator.py'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add deployment steps, if needed (for example, deploy to a server)
            }
        }
    }
    post {
        always {
            echo 'Cleaning up...'
            // Add any clean-up steps if needed
        }
        success {
            echo 'Build and test passed successfully!'
        }
        failure {
            echo 'Build or tests failed.'
        }
    }
}
