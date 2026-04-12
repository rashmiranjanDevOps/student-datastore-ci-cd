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
