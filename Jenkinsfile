library identifier: 'jenkins-shared@master', retriever: modernSCM(
 [$class: 'GitSCMSource',
  remote: 'https://github.com/MobodidTech/jenkins-shared.git',
 ])

pipeline {

    
    environment {
      appName = "server"
      registry = "mesrarbrand/saleor"
      registryCredential = "dockerHub"
      projectPath = "/var/lib/jenkins/workspace/marrakech_test_qa"
     }
    
    agent any
    
    
    
    stages {
        
         stage('Build Image') {
           steps {
            script {
             if (isMaster()) {
              dockerImage = docker.build "$registry:latest"
             } else {
              dockerImage = docker.build "$registry:${params.RELEASE_TAG}"
             }
            }
           }
          }
        
        stage('Test') {
            steps {
                sh 'python3 --version'
            }
        }
     
     stage('run server'){
      steps{
       script{
         docker.image("$registry:${params.RELEASE_TAG}").run("-p 127.0.0.1:8000:8000 ")
       }
      }
     }
     
     stage('Deploy Image') {
        steps {
         script {
           docker.withRegistry('', registryCredential) {
           dockerImage.push()
           }
         }
        }
   }
        
    }
}
def isMaster() {
 "${params.RELEASE_TAG}" == "master"
}
