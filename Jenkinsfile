pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                git branch: 'main', credentialsId: 'token', url: 'https://github.com/Bharti7-star/EasyCRUD.git' 
            }
        }
        stage('Create DB') {
            steps {
                sh '''
               docker network create app-network || true
               docker rm -f mysql-db || true   
              docker run -d \
              --name mysql-db \
              --network app-network \
              -e MARIADB_ROOT_PASSWORD=123 \
              -e MARIADB_DATABASE=student_app \
              mariadb:latest
        '''
    }
        }
        stage('Build backend') {
            steps {
                sh '''
                cd backend
                 docker build -t backend .
                  docker run -d --network app-network -p 8081:8080 backend:latest
                    
                   '''
 }
}
       stage('Build frontend') {
            steps {
                sh '''
                cd frontend
                 --network app-network \
                  docker build -t frontend .
                  docker run -d --network app-network -p 8000:80 frontend:latest
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


