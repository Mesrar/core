pipeline {

    agent { dockerfile true }
    stages {
        
      stage('Building image') {
              steps{
                script {
                  docker.build registry + ":$BUILD_NUMBER"
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
