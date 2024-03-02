pipeline {
  agent any
  stages {
    stage('Install') {
      parallel {
        stage('Install') {
          steps {
            build 'npm install'
          }
        }

        stage('Ckeck node') {
          steps {
            sh '''node js --version
npm --version'''
          }
        }

      }
    }

    stage('Test') {
      steps {
        sh 'npm test'
      }
    }

    stage('error') {
      steps {
        echo 'Everything is okay'
      }
    }

  }
}