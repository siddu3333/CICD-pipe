pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build --no-cache -t vite-app .'
            }
        }    
        stage('Deploy Container') {
            steps {
                bat '''
                docker stop vite-Container || echo Container not running
                docker rm vite-container || echo Container not found
                docker run -d -p 8081:80 --name vite-c0ntainer vite-app
                '''
                
            }
        }   
    }
}