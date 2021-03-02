pipeline {

    agent { dockerfile true }
    stages {
        
      stage('build') {
            steps {
                sh 'docker build -t core .'
            }
      }
        
        stage('Test') {
            steps {
                sh 'python3 --version'
            }
        }
        
    }
}
