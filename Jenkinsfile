pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''pwd
ls
date
pwd
whoami'''
      }
    }

    stage('Deploy to test') {
      parallel {
        stage('Deploy to test') {
          steps {
            echo 'this is test env'
          }
        }

        stage('Testing') {
          steps {
            echo 'Sanity test'
          }
        }

      }
    }

    stage('Deploy to prod') {
      parallel {
        stage('Deploy to prod') {
          steps {
            sleep 10
          }
        }

        stage('Prod') {
          steps {
            echo 'First release'
          }
        }

      }
    }

  }
}