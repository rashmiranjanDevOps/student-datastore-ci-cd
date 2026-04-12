# 🚀 CI/CD Pipeline with GitOps

---

## 📌 Overview

This project implements a simple **end-to-end CI/CD pipeline** using Jenkins and GitOps.

### 🔧 What it automates:

- 🔨 Build and Test  
- 🔍 Code Quality Check (SonarQube)  
- 🔐 Security Scan (Trivy)  
- 🐳 Docker Image Build & Push  
- 🚀 Deployment using ArgoCD  
- 🔔 Slack Notifications  

---

### 🧱 Architecture

GitHub
   ↓
Jenkins (CI)
   ↓
Build → Test → SonarQube → Trivy
   ↓
Docker Image Push (DockerHub)
   ↓
GitOps Repo Update
   ↓
ArgoCD Deployment
   ↓
Kubernetes Cluster
   ↓
Slack Notification 🚀


---

### 🛠️ Tools Used

| Tool | Purpose |
|------|--------|
| ⚙️ Jenkins | CI/CD Automation |
| 🐳 Docker | Containerization |
| ☸️ Kubernetes | Orchestration |
| 🚀 ArgoCD | GitOps Deployment |
| 🔍 SonarQube | Code Quality |
| 🔐 Trivy | Security Scan |
| ☁️ AWS EC2 | Infrastructure |
| 💬 Slack | Notifications |

### 🔄 Pipeline Flow

1️⃣ Code pushed to GitHub  
2️⃣ Jenkins pipeline starts  
3️⃣ Build and test executed  
4️⃣ SonarQube checks code quality  
5️⃣ Docker image is built and scanned  
6️⃣ Image pushed to DockerHub  
7️⃣ Kubernetes YAML updated  
8️⃣ ArgoCD deploys application  
9️⃣ Slack sends notification

### 🔢 Versioning

APP_VERSION = v${BUILD_NUMBER}

📌 Example
Build #1 → v1
Build #2 → v2


---

### 🔐 Credentials

Stored securely in Jenkins:

- 🔑 DockerHub credentials  
- 🔑 GitHub token  
- 🔑 SonarQube token  
- 🔑 Slack token

### 📂 Project Structure

```text
student-datastore-ci-cd/
├── Jenkinsfile
├── Dockerfile
├── pom.xml
└── src/

datastore-k8s-argocd/
└── datastore-deploy/
    └── datastore-deploy.yaml

### ✅ Result

✔ Automated CI/CD pipeline  
✔ GitOps-based deployment  
✔ Secure and scalable workflow  
