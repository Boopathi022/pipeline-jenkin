pipeline {
    agent any

    environment {
        IMAGE_VERSION = "${env.BUILD_NUMBER}"
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/YOUR_USERNAME/YOUR_REPO.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:${IMAGE_VERSION} .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh '''
                docker stop myapp || true
                docker rm myapp || true
                '''
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p 8081:80 --name myapp myapp:${IMAGE_VERSION}'
            }
        }
    }
}

