pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 priyankaca3/registration:v1'
                bat 'docker push priyankaca3/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f C:/DevOps/week2/deployment.yaml'
                bat 'kubectl apply -f C:/DevOps/week2/service.yaml'
            }
        }
    }
}
