pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        build 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'npm test'
      }
    }

    stage('') {
      steps {
        echo 'Everything is okay'
      }
    }

  }
}