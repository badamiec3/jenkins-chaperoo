pipeline {
  agent any
   environment{
      DB_PASSWORD=credentials('DATABASE_PASSWORD')
  }
  stages{
    stage('Stage 1: Clone Repo') {
      steps {

      sh 'git clone https://github.com/badamiec3/chaperootodo_client.git'
     
      }
    }
    stage('Stage 2: Install Docker and Docker-compose') {
      steps {
        sh 'whoami'
        sh "curl https://get.docker.com | sudo bash"
        sh 'sudo usermod -aG docker $(whoami)'
        sh "sudo apt update"
        sh "sudo apt install -y curl jq"
        sh 'sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose'
        sh "sudo chmod a+x /usr/local/bin/docker-compose"
        sh "docker-compose --version"
      }
    }
     stage('Stage 3: Deploy') {
      steps {
        
        sh 'ls'
        sh 'chmod 777 /home/jenkins/.jenkins/workspace/jenkins-chaperoo/chaperootodo_client'
        sh "cd /home/jenkins/.jenkins/workspace/jenkins-chaperoo/chaperootodo_client"
        sh 'ls'
        sh 'pwd'
        sh "docker-compose pull && docker-compose up -d"
        
      }
    }
  }

}


