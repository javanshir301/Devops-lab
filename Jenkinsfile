pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github-token', url: 'https://github.com/javanshir301/Devops-lab.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Building the project..."'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
            }
        }
    }
}

