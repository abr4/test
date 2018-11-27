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
    stage('Github feature') {
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
            echo 'Shell Execution Begin'
            sh '''echo "Execution START at $(date)"
sh welcome.sh
echo "Execution END at $(date)"'''
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