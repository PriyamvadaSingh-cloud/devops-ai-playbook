#  DevOps AI Playbook – Kubernetes GitOps Deployment on AWS

![AWS](https://img.shields.io/badge/AWS-EKS-orange)
![Docker](https://img.shields.io/badge/Docker-Containers-blue)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestration-326CE5)
![ArgoCD](https://img.shields.io/badge/ArgoCD-GitOps-red)
![GitHub Actions](https://img.shields.io/badge/GitHub-Actions-black)

---

#  Project Overview

This repository demonstrates an end-to-end DevOps workflow for deploying a microservices application on Amazon EKS using GitOps with ArgoCD.

The project covers containerization, Kubernetes deployments, CI automation, image management using Amazon ECR, and continuous deployment through GitOps practices.

The deployment was configured in my own AWS environment and includes troubleshooting and debugging of real deployment issues.

---

# Tech Stack

| Category | Technology |
|----------|------------|
| Cloud | AWS |
| Containerization | Docker |
| Registry | Amazon ECR |
| Orchestration | Kubernetes (Amazon EKS) |
| GitOps | ArgoCD |
| CI | GitHub Actions |
| Version Control | Git & GitHub |

---

#  Architecture

```text
                    Developer
                        │
                        │ git push
                        ▼
                GitHub Repository
                        │
                        ▼
               GitHub Actions CI
                        │
         Build Docker Images
                        │
                        ▼
                  Amazon ECR
                        │
                        ▼
                  ArgoCD Watches
                        │
                        ▼
               Kubernetes (EKS)
                        │
         ┌──────────────┼──────────────┐
         ▼              ▼              ▼
     Frontend      API Gateway     Microservices
                        │
                        ▼
                  PostgreSQL Database
```

---

#  Repository Structure

```text
devops-ai-playbook
│
├── .github/
│   └── workflows/
│       └── ci.yml
│
├── gitops/
│   ├── argo-cd.yml
│   ├── kustomization.yml
│   └── k8s/
│
├── projects/
│   └── boutique-microservices/
│
└── README.md
```

---

#  Deployment Workflow

```text
Developer
      │
      ▼
Git Push
      │
      ▼
GitHub Actions
      │
      ▼
Docker Build
      │
      ▼
Push Images to Amazon ECR
      │
      ▼
ArgoCD Detects Changes
      │
      ▼
Sync Kubernetes Manifests
      │
      ▼
Deploy to Amazon EKS
```

---

#  AWS Services Used

- Amazon EC2
- Amazon EKS
- Amazon ECR
- IAM
- CloudShell
- kubectl
- AWS CLI

---

#  Features

- Dockerized Microservices
- Kubernetes Deployments
- Amazon EKS Cluster
- GitOps Deployment using ArgoCD
- GitHub Actions CI Pipeline
- Amazon ECR Image Registry
- Kubernetes Services & Namespaces
- Automatic Application Synchronization

---

#  Major Issues Solved

## InvalidImageName

Cause:
Docker image references contained placeholder values.

Solution:
Updated Kubernetes manifests with correct Amazon ECR image URLs.

---

## ImagePullBackOff

Cause:
Images were not available in ECR.

Solution:
Built Docker images and pushed them to Amazon ECR.

---

## ArgoCD Sync Issues

Cause:
GitOps manifests and image references were incorrect.

Solution:
Updated manifests and synchronized ArgoCD.

---

## Kubernetes Pod Failures

Cause:
Deployment configuration issues.

Solution:
Validated manifests, reapplied resources, and verified pod health.

---

# 📸 Screenshots

## Amazon EKS

(Add Screenshot)

---

## Amazon ECR

(Add Screenshot)

---

## GitHub Actions

(Add Screenshot)

---

## ArgoCD Dashboard

(Add Screenshot)

---

## Kubernetes Pods

(Add Screenshot)

---

#  Key Learnings

- Docker Image Lifecycle
- Kubernetes Deployments
- GitOps Workflow
- Continuous Integration
- Amazon EKS Administration
- ArgoCD Synchronization
- Kubernetes Troubleshooting

---

#  My Contributions

- Configured Amazon EKS Cluster
- Connected kubectl to EKS
- Built Docker Images
- Pushed Images to Amazon ECR
- Configured GitHub Actions
- Configured ArgoCD
- Updated Kubernetes manifests
- Fixed deployment failures
- Debugged image pull issues
- Verified successful deployments

---

#  Acknowledgement

This project is based on a DevOps learning repository. I used it as a learning project and independently configured, deployed, customized, and debugged the application in my own AWS environment.



#  Author

**Priyamvada Singh**

GitHub:
https://github.com/PriyamvadaSingh-cloud
