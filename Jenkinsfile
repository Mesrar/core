library identifier: 'jenkins-shared@master', retriever: modernSCM(
 [$class: 'GitSCMSource',
  remote: 'https://github.com/MobodidTech/jenkins-shared.git',
 ])

pipeline {

    
    environment {
      appName = "server"
      registry = "mesrar/core"
      registryCredential = "DjangoServerRegistry"
      projectPath = "/var/lib/jenkins/workspace/marrakech_test_qa"
     }
    
    agent any
    
    parameters {
      gitParameter name: 'RELEASE_TAG',
       type: 'PT_TAG',
       defaultValue: 'master'
     }
    
    
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
        
    }
}

def getBuildName() {
 "${BUILD_NUMBER}_$appName:${params.RELEASE_TAG}"
}

def isMaster() {
 "${params.RELEASE_TAG}" == "master"
}
