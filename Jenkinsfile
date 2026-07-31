pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                    credentialsId: 'github-cred',
                    url: 'https://github.com/Tamanna2732/mern-amazona-devops.git'
            }
        }

        stage('Build Docker Images') {
            steps {
                sh 'docker compose build'
            }
        }

        stage('Deploy Application') {
            steps {
                sh 'docker compose down || true'
                sh 'docker compose up -d'
            }
        }

        stage('Verify Deployment') {
            steps {
                sh 'docker ps'
            }
        }

    }
}