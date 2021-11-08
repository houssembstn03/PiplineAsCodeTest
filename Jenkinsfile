pipeline {
  agent any
  tools{
    maven 'maven-3.8.3'
    
    

       }
  environment{
    PATH= "${PATH}"
   

  }
  
  stages {
        
             

    stage('Git Checkout') {
     steps {
       git branch: 'master', credentialsId: 'githubID', url: 'https://github.com/houssembstn03/PiplineAsCodeTest.git'
      }
    }

    stage ('maven Build') {
            steps {
                sh 'mvn clean package' 
            }
           
        }
   
  }
}
