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

## 🧱 Architecture

```text
GitHub 
   ↓
Jenkins (CI)
   ↓
Build → Test → Scan
   ↓
Docker Image Push
   ↓
GitOps Repo Update
   ↓
ArgoCD Deployment
   ↓
Kubernetes
   ↓
Slack Notification 🚀

---

## 🛠️ Tools Used

- ⚙️ Jenkins  
- 🐳 Docker  
- ☸️ Kubernetes  
- 🚀 ArgoCD  
- 🔍 SonarQube  
- 🔐 Trivy  
- ☁️ AWS EC2  
- 💬 Slack  

---

## 🔄 Pipeline Flow

1️⃣ Code pushed to GitHub  
2️⃣ Jenkins pipeline starts  
3️⃣ Build and test executed  
4️⃣ SonarQube checks code quality  
5️⃣ Docker image is built and scanned  
6️⃣ Image pushed to DockerHub  
7️⃣ Kubernetes YAML updated  
8️⃣ ArgoCD deploys application  
9️⃣ Slack sends notification  

---

## 🔢 Versioning

```bash
APP_VERSION = v${BUILD_NUMBER}
