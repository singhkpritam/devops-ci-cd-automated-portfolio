pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/singhkpritam/devops-ci-cd-automated-portfolio.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t singhkpritam/devops-portfolio:v1 .'
            }
        }

        stage('Docker Login') {
            steps {
                sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push singhkpritam/devops-portfolio:v1'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}
