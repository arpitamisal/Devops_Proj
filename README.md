# 🚀 End-to-End CI/CD & GitOps Pipeline on Kubernetes

This project demonstrates how to build a fully automated **CI/CD and GitOps pipeline** from the ground up using modern DevOps tools. The pipeline automatically builds, packages, and deploys a simple Python Flask application to Kubernetes whenever changes are pushed to GitHub.

## 📌 Overview

The workflow follows these steps:

1. **Provision Kubernetes** using Minikube with Terraform.
2. **Containerize** a Python Flask application using Docker.
3. **Package** the application using a reusable Helm chart.
4. **Automate CI** with GitHub Actions to:
   - Build the Docker image
   - Push it to Docker Hub
   - Update the Helm chart with the latest image tag
5. **Automate CD** using ArgoCD, which continuously monitors the Git repository and synchronizes the Kubernetes cluster with the desired state.

This project showcases how CI/CD pipelines and GitOps work together to create reliable, automated application deployments on Kubernetes.

---

## 🏗️ Architecture

```
Developer
     │
     ▼
 GitHub Repository
     │
     ▼
 GitHub Actions (CI)
 ├── Build Docker Image
 ├── Push to Docker Hub
 └── Update Helm Chart
     │
     ▼
 Git Repository
     │
     ▼
      ArgoCD
     │
     ▼
 Kubernetes (Minikube)
     │
     ▼
 Flask Application
```

---

## 🛠️ Tech Stack

- Python (Flask)
- Docker
- Kubernetes (Minikube)
- Terraform
- Helm
- GitHub Actions
- ArgoCD
- Git & GitHub

---

## 📂 Project Structure

```
.
├── app.py
├── Dockerfile
├── helm-chart/
├── .github/workflows/
├── terraform/
├── argocd-app.yaml
└── README.md
```

---

## 🚀 Getting Started

### Clone the repository

```bash
git clone https://github.com/arpitamisal/Devops_Proj.git
cd Devops_Proj
```

### Build the Docker image

```bash
docker build -t your-dockerhub-username/devops-proj .
```

### Run locally

```bash
docker run -p 8080:8080 your-dockerhub-username/devops-proj
```

Visit:

```
http://localhost:8080
```

---

## ⚙️ CI/CD Workflow

Every push to the repository automatically triggers:

- Docker image build
- Image push to Docker Hub
- Helm values update with the latest image tag
- Git commit of updated deployment manifests

ArgoCD detects the repository changes and automatically deploys them to the Kubernetes cluster.

---

## 🔄 GitOps Workflow

ArgoCD continuously watches the Git repository and ensures the Kubernetes cluster always matches the desired state stored in Git.

Features include:

- Automatic synchronization
- Self-healing
- Automatic pruning of removed resources

---

## 📦 Sample Application

The application is a lightweight Flask service that returns the current server time.

Example response:

```
The current time of the day:
2026-06-25 18:42:10
```

---

## 📖 Production Considerations

While this project demonstrates the core concepts of CI/CD and GitOps, production environments typically require additional capabilities, including:

- Unit testing
- Integration testing
- End-to-end testing
- Security and vulnerability scanning
- Secrets management
- Multi-environment deployments (Dev, QA, Staging, Production)
- Monitoring and alerting
- High availability and disaster recovery
- Rollback strategies and progressive deployments (Blue-Green/Canary)

---

## 🎯 Learning Outcomes

Through this project, I gained hands-on experience with:

- Infrastructure as Code using Terraform
- Docker containerization
- Kubernetes deployments
- Helm chart packaging
- GitHub Actions CI pipelines
- GitOps using ArgoCD
- Automated Kubernetes application delivery

