pipeline {
    agent any

    environment {
        IMAGE_NAME = "saitejadevopsengineer/flask-cicd-app"
    }

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/saiteja-devops-engineer/ci-cd-pipeline-automation.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${IMAGE_NAME}", "-f ./flask-app/Dockerfile ./flask-app")
                }
            }
        }

        stage('Push to DockerHub') {
            steps {
                script {
                    docker.withRegistry('', 'dockerhub') {
                        docker.image("${IMAGE_NAME}").push("latest")
                    }
                }
            }
        }

        stage('Deploy to EKS') {
            steps {
                script {
                    // Ensure that Jenkins can run kubectl
                    // This command assumes kubectl is installed and configured with the proper kubeconfig (or AWS CLI is used to configure it)
                    bat 'kubectl apply -f k8s-deployment.yaml'
                }
            }
        }
    }
}
