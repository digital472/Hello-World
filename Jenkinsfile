pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        awsIdentity()
        sh 'unzip deployment.zip'
      }
    }
  }
}