🚀 Task-2: DevSecOps & GitOps Delivery on Kubernetes (EKS)
📌 Overview
This project enhances the CI/CD pipeline by adding:

Security Scans → tfsec (IaC), Trivy (containers)

Secret Management → Kubernetes Sealed Secrets

GitOps → Continuous deployment using Argo CD

EKS → Scalable Kubernetes cluster

GitHub Actions → Automated CI/CD

✅ Goal: Build a secure, automated, and scalable Kubernetes deployment pipeline.

📂 Repository Structure
task2/
├── .github/
│   └── workflows/
│       └── main.yml
├── k8s/
│   ├── deployment.yaml
│   ├── svc.yaml
│   └── ingress.yaml
├── sealed-secrets/
│   └── mysealedsecret.yaml
├── argocd/
│   └── argocd-install.yaml
└── frontend/
    ├── Dockerfile
    ├── nginx.conf
    └── src/

    ✅ Quick Run Steps (FOR MORE DETAILED STEPS FOLLOW MY PPT)
git clone https://github.com/priyanshu-t07/DevSecOps-project-2.git task2 && cd task2
docker build -t my-frontend:latest frontend/
aws ecr create-repository --repository-name my-frontend
docker tag my-frontend:latest <ECR_URI>:latest && docker push <ECR_URI>:latest
eksctl create cluster --name devops-pipeline
kubectl apply -f argocd/argocd-install.yaml
kubectl apply -f sealed-secrets/mysealedsecret.yaml
kubectl apply -f k8s/
kubectl get ingress   # Copy DNS → open in browser

🔑 Key Features
✔ tfsec → Terraform security scanning
✔ Trivy → Container image vulnerability scanning
✔ Sealed Secrets → Secure Kubernetes secrets
✔ GitHub Actions → CI/CD automation
✔ Argo CD → GitOps continuous delivery


🔧 Prerequisites
Tool	Required
AWS CLI	Configured
kubectl	Latest
eksctl	Latest
Docker	Installed
Helm	Installed
Node.js	Installed


