pipeline {
  agent {
    docker {
      image 'python:3.7.2'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'sudo pip3 install -r requirements.txt --user'
      }
    }

    stage('test') {
      steps {
        sh 'python3 test.py'
      }
    }

  }
}