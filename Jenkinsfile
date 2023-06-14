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
        sh 'docker build -t hellow-world-python .'
      }
    }

    stage('Test') {
      steps {
        sh 'docker run -itd -p 8080:8080 --name hellow-world hello-world-python'
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