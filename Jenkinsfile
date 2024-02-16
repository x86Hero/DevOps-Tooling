pipeline {
  agent {
    label "worker-01"
  }
  /* environment {} */
  stages {
    stage('Build') {
      steps{
        sh 'docker network create lab3-net'
        sh 'docker build -t flask-app .'
      }
    }
    stage('Deploy') {
      steps{
        sh 'docker run -d --network lab3-net --name flask-app flask-app'
        sh 'docker run -d -p 80:80 --network lab3-net --name nginx nginx'
      }
    }
    stage('Test') {
      steps{
        sh 'curl localhost'
      }
    }
  }
}
