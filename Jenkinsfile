pipeline {
    agent any  
    stages {
        stage("test") {
            steps {
                echo "hello world"
            }
        }
        stage("build") {
            steps {
                bat "docker-compose up -d --build"
            }
        }
    }
    post {
        success {
            emailext (
                subject: "Notification de build Jenkins - Succès",
                body: "Le build de votre pipeline Jenkins s'est terminé avec succès.",
                to: "sambasy837@gmail.com",
            )
        }
        failure {
            emailext (
                subject: "Notification de build Jenkins - Échec",
                body: "Le build de votre pipeline Jenkins a échoué.",
                to: "sambasy837@email.com",
            )
        }
    }
}
