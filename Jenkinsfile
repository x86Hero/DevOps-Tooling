pipeline {
  agent {
    label "worker-01"
  }
  /* environment {} */
  stages {
    stage('Build') {
      steps{
        sh 'chmod +x build.sh'
        sh 'chmod +x test.sh'
        sh 'chmod +x deploy.sh'
        sh './build.sh'
      }
    }
    stage('Test') {
      steps{
        sh './test.sh'
      }
    }
    stage('Deploy') {
      steps{
        sh './deploy.sh'
      }
    }
  }
}
