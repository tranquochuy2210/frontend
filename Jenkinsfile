pipeline {
    agent any
    stages {
        stage('start') {
            steps {
                echo "hello world"
            }
        }
        stage('docker hub') {
            steps {
                withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t frontend .'
                    sh 'docker tag frontend 225702921/frontend:v1'
                    sh 'docker push 225702921/frontend:v1'
                }
            }
        }
    }
}