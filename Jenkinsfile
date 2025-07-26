pipeline {
  agent any

  environment {
    IMAGE_NAME = "yourdockerhub/flask-cicd-app"
  }

  stages {
    stage('Clone Repository') {
      steps {
        git 'https://github.com/saiteja-devops-engineer/ci-cd-pipeline-automation.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        dir('app/flask-app') {
          script {
            docker.build("${IMAGE_NAME}")
          }
        }
      }
    }

    stage('Push to DockerHub') {
      steps {
        withDockerRegistry([credentialsId: 'dockerhub-creds', url: '']) {
          sh "docker push ${IMAGE_NAME}:latest"
        }
      }
    }

    stage('Deploy to EKS') {
      steps {
        sh 'kubectl apply -f k8s/deployment.yaml'
      }
    }

    stage('Health Check') {
      steps {
        sh 'python3 scripts/health_check.py'
      }
    }
  }
}