pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                git branch: 'main', credentialsId: 'token', url: 'https://github.com/Bharti7-star/EasyCRUD.git' 
            }
        }
        stage('Build backend') {
            steps {
                sh '''
                cd backend
                  docker build -t backend .
                  docker run -d -p 8081:8080 backend:latest
                   '''
 }
}
       stage('Build frontend') {
            steps {
                sh '''
                cd frontend
                  docker build -t frontend .
                  docker run -d -p 8000:80 frontend:latest
                   '''
 }
}
        
        
        
        
 stage('Test') {
            steps {
              echo 'Test Completed'
               
                }
            }
        }
}


