pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-first-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop my-container || true'
                sh 'docker rm my-container || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name my-container my-first-app'
            }
        }

    }
}