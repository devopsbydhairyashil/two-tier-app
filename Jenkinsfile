pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/<your-username>/two-tier-app.git'
            }
        }

        stage('Build & Deploy') {
            steps {
                sh 'sudo docker compose down || true'
                sh 'sudo docker compose up -d --build'
            }
        }
    }

    post {
        success {
            echo '✅ Deployment Successful!'
        }
        failure {
            echo '❌ Build Failed!'
        }
    }
}
