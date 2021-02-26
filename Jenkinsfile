pipeline {
  agent {
    docker {
      image 'slaeor_core'
    }

  }
  stages {
    stage('stage') {
      steps {
        sh '''
node {
def installed = fileExists \'bin/activate\'

if (!installed) {
    stage("Install Python Virtual Enviroment") {
        sh \'virtualenv --no-site-packages .\'
    }
}   

stage ("Get Latest Code") {
    checkout scm
}

stage ("Install Application Dependencies") {
    sh \'\'\'
        source bin/activate
        pip install -r saleor/requirements.txt
        deactivate
       \'\'\'
}

stage ("Collect Static files") {
    sh \'\'\'
        source bin/activate
        python manage.py collectstatic --noinput
        deactivate
       \'\'\'
}
}'''
      }
    }

  }
  environment {
    ALLOWED_HOSTS = 'ALLOWED_HOSTS'
  }
}