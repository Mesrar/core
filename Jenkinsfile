pipeline {
  agent {
    docker {
      image 'python:3.7.2'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'docker build -t saleor_marrakech .'
      }
    }

  }
}
