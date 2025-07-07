# 🛠️ Three-Tier DevOps Architecture with CI/CD, Docker, Kubernetes & Terraform on AWS

This project demonstrates a complete DevOps lifecycle for a PHP-based monolithic web application. It implements a three-tier architecture with CI/CD pipelines, containerization, Kubernetes orchestration, and infrastructure as code using Terraform on AWS.

---

## 📌 Project Objective

To automate the build, test, and deployment of a PHP web application hosted on GitHub using industry-standard DevOps tools and best practices. The project simulates a scalable, production-ready environment with high availability, automation, and maintainability.

---

## 🧱 Architecture Overview

```

GitHub (Source Control)
|
v
Jenkins (CI/CD Pipeline) ---------> Docker (Build & Push Image)
|
v
Terraform (Provision AWS Infra)
|
v
Kubernetes Cluster (Deployed App with 2 Replicas)
|
v
NodePort Service (Port: 30008)

```

---

## 🔧 Tech Stack & Tools

| Component            | Tool/Service Used          |
|----------------------|----------------------------|
| Source Code          | GitHub                     |
| CI/CD Pipeline       | Jenkins, AWS CodeBuild     |
| Containerization     | Docker, Docker Hub         |
| Orchestration        | Kubernetes (2 replicas)    |
| IaC                  | Terraform                  |
| Cloud Provider       | AWS EC2                    |
| Configuration Mgmt   | Shell Scripts (Custom)     |
| Deployment Method    | NodePort Service (30008)   |

---

## 🧪 Key Features

- ✅ Three-tier deployment: Source ➝ CI/CD ➝ Container ➝ K8s  
- ✅ Jenkins pipeline with Build, Test, Deploy stages  
- ✅ Custom Dockerfile to containerize the application  
- ✅ Kubernetes deployment with 2 replicas  
- ✅ Infrastructure provisioned using Terraform  
- ✅ Scheduled release strategy (25th of each month)  
- ✅ Git-based version control with branching workflow  
- ✅ Scalable and production-grade environment on AWS

---

## 📂 Project Structure

```

├── Dockerfile
├── Jenkinsfile
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   └── outputs.tf
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
├── scripts/
│   ├── setup-worker1.sh
│   ├── setup-worker2.sh
│   └── ...
└── README.md

````

---

## 🚀 Deployment Steps

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/devops-three-tier-app.git
cd devops-three-tier-app
````

### 2. Build & Push Docker Image

```bash
docker build -t your-dockerhub-username/php-webapp .
docker push your-dockerhub-username/php-webapp
```

### 3. Provision Infrastructure using Terraform

```bash
cd terraform
terraform init
terraform apply
```

### 4. Deploy Application on Kubernetes

```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```

### 5. Access Application

Navigate to `http://<EC2-Public-IP>:30008` in your browser.

---

## 👨‍💻 Jenkins Pipeline

The pipeline is divided into three stages:

* **Build** – Triggered by GitHub push, builds Docker image
* **Test** – Runs automated testing (optional/custom scripts)
* **Deploy** – Pushes image to DockerHub and applies K8s configs

---

## 🛡️ Security & Access

* Security Groups configured for SSH, Docker, Jenkins, and NodePort
* Environment variables managed securely in Jenkins
* IAM roles restricted to least-privilege permissions for Terraform and EC2

---

## 🧠 Learning Outcomes

* End-to-end understanding of DevOps lifecycle
* Practical experience with Docker, Kubernetes, Jenkins, Terraform
* Infrastructure provisioning using IaC on AWS
* Automating deployment pipelines and scaling applications

---

## 🔗 Project Source

* Web Application Code: [https://github.com/hshar/website](https://github.com/hshar/website)
* Your GitHub Repo: `https://github.com/Devkhuman/website`

---

## 📞 Contact

**Dev Khuman**
Email: [devjkhuman17@gmail.com](mailto:devjkhuman17@gmail.com)
LinkedIn: [https://www.linkedin.com/in/devkhuman3](https://www.linkedin.com/in/devkhuman3)
