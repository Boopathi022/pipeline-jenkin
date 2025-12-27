pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh '''
                docker build -t myapp:latest .
                '''
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop myapp || true
                docker rm myapp || true
                docker run -d -p 8080:80 --name myapp myapp:latest
                '''
            }
        }

        stage('Debug') {
            steps {
                sh '''
                docker ps -a
                '''
            }
        }
    }
}

