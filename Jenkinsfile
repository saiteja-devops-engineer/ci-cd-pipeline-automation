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
                    docker.build("${IMAGE_NAME}")
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
    }
}
