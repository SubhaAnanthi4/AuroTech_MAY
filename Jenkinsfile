pipeline {
    agent any

    environment {
        APP_NAME = 'AuroTechApp'
        DEPLOY_SERVER = 'localhost:3001'

    }

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    git 'https://github.com/SubhaAnanthi4/AuroTech_MAY.git'
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    echo "Running tests..."
                    sh 'npm test'
                }
            }
        }

        stage('Build Application') {
            steps {
                script {
                    echo "Building application..."
                    sh 'npm run build'
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                script {
                    echo "Deploying to production..."
                    sh """
                    ssh user@${DEPLOY_SERVER} 'cd /path/to/your/app && git pull origin main && npm install && npm start'
                    """
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
