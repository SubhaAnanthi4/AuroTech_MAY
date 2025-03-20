pipeline {
    agent any

    environment {
        APP_NAME = 'AuroTechApp'
        DEPLOY_SERVER = 'localhost:3000'  // Use localhost with port 3000 for local deployment
    }

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    // Cloning the repository from GitHub
                    git branch: 'main', url: 'https://github.com/SubhaAnanthi4/AuroTech_MAY.git'
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Install dependencies via npm
                    echo 'Installing dependencies...'
                    sh 'npm install'
                }
            }
        }

        stage('Build Application') {
            steps {
                script {
                    // Build the application (e.g., React app)
                    echo 'Building application...'
                    sh 'npm run build'
                }
            }
        }

        stage('Start Local Server') {
            steps {
                script {
                    // Start the local server (e.g., for React app)
                    echo 'Starting local server on localhost:3000...'
                    sh 'npm start &'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded! The application is running on localhost:3000.'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
