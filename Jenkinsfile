pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/chiragnb-cmd/CC_Lab-6.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                docker build -t backend-app ./backend
                '''
            }
        }

        stage('Stop Old Container If Running') {
            steps {
                sh '''
                docker rm -f backend-container || true
                '''
            }
        }

        stage('Run Backend Container') {
            steps {
                sh '''
                docker run -d -p 5001:5000 --name backend-container backend-app
                '''
            }
        }
    }
}
