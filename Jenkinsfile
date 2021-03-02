pipeline {
 environment {
  appName = "server"
  registry = "torkashavnd/django-server"
  registryCredential = "DjangoServerRegistry"
  projectPath = "/jenkins/data/workspace/django-server"
 }
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
