pipeline {
    agent any
    stages {
        stage('1. Fetch Code') { steps { checkout scm } }
        stage('2. Build Image') { steps { sh 'docker compose build' } }
        stage('3. Run App') { steps { sh 'docker compose down || true'; sh 'docker compose up -d' } }
    }
}
