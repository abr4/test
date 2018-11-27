pipeline {
  agent any
  stages {
    stage('Checkout SCM') {
      steps {
        timestamps() {
          sleep 5
        }

      }
    }
    stage('Time') {
      steps {
        git(url: 'https://github.com/abr4/test', branch: 'feature', changelog: true)
      }
    }
    stage('File list') {
      steps {
        //bat(returnStatus: true, returnStdout: true, encoding: 'ASCII', script: 'listfiles.bat')
        bat "listfiles.bat"
      }
    }
    stage('Test Finish') {
      steps {
        //mail(subject: 'Build Finish', body: 'Build Finish for Test devops.local', to: 'abr4@3ds.com', from: 'abr4@3ds.com')
        echo "%PATH%"
      }
    }
  }
  environment {
    hostname = 'abr4win10plp'
  }
}
