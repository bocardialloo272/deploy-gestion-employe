pipeline {
    // agent windows 1
    agent {
        label 'agent-windows'
    }

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Pull Images') {
            steps {
                bat 'docker compose pull'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker compose up -d'
            }
        }
    }

    post {
        success {
            echo 'Déploiement réussi.'
        }
        failure {
            echo 'Le déploiement a échoué, vérifiez les logs Jenkins.'
        }
    }
}