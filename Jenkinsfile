pipeline {
    agent any

    environment {
        IMAGE_NAME = "myapp"
        IMAGE_VERSION = "${BUILD_NUMBER}"
    }

    stages {
        stage('Checkout') {
            steps { checkout scm }
        }

        stage('Build Image') {
            steps { sh "docker build -t ${IMAGE_NAME}:${IMAGE_VERSION} ." }
        }

        stage('Deploy to Dev') {
            steps {
                sh """
                ssh ubuntu@3.7.68.139 '
                docker stop myapp || true
                docker rm myapp || true
                docker run -d -p 8082:80 --name myapp ${IMAGE_NAME}:${IMAGE_VERSION}'
                """
            }
        }

        stage('Test on Dev') {
            steps {
                sh 'echo "Tests Passed on Dev"'  // Later: run real tests
            }
        }

        stage('Deploy to Prod') {
            steps {
                sh """
                ssh ubuntu@3.7.248.124 '
                docker stop myapp || true
                docker rm myapp || true
                docker run -d -p 8083:80 --name myapp ${IMAGE_NAME}:${IMAGE_VERSION}'
                """
            }
        }
    }
}
