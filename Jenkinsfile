
// pipeline {
//     agent any

//     environment {
//         DOCKER_IMAGE = "prashant0553/devops-node-app"
//     }

//     stages {

//         stage('Clone Code') {
//             steps {
//                 git branch: 'main', url: 'https://github.com/prashant0553/complete-devops-project.git'
//             }
//         }

//         stage('Build Docker Image') {
//             steps {
//                 sh 'docker build -t $DOCKER_IMAGE .'
//             }
//         }

//         stage('Push Docker Image') {
//             steps {
//                 sh 'docker push $DOCKER_IMAGE'
//             }
//         }

//         stage('Deploy Kubernetes') {
//             steps {
//                 sh 'kubectl apply -f k8s/deployment.yaml'
//                 sh 'kubectl apply -f k8s/service.yaml'
//             }
//         }
//     }
// }

pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/prashant0553/complete-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t prashant0553/devops-node-app .'
            }
        }

        stage('Push Docker Image') {
            steps {
                bat 'docker login -u prashant0553 -p your_real_password'
                bat 'docker push prashant0553/devops-node-app'
            }
        }

        stage('Deploy Kubernetes') {
            steps {
                echo 'Deploying to Kubernetes...'
            }
        }
    }
}