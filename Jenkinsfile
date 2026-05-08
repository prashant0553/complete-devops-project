
pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "prashant0553/devops-node-app"
    }

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/prashant0553/complete-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push $DOCKER_IMAGE'
            }
        }

        stage('Deploy Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/deployment.yaml'
                sh 'kubectl apply -f k8s/service.yaml'
            }
        }
    }
}