pipeline {
    agent any

    environment {
        IMAGE_NAME = "singhkpritam/devops-portfolio"
        IMAGE_TAG = "${BUILD_NUMBER}"
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/singhkpritam/devops-ci-cd-automated-portfolio.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t $IMAGE_NAME:$IMAGE_TAG ."
            }
        }

        stage('Docker Login') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                sh "docker push $IMAGE_NAME:$IMAGE_TAG"
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh "kubectl set image deployment/devops-portfolio-deployment \
                devops-portfolio-container=$IMAGE_NAME:$IMAGE_TAG"

                sh "kubectl rollout status deployment/devops-portfolio-deployment"

                sh "kubectl apply -f service.yaml"
            }
        }
    }

    post {
        success {
            echo "✅ Pipeline Successfully Completed!"
        }
        failure {
            echo "❌ Pipeline Failed - Check Logs"
        }
    }
}