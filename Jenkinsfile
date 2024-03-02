pipeline {
  agent any
  stages {
    stage('Git checkout') {
      steps {
        git(url: 'git \'https://github.com/dzidzi91/react-login-form.git\'', branch: 'master', poll: true)
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t jenkins-image .'
      }
    }

    stage('Docker login') {
      steps {
        sh 'docker login -u ${dockerhub_credentials}'
      }
    }

    stage('Docker push') {
      steps {
        sh 'docker push dzidzi91/jenkins:v1'
      }
    }

    stage('Docker logout') {
      steps {
        sh 'docker logout'
      }
    }

  }
  environment {
    dockerhub_credentials = 'dockerhub_ID'
  }
}