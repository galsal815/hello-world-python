pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/galsal815/hello-world-python', branch: 'master')
      }
    }

    stage('Build') {
      steps {
        sleep 5
      }
    }

    stage('Test') {
      steps {
        sleep 5
      }
    }

    stage('Push to dockerhub') {
      steps {
        sleep 5
      }
    }

  }
}