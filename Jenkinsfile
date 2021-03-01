pipeline {
  agent {
    docker {
      image 'python:3.7.2'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'virtualenv -p python3 venv'
        sh 'virtualenv -p python3.7 venv'
        sh 'pip3 install -r requirements.txt'
      }
    }

    stage('test') {
      steps {
        sh 'python3 test.py'
      }
    }

  }
}