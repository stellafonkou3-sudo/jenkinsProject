pipeline {
    agent any  // Utilise n'importe quel agent disponible

    stages {
        stage('Cloner le code') {
            steps {
                // Cloner le dépôt Git
                git url: 'https://votre-repo-git.git', branch: 'main'
            }
        }

        stage('Compiler le code') {
            steps {
                // Compiler le projet avec Maven
                sh 'mvn clean compile'
            }
        }

        stage('Tests unitaires') {
            steps {
                // Exécuter les tests unitaires avec Maven
                sh 'mvn test'
            }
        }

        stage('Déployer sur Tomcat') {
            steps {
                // Déployer l'application sur Tomcat
                // Exemple via le plugin Tomcat Maven, ou copie du .war dans le dossier webapps
                sh '''
                    mvn package
                    cp target/votre-app.war /chemin/vers/tomcat/webapps/
                '''
            }
        }
    }

    post {
        always {
            echo 'Pipeline terminé'
        }
        success {
            echo 'Pipeline exécuté avec succès !'
        }
        failure {
            echo 'Échec du pipeline'
        }
    }
}
