pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build and Test') {
            steps {
                bat 'docker-compose build'
                bat 'docker-compose up --exit-code-from ai-recruiting-platform-tests'
            }
        }
        
        stage('Push Images') {
            steps {
                bat 'docker-compose push'
            }
        }
    }
}
