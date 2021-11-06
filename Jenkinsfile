pipeline {
  agent any
  tools{
    maven 'maven-3.8.3'
    
       }
  environment{
    PATH= "${PATH}"
   

  }
  
  stages {
        stage('Initial'){
             steps{
                    sh'''
                    echo "PATH= ${PATH}" 
                    
                    '''
                  }
        }
             

    stage('Git Checkout') {
     steps {
       git branch: 'main', credentialsId: 'githubID', url: 'https://github.com/houssembstn03/MYApp.git'
      }
    }
    stage("Maven Build"){
     steps {
                sh '''mvn install:install-file -Dfile='c:\\kaptcha-2.3.jar' -DgroupId=com.google.code -DartifactId=kaptcha -Dversion=2.3 -Dpackaging=jar'''
            }
            post {
                success {
                    junit 'target/surefire-reports/*/.xml' 
                }
            }
    }
  }
}
