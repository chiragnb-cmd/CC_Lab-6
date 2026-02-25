pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/chiragnb-cmd/CC_Lab-6.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t backend-app backend'
            }
        }

        stage('Run Backend Container') {
            steps {
                sh 'docker run -d -p 5001:5000 backend-app'
            }
        }
    }
}
