pipeline {
    agent any
    stages {
        stage('1. Fetch Code') {
            steps {
                checkout scm
            }
        }
        stage('2. Clean Existing App') {
            steps {
                // Pazhaya containers running-la irundha stop panni clear pannuvom
                sh 'docker compose down || true'
            }
        }
        stage('3. Build & Run App via Compose') {
            steps {
                // Docker Compose vachu project-a fresh-ah build panni background-la run panrom
                sh 'docker compose up --build -d'
            }
        }
    }
}
