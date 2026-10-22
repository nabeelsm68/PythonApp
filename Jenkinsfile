
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat '"C:/Users/nabee/AppData/Local/Programs/Python/Python312/python.exe" -m compileall -q .'
            }
        }

        stage('Test') {
            steps {
                bat '"C:/Users/nabee/AppData/Local/Programs/Python/Python312/python.exe" -m pytest'
            }
        }

        stage('Package') {
            steps {
                bat '"C:/Users/nabee/AppData/Local/Programs/Python/Python312/python.exe" -m zipfile -c app.zip app.py test_app.py'
            }
        }
    }

    post {
        success {
            echo 'Python CI/CD Pipeline Successful!'
        }
        failure {
            echo 'Python CI/CD Pipeline Failed!'
        }
    }
}
