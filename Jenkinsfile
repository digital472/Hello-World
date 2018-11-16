pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        awsIdentity()
        sh 'unzip deployment.zip'
      }
    }
    stage('Deploy') {
      steps {
        sh '''/usr/local/bin/custodian run --output-dir=. my-first-policy.yml
'''
      }
    }
  }
}