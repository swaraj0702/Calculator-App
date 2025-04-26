pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from Git
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add any build steps if needed, e.g., setup or install
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Run tests using pytest (adjust to match your testing framework)
                sh 'pytest test_calculator.py'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // You can add deployment steps here if required
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            // Any cleanup steps can go here
        }
        success {
            echo 'Build and tests passed successfully!'
        }
        failure {
            echo 'Build or tests failed.'
        }
    }
}
