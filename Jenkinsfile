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
        timestamps() {
          timestamps()
        }

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