pipeline {

    agent { dockerfile true }
    stages {
        
      stage('Test') {
            steps {
                sh 'docker build -t core .'
            }
        stage('Test') {
            steps {
                sh 'python3 --version'
            }
        }
    }
}
