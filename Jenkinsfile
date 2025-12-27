pipeline {
    agent any
    stages {
        stage('Test Docker') {
            steps {
                sh 'docker run --rm nginx:alpine'
            }
        }
    }
}
