pipeline {
    agent any

    environment {
        APP_NAME = 'AuroTechApp'
        DEPLOY_SERVER = 'localhost:3000'  // Use localhost for local deployment or any server
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

        stage('Deploy Frontend') {
            steps {
                script {
                    // Deploying the static files using a simple web server (Python HTTP Server)
                    echo 'Deploying frontend application...'
                    sh 'python3 -m http.server 3000 &'
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

