pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/galsal815/hello-world-python.git', branch: 'master')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t galsal/hello-world-python:$BUILD_NUMBER .'
      }
    }

    stage('Test') {
      steps {
        sh 'docker run -itd -p 8080:8080 --name hello-world galsal/hello-world-python:$BUILD_NUMBER'
        sleep 5
        sh 'curl localhost:8080'
        sh 'docker stop hellow-world && docker rm hello-world'
      }
    }

    stage('Push to dockerhub') {
      steps {
        sleep 5
      }
    }

  }
}