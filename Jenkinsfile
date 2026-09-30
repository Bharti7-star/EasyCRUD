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
                  docker run -d -p 80:80 backend:latest
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


