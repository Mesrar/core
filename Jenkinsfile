pipeline {

    agent { dockerfile true }
    stages {
        
      stage('Building image') {
              steps{
                script {
                  docker.build core
                }
              }
            }
        stage('Test') {
            steps {
                sh 'python3 --version'
            }
        }
    }
}
