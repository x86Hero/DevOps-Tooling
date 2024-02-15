pipeline {
  agent {
    label "worker-01"
  }
  /* environment {} */
  stages {
    stage('Build') {
      steps{
        sh 'touch ~/jenkins-test/script.sh'
        sh 'echo "echo "Im running!"" > script.sh'
      }
    }
    stage('Test') {
      steps{
        sh 'cd ~/jenkins-test/'
        sh 'ls -a'
        sh 'chmod +x script.sh'
        sh './script.sh'
      }
    }
    stage('Deploy') {
      steps{
        sh 'mkdir ~/deployed'
        sh 'mv ~/jenkins-test/script.sh ~/deployed/script.sh'
        sh 'ls ~/deployed'
      }
    }
  }
}
