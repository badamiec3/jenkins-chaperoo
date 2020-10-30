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
         sh "curl https://get.docker.com | sudo bash"
         sh 'sudo usermod -aG docker $(whoami)'
         sh "sudo apt update"
         sh "sudo apt install -y curl jq"
         sh 'expose version=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | jq -r '.tag_name')'
         sh 'sudo curl -L "https://github.com/docker/compose/releases/download/${version}/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose'
         sh "sudo chmod a+x /usr/local/bin/docker-compose"
      }
    }
     stage('Stage 3: Deploy') {
      steps {
        sh "echo 'deploy'"
        
      }
    }
  }

}


