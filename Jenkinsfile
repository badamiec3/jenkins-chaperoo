pipeline {
  agent any
  stages{
    stage('Stage 1: Clone Repo') {
      steps {

      sh 'git clone https://github.com/badamiec3/chaperootodo_client-.git' 
     
      }
    }
    stage('Stage 2: Install Docker and Docker-compose') {
      steps {
         sh "echo 'install docker'"
      }
    }
     stage('Stage 3: Deploy') {
      steps {
        sh "echo 'deploy'"
        
      }
    }
  }

}


