pipeline {
    agent any

    environment {
        IMAGE_NAME = "myapp"
        IMAGE_TAG  = "${BUILD_NUMBER}"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Boopathi022/pipeline-jenkin.git'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:$IMAGE_TAG .'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker stop myapp || true
                docker rm myapp || true
                docker run -d -p 8082:80 --name myapp $IMAGE_NAME:$IMAGE_TAG
                '''
            }
        }
    }
}
