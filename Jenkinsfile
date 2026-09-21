pipeline {
    agent any
    stages {
        stage('1. Fetch Code') {
            steps {
                // Pulls the latest source code from the configured Git repository source
                checkout scm
            }
        }
        stage('2. Clean Existing App') {
            steps {
                // Safely stops and removes any previously running containers and networks
                sh 'docker compose down || true'
            }
        }
        stage('3. Build & Run App via Compose') {
            steps {
                // Rebuilds the image from scratch and starts the container in detached background mode
                sh 'docker compose up --build -d'
            }
        }
    }
}
