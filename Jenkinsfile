pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/oumaymabenbrahem/ateliergit.git'
            }
        }

        stage('Prepare Environment') {
            steps {
                sh 'java -version' // Vérifier que Java est installé
                sh 'gradle -v' // Vérifier que Gradle est installé
            }
        }

        stage('Build') {
            steps {
                sh 'gradle build' // Construire le projet avec Gradle global
            }
        }

        stage('Test') {
            steps {
                sh 'gradle test' // Exécuter les tests
            }
        }

        stage('Deploy') {
            steps {
                echo 'Déploiement en cours...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline terminé !'
        }
        success {
            echo 'Pipeline exécuté avec succès !'
        }
        failure {
            echo 'Pipeline échoué.'
        }
    }
}
