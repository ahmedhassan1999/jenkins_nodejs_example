pipeline {
  agent any
  stages {
    stage('Build and push image') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'docker-hub', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
          sh 'docker build -t ahmedhassan00/hello .'
          sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
          sh 'docker push ahmedhassan00/hello'
          sh 'docker run -d -p 3000:3000  ahmedhassan00/hello'
        }
      }
    }
  }
}  