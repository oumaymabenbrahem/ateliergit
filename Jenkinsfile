pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Cloner le dépôt
                git branch: 'master', url: 'https://github.com/oumaymabenbrahem/ateliergit.git'
            }
        }

        stage('Build') {
            steps {
                // Commandes pour construire ton projet
                sh './gradlew build' // Si c'est un projet Java avec Gradle
                // mvn clean install (si Maven est utilisé)
                // npm install (si c'est un projet Node.js)
            }
        }

        stage('Test') {
            steps {
                // Exécuter les tests
                sh './gradlew test' // Exemple pour Gradle
                // sh 'npm test' ou autres selon ton projet
            }
        }

        stage('Deploy') {
            steps {
                // Déployer ton projet (ajouter ta logique ici)
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
