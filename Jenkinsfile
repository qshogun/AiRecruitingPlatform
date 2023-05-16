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
                sh 'docker-compose build'
                sh 'docker-compose up --exit-code-from ai-recruiting-platform-tests'
            }
        }
        
        stage('Push Images') {
            steps {
                sh 'docker-compose push'
            }
        }
    }
}
