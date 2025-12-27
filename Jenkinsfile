pipeline {
    agent any
    stages {
        stage('Test Docker') {
            steps {
                sh 'docker run -d -p 8081:80 --name myapp nginx >/dev/null 2>&1 &'
            }
        }
    }
}

