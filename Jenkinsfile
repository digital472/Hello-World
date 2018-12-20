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
      environment {
        PATH = "/usr/local/bin:$PATH"
      }
      steps {
        script {
          def buildspec = readYaml (file: 'buildspec.yml')
          for (int i=0; i < buildspec.phases.build.commands.size(); i++) {
            sh buildspec.phases.build.commands[i]
          }
        }
      }
    }
  }
}
