pipeline {
  agent any
  stages {
    stage ('test') {
      steps {
        bat 'docker ps -a'
      }
    }
    stage ('Run Docker Compose') {
      steps {
        bat 'docker-compose up  -d'
      }
      }
      
    }
  post {
    success {
     slackSend channel: '#aléatoire', message: 'code sucess'
    }
    failure {
     slackSend channel: '#aléatoire', message: 'code error'
    }
  }
}
