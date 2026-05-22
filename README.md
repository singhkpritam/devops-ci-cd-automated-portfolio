# 🚀 DevOps CI/CD Automated Portfolio

A complete DevOps automation project demonstrating Continuous Integration and Continuous Deployment using Docker, Kubernetes, Jenkins, and GitHub.

---

## 📌 Project Overview

This project automates the deployment process of a frontend web application.

Whenever code is pushed to GitHub, Jenkins automatically:

- Pulls the latest source code
- Builds a Docker image
- Pushes the image to Docker Hub
- Updates the Kubernetes deployment
- Deploys the latest application version automatically

---

## ⚙️ Tech Stack

- HTML5
- CSS3
- JavaScript
- Docker
- Docker Hub
- Kubernetes
- Minikube
- Jenkins
- GitHub
- Ubuntu VM

---

## 🔥 CI/CD Workflow

```text
Developer Push Code
        ↓
GitHub Repository
        ↓
Jenkins Pipeline Trigger
        ↓
Docker Image Build
        ↓
Docker Hub Push
        ↓
Kubernetes Deployment Update
        ↓
Application Live
```

---

## 📂 Project Structure

```text
devops-ci-cd-automated-portfolio/
│
├── index.html
├── style.css
├── app.js
├── Dockerfile
├── .dockerignore
├── .gitignore
├── deployment.yaml
├── service.yaml
├── Jenkinsfile
└── README.md
```

---

## 🐳 Docker Setup

### Build Docker Image

```bash
docker build -t singhkpritam/devops-portfolio:v1 .
```

### Run Docker Container

```bash
docker run -d -p 8081:80 singhkpritam/devops-portfolio:v1
```

### Push Image to Docker Hub

```bash
docker push singhkpritam/devops-portfolio:v1
```

---

## ☸️ Kubernetes Deployment

### Apply Deployment and Service

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### Access Application

```bash
minikube service devops-portfolio-service
```

---

## ⚡ Jenkins Automation

This project uses Jenkins Declarative Pipeline for CI/CD automation.

### Pipeline Stages

- Checkout Code
- Build Docker Image
- Docker Login
- Push Docker Image
- Deploy to Kubernetes

---

## 🔐 Features

- Automated CI/CD Pipeline
- Dockerized Frontend Application
- Kubernetes Deployment Automation
- Rolling Updates
- GitHub Webhook Integration
- Version-Based Docker Images
- Jenkins Pipeline Automation

---

## 🌐 GitHub Repository

https://github.com/singhkpritam/devops-ci-cd-automated-portfolio

---

## 👨‍💻 Author

Pritam Singh  
DevOps & Cloud Enthusiast 🚀
