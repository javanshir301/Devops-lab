pipeline {
    agent any
    environment {
        VIRTUAL_ENV = 'venv'
    }
    stages {
        stage('Checkout') {
            steps { 
                git credentialsId: 'github-token', url: 'https://github.com/javanshir301/Devops-lab.git', branch: 'main'
            }
        }
        stage('Setup Python') {
            steps {
                sh 'python3 -m venv ${VIRTUAL_ENV}'
                sh 'source ${VIRTUAL_ENV}/bin/activate && pip install -r requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'source ${VIRTUAL_ENV}/bin/activate && pytest'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying the application..."'
            }
        }
    }
}

