# 🚀 CI/CD Pipeline with GitOps

## 📌 Overview

This project implements a simple **end-to-end CI/CD pipeline** using Jenkins and GitOps.

It automates:
- Build and Test
- Code Quality Check (SonarQube)
- Security Scan (Trivy)
- Docker Image Build & Push
- Deployment using ArgoCD
- Slack Notifications

---

## 🧱 Architecture

```text
GitHub → Jenkins → Build/Test → Docker → GitOps Repo → ArgoCD → Kubernetes → Slack
🛠️ Tools Used
Jenkins
Docker
Kubernetes
ArgoCD
SonarQube
Trivy
AWS EC2
Slack

🔄 Pipeline Flow
Code pushed to GitHub
Jenkins pipeline starts
Build and test executed
SonarQube checks code quality
Docker image is built and scanned
Image pushed to DockerHub
Kubernetes YAML updated
ArgoCD deploys application
Slack sends notification

🔢 Versioning
APP_VERSION = v${BUILD_NUMBER}

Example:
Build #1 → v1
Build #2 → v2

🔐 Credentials

Stored in Jenkins:

DockerHub credentials
GitHub token
SonarQube token
Slack token

📂 Project Structure
student-datastore-ci-cd/
├── Jenkinsfile
├── Dockerfile
├── pom.xml
└── src/

datastore-k8s-argocd/
└── datastore-deploy/
    └── datastore-deploy.yaml

Result
Automated CI/CD pipeline
GitOps-based deployment
Secure and scalable workflow

👨‍💻 Author

Rashmi Ranjan Panigrahy
