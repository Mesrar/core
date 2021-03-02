pipeline {

    agent { dockerfile true }
    stages {
        
      stage('build') {
            steps {
                script{
                    docker.build
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
