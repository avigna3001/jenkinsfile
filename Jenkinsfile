pipeline {
    agent any

    environment {
        IMAGE_NAME = "shravani3001/simple-app"
    }

    stages {
        stage('Clone App Repo') {
            steps {
                git 'https://github.com/YOUR_USERNAME/YOUR_NODEJS_APP_REPO.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t $IMAGE_NAME ."
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    withDockerRegistry([credentialsId: 'dockerhub-creds', url: '']) {
                        sh "docker push $IMAGE_NAME"
                    }
                }
            }
        }
    }
}

