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
      parallel {
        stage('File list') {
          steps {
            bat 'listfiles.bat'
          }
        }
        stage('Linux Script') {
          steps {
            sh 'sh welcome.sh'
          }
        }
      }
    }
    stage('Test Finish') {
      steps {
        bat 'echo %PATH%'
      }
    }
  }
  environment {
    hostname = 'abr4win10plp'
  }
}