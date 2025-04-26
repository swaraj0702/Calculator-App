pipeline {
    agent any

    environment {
        VENV_DIR = 'venv'  // virtual environment directory
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Setup Python Virtual Environment') {
            steps {
                bat 'python -m venv %VENV_DIR%'
            }
        }

        stage('Activate and Install Dependencies') {
            steps {
                bat '''
                call %VENV_DIR%\\Scripts\\activate
                python -m pip install --upgrade pip
                pip install pytest
                '''
            }
        }

        stage('Run Tests') {
            steps {
                bat '''
                call %VENV_DIR%\\Scripts\\activate
                pytest test_calculator.py
                '''
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            // Optional: clean virtual environment after build
            deleteDir()
        }
        success {
            echo 'Build and Tests passed!'
        }
        failure {
            echo 'Build or Tests failed.'
        }
    }
}
