pipeline {

    agent any

    environment {
        IMAGE_NAME = "rayyan3210/hello-devops-app:latest"
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Code already checked out by Jenkins'
            }
        }


        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }


        stage('Build Docker Image') {
            steps {
                bat 'docker build -t %IMAGE_NAME% .'
            }
        }


        stage('Login to Docker Hub') {
            steps {
                withCredentials([
                    usernamePassword(
                        credentialsId: 'dockerhub-creds',
                        usernameVariable: 'DOCKER_USER',
                        passwordVariable: 'DOCKER_PASS'
                    )
                ]) {

                    bat 'docker login -u %DOCKER_USER% -p %DOCKER_PASS%'

                }
            }
        }


        stage('Push Docker Image') {
            steps {
                bat 'docker push %IMAGE_NAME%'
            }
        }


        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f k8s/'
            }
        }

    }
}