pipeline {
  agent any
  environment{
    PATH = "/opt/maven3/bin:$PATH"
  }
  stages {
    stage('Git Checkout') {
     steps {
       git branch: 'main', credentialsId: 'githubID', url: 'https://github.com/houssembstn03/MYApp.git'
      }
    }
    stage("Maven Build"){
      steps{
        sh "mvn clean package"
      }
    }
  }
}