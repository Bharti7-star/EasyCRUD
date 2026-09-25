
pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                git branch: 'main',
                credentialsId: 'new',
                url: 'https://github.com/Bharti7-star/EasyCRUD.git'    
            }
        }
        stage('Build') {
            steps {
                 sh '''cd backend
                mvn clean package -DskipTests'''            }
        }

        stage('Test') {
            steps {
                echo 'Test Completed'
            }
        }
    }
}
