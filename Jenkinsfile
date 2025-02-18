pipeline {
    agent any

    environment {
        IMAGE_NAME = "javanshir301/devops-lab"
        IMAGE_TAG = "latest"
        DOCKER_HUB_CREDENTIALS = "docker-hub-cred"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/javanshir301/Devops-lab.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:$IMAGE_TAG .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withDockerRegistry([credentialsId: DOCKER_HUB_CREDENTIALS, url: 'https://index.docker.io']) {
                    sh 'docker push $IMAGE_NAME:$IMAGE_TAG'
                }
            }
        }
    }
}

