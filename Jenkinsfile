pipeline {
  agent any
  environment {
  acr_registry = "apinode"
  }
  stages {
    stage('checkout scm') {
      steps{
      checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'git_creds', url: 'https://github.com/harikrishnapalakila/aksapi.git']])
    }
    }
    stage("ce-terraform-cms-api-build") {
            steps {
                script {
                  cmsapi = docker.build("${acr_registry}:${env.BUILD_ID}")
                    
                }
            }
        }
    
  
  }

}
