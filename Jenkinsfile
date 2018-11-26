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
        bat(returnStatus: true, returnStdout: true, encoding: 'ASCII', script: 'abr4.bat')
      }
    }
    stage('Test Finish') {
      steps {
        sh 'echo "DONE"'
      }
    }
  }
  environment {
    hostname = 'abr4win10plp'
  }
}