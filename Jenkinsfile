pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t aceest-gym .'
            }
        }

        stage('Run Tests in Docker') {
            steps {
                bat 'docker run --rm aceest-gym pytest'
            }
        }
    }
}