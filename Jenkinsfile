pipeline {
    agent any

    environment {
        IMAGE_NAME = "myapp"
        IMAGE_VERSION = "${BUILD_NUMBER}"
    }

    stages {
        stage('Clean Workspace') {
            steps {
                sh 'rm -rf *'
            }
        }

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t ${IMAGE_NAME}:${IMAGE_VERSION} .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop myapp || true
                docker rm myapp || true
                docker run -d -p 8081:80 --name myapp ${IMAGE_NAME}:${IMAGE_VERSION} >/dev/null 2>&1
                '''
            }
        }
    }

    post {
        success {
            echo "Deployment successful"
        }
        failure {
            echo "Deployment failed"
        }
    }
}
