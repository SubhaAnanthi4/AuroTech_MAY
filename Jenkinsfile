pipeline {
    agent any

    environment {
        APP_NAME = 'AuroTechApp'
        DEPLOY_SERVER = 'localhost:3000'  // Use your server's IP or hostname if needed
    }

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    // Cloning the repository from GitHub
                    git 'https://github.com/SubhaAnanthi4/AuroTech_MAY.git'
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

        stage('Run Tests') {
            steps {
                script {
                    // Run tests using npm
                    echo 'Running tests...'
                    sh 'npm test'
                }
            }
        }

        stage('Build Application') {
            steps {
                script {
                    // Build the application
                    echo 'Building application...'
                    sh 'npm run build'
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                script {
                    // Deploy the application by starting the server
                    echo 'Deploying to production...'
                    sh 'npm start'
                }
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
