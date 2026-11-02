pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Starting Python CI'
            }
        }

        stage('Check Python') {
            steps {
                bat 'python --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'python -m pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'python -m pytest -v'
            }
        }
    }

    post {
        success {
            echo 'All tests passed!'
        }
        failure {
            echo 'Pipeline failed. Check Console Output.'
        }
    }
}
