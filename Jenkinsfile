
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh ' docker build -t img . '
            }
        }

        stage('Deploy') {
            steps {
                sh ' docker run -p 3000:3000 -d img'
            }
        }
        
        
    }
}
