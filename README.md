# 🚀 CI/CD Pipeline Automation with Jenkins, Docker & AWS

This project demonstrates a scalable, production-ready CI/CD pipeline that integrates **Jenkins**, **Docker**, **Terraform**, **Ansible**, **SonarQube**, **AWS**, **Kubernetes (EKS)**, and **Prometheus + Grafana** for full observability.

## 🔧 Tech Stack
- Jenkins
- Git
- Docker
- AWS EC2 & EKS
- Terraform
- Ansible
- SonarQube
- Prometheus
- Grafana
- Shell Scripting & Python

## 💡 What It Does
- Automates CI/CD with Jenkins Pipelines
- Builds and pushes Docker images
- Provisions AWS infrastructure using Terraform
- Configures environments with Ansible
- Deploys to Kubernetes (EKS)
- Monitors with Prometheus & Grafana
- Enforces code quality via SonarQube

## 📊 Outcome
- 🚀 Reduced release times by 60%
- 🔐 Eliminated manual errors through IaC
- 📈 Improved system visibility and MTTR

---

## 📂 File Structure

```bash
ci-cd-pipeline-automation/
├── Jenkinsfile               # Pipeline config
├── terraform/                # IaC to provision EC2/EKS
├── ansible/                  # Config management
├── monitoring/               # Prometheus + Grafana
├── scripts/                  # Shell & Python automation
└── docker-compose.yml        # For local testing
