# 🚀 End-to-End CI/CD Pipeline with GitOps

![Jenkins](https://img.shields.io/badge/Jenkins-CI-blue?logo=jenkins)
![Docker](https://img.shields.io/badge/Docker-Containerization-blue?logo=docker)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestration-blue?logo=kubernetes)
![ArgoCD](https://img.shields.io/badge/ArgoCD-GitOps-orange?logo=argo)
![SonarQube](https://img.shields.io/badge/SonarQube-Code%20Quality-green?logo=sonarqube)
![Trivy](https://img.shields.io/badge/Trivy-Security-red)
![AWS](https://img.shields.io/badge/AWS-Cloud-orange?logo=amazonaws)
![Slack](https://img.shields.io/badge/Slack-Notification-purple?logo=slack)

---

## 📌 Project Overview

This project demonstrates a **production-ready DevOps CI/CD pipeline** using GitOps principles.

✔ Automated Build, Test & Deployment  
✔ Docker Image Creation & Security Scan  
✔ Code Quality Analysis using SonarQube  
✔ GitOps Deployment using ArgoCD  
✔ Real-time Slack Notifications  

---

## 🧱 Architecture

```text
Developer → GitHub → Jenkins → Build/Test → Sonar/Trivy
        → Docker Push → GitOps Repo Update → ArgoCD → Kubernetes → Slack

⚙️ Tech Stack
Jenkins (CI/CD)
Docker (Containerization)
Kubernetes (Deployment)
ArgoCD (GitOps)
SonarQube (Code Quality)
Trivy (Security Scan)
AWS EC2 (Infrastructure)
Slack (Notifications)
🔄 Pipeline Flow
Code pushed to GitHub
Jenkins triggers pipeline
Build & Test executed
SonarQube analysis + Quality Gate
Docker image built & scanned (Trivy)
Image pushed to DockerHub
GitOps repo updated
ArgoCD deploys application
Slack sends notification
🔢 Auto Versioning
APP_VERSION = v${BUILD_NUMBER}

Example:

Build #10 → v10
Build #11 → v11
🔐 Credentials Used
DockerHub Credentials
GitHub Token
SonarQube Token
Slack Token

(All stored securely in Jenkins Credentials Manager)

📂 Project Structure
student-datastore-ci-cd/
├── Jenkinsfile
├── Dockerfile
├── src/
└── pom.xml

datastore-k8s-argocd/
└── datastore-deploy/
    └── datastore-deploy.yaml
🔔 Slack Notifications

✔ Success
✔ Failure
✔ Build Status

🧠 Key Learnings
CI/CD pipeline automation
GitOps deployment strategy
Docker & Kubernetes workflow
Debugging real-world DevOps issues
🚀 Future Enhancements
Blue-Green Deployment
Canary Deployment
Helm Charts
Terraform Infrastructure
👨‍💻 Author

Rashmi Ranjan Panigrahy


---

# 🖼️ 2. ARCHITECTURE DIAGRAM (VISUAL)


::contentReference[oaicite:0]{index=0}


---

## 🧠 How to Explain This Diagram (Interview)

👉 Say:

- Developer pushes code to GitHub  
- Jenkins triggers CI pipeline  
- Performs build, test, SonarQube, Trivy  
- Builds Docker image and pushes  
- Updates GitOps repo  
- ArgoCD detects change and deploys  
- Slack sends notification  
