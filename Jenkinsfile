pipeline {
  agent any
  stages {
    stage('Checkout SCM') {
      steps {
        timestamps() {
          echo 'Build Started'
          sleep 5
        }

      }
    }
    stage('Tool Existence Check') {
      parallel {
        stage('Tool Existence Check') {
          steps {
            sh '''#!/bin/bash

echo "................................."
echo "Hello World"
echo "................................."
echo "This is a test"
echo "................................."
echo "Script Found: TEST OK"
echo "................................."'''
          }
        }
        stage('Check Date') {
          steps {
            sh '''#!/bin/bash

echo "................................."
echo "Current Date & Time is: $(date)"
echo "................................."
echo "This is server $(hostname)"
echo "................................."'''
          }
        }
      }
    }
  }
  environment {
    hostname = 'abr4win10plp'
  }
}