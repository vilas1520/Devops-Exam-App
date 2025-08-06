pipeline {
    agent any

    environment {
        COMPOSE_PROJECT_NAME = "exam-app-project"
    }

    stages {
        stage("Clone repository") {
            steps {
                echo "Cloning code..."
                git url: 'https://github.com/VedTambe/Devops-Exam-App.git', branch: 'main'
            }
        }
        stage("Build Docker image") {
            steps {
                echo "Building Docker image..."
                sh 'docker-compose build'
            }
        }
        stage("Start project") {
            steps {
                echo "Starting project containers..."
                sh 'docker-compose up -d'
            }
        }
        stage("Verify running containers") {
            steps {
                echo "Verifying containers..."
                sh 'docker ps'
            }
        }
    }

    post {
        always {
            echo "Pipeline finished!"
        }
    }
}
