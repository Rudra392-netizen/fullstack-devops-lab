 <div align="center">

# 🚀 Production-Ready Full Stack DevOps CI/CD Pipeline

### Automating Code Quality • Containerization • Security • Kubernetes Deployment

<p align="center">

<img src="https://img.shields.io/badge/CI/CD-Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white"/>

<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"/>

<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white"/>

<img src="https://img.shields.io/badge/SonarQube-4E9BCD?style=for-the-badge&logo=sonarqube&logoColor=white"/>

<img src="https://img.shields.io/badge/Trivy-1904DA?style=for-the-badge"/>

<img src="https://img.shields.io/badge/DockerHub-0db7ed?style=for-the-badge&logo=docker&logoColor=white"/>

<img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white"/>

<img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black"/>

<img src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white"/>

</p>

</div>

---

# 📖 About The Project

Modern software delivery is much more than writing code. Applications must be tested, analyzed for code quality, scanned for vulnerabilities, containerized, deployed automatically, and updated without downtime.

I built this project to understand how these technologies work together in a real DevOps workflow instead of learning each tool independently.

In this project, I integrated **Jenkins**, **Docker**, **SonarQube**, **Trivy**, **DockerHub**, and **Kubernetes** into a single automated CI/CD pipeline.

Whenever changes are pushed to GitHub, Jenkins automatically performs code checkout, static code analysis, Docker image creation, vulnerability scanning, pushes images to DockerHub, deploys the application on Kubernetes, and sends email notifications after the pipeline execution.

This project helped me gain practical experience with containerization, CI/CD automation, Kubernetes deployments, deployment strategies, DevSecOps fundamentals, and production-style software delivery workflows.

---

# 🎯 Project Objectives

✔ Learn how a complete CI/CD pipeline works

✔ Automate application deployment

✔ Improve code quality using SonarQube

✔ Scan Docker images using Trivy

✔ Deploy applications on Kubernetes

✔ Practice Rolling Update and Rollback strategies

✔ Build a production-style DevOps workflow

---

# 🚧 Project Status

> **Current Version : v1.0**

### ✅ Completed

- Jenkins Declarative Pipeline
- Jenkins Shared Library
- Docker Image Build
- DockerHub Integration
- SonarQube Integration
- Trivy Image Scanning
- Kubernetes Deployment
- Rolling Update Strategy
- Rollback Strategy
- Email Notifications
- Local Kubernetes Deployment using Kind

### 🚀 Planned Enhancements

- Terraform Infrastructure Provisioning
- Amazon EKS Deployment
- Amazon ECR Integration
- Helm Charts
- Prometheus Monitoring
- Grafana Dashboards
- Loki Logging
- Argo CD (GitOps)
- OpenTelemetry
- Blue-Green Deployment
- Canary Deployment
- Horizontal Pod Autoscaler (HPA)

---

# 🏗 Project Architecture

```text
                Developer

                    │

                    ▼

               Push Code

                    │

                    ▼

                GitHub Repository

                    │

                    ▼

             Jenkins Pipeline

                    │

     ┌──────────────┼──────────────┐

     ▼                              ▼

 SonarQube                  Docker Build

     │                              │

     ▼                              ▼

Quality Gate                 Trivy Scan

              │

              ▼

        Push to DockerHub

              │

              ▼

      Kubernetes (Kind)

              │

      Rolling Update

              │

        Rollback (If Needed)

              │

              ▼

     Email Notification
```

---

# ⚙ Technology Stack

| Category | Technologies |
|----------|--------------|
| Programming | JavaScript |
| Frontend | React |
| Backend | Node.js |
| Database | MongoDB |
| Version Control | Git, GitHub |
| CI/CD | Jenkins |
| Containerization | Docker |
| Image Registry | DockerHub |
| Code Quality | SonarQube |
| Security Scanning | Trivy |
| Orchestration | Kubernetes (Kind) |

---

# 📂 Repository Structure

```text
fullstack-devops-lab

│

├── Application-Code/

│ ├── frontend/

│ ├── backend/

│ └── database/

│

├── K8s/

│ ├── frontend/

│ ├── backend/

│ ├── mongodb/

│ ├── ingress/

│ ├── config/

│ └── namespace/

│

├── Jenkinsfile

├── README.md

├── trivy.report.txt

└── .gitignore
```

---

## PART 2:-
---

# ⚙️ CI/CD Pipeline

## 📌 Overview

The CI/CD pipeline is the core of this project. Instead of manually building, testing, scanning, and deploying the application every time changes are made, I automated the complete workflow using **Jenkins**.

Whenever new code is pushed to the GitHub repository, Jenkins automatically starts the pipeline and performs a series of predefined stages. This helps reduce manual effort, improves deployment consistency, and ensures every build follows the same process.

The pipeline also integrates code quality analysis, container security scanning, Docker image publishing, Kubernetes deployment, and email notifications.

---

# 🔄 CI/CD Workflow

```text
Developer
    │
    ▼
Push Code to GitHub
    │
    ▼
Jenkins Pipeline Triggered
    │
    ▼
Checkout Source Code
    │
    ▼
Install Dependencies
    │
    ▼
SonarQube Static Code Analysis
    │
    ▼
Quality Verification
    │
    ▼
Build Docker Images
    │
    ▼
Trivy Security Scan
    │
    ▼
Push Images to DockerHub
    │
    ▼
Deploy to Kubernetes (Kind)
    │
    ▼
Rolling Update
    │
    ▼
Email Notification
```

---

# 🏗️ Jenkins Declarative Pipeline

The complete automation workflow is implemented using a **Jenkins Declarative Pipeline**.

The Jenkinsfile defines every stage required to build, analyze, package, and deploy the application automatically.

Instead of executing multiple commands manually, Jenkins performs every task in the correct order whenever the pipeline runs.

---

<details>

<summary><b>📌 Pipeline Stages</b></summary>

### ✅ Stage 1 — Checkout Source Code

The pipeline begins by downloading the latest source code from GitHub.

This ensures Jenkins always works with the latest version of the project.

---

### ✅ Stage 2 — Install Project Dependencies

The required project dependencies are installed before building the application.

This prepares the application for code analysis and Docker image creation.

---

### ✅ Stage 3 — SonarQube Analysis

The source code is analyzed using SonarQube.

This stage checks for:

- Code Smells
- Bugs
- Maintainability Issues
- Security Hotspots
- Vulnerabilities

Performing static code analysis before deployment helps identify problems early in the development lifecycle.

---

### ✅ Stage 4 — Build Docker Images

After successful code analysis, Docker images are built for the application.

Containerization ensures the application runs consistently across different environments.

---

### ✅ Stage 5 — Trivy Image Scan

Before deployment, Docker images are scanned using Trivy.

This security scan helps detect known vulnerabilities inside container images.

Running image scans before deployment is an important DevSecOps practice.

---

### ✅ Stage 6 — Push Docker Images

After the security scan completes successfully, Docker images are pushed to DockerHub.

These images become available for Kubernetes deployments.

---

### ✅ Stage 7 — Kubernetes Deployment

The updated Docker images are deployed to the Kubernetes cluster.

Kubernetes automatically replaces old containers with new ones while keeping the application available.

---

### ✅ Stage 8 — Email Notification

Once the pipeline finishes, Jenkins sends an email notification indicating whether the pipeline execution was successful or failed.

This helps monitor pipeline executions without manually checking the Jenkins dashboard.

</details>

---

# 📚 Jenkins Shared Library

To improve pipeline organization and code reusability, I integrated a **Jenkins Shared Library** into this project.

Instead of writing all pipeline logic directly inside the Jenkinsfile, reusable functions are stored in the shared library and called whenever required.

This approach keeps the Jenkinsfile cleaner, easier to maintain, and allows common pipeline logic to be reused across multiple projects.

### Benefits

- Cleaner Jenkinsfile
- Better code organization
- Reusable pipeline functions
- Easier maintenance
- Follows DevOps best practices

---

# 🔍 SonarQube Integration

Code quality is an important part of any CI/CD pipeline.

I integrated SonarQube with Jenkins so that every pipeline execution performs automated static code analysis before building Docker images.

The purpose of this integration is to identify potential issues early in the development process rather than after deployment.

### SonarQube helps identify:

- Code Smells
- Bugs
- Security Issues
- Vulnerabilities
- Maintainability Problems
---

# 🛡️ Trivy Security Scanning

After building Docker images, the pipeline performs container image security scanning using Trivy.

Scanning Docker images before deployment helps identify known vulnerabilities inside the container image.

This improves the security of the deployment process and introduces basic DevSecOps practices into the CI/CD pipeline.

### Trivy Scan Covers

- Operating System Packages
- Known CVEs
- Dependency Vulnerabilities
- Security Risks inside Docker Images

> 📸 **Screenshot Placeholder**

<img width="1777" height="836" alt="Screenshot 2026-04-25 164400" src="https://github.com/user-attachments/assets/0c53e71f-3555-449e-823f-5036aebf1c5e" />


---

# 🐳 Docker Image Build

Docker is used to package the application into portable container images.

Containerization ensures the application behaves consistently regardless of the environment where it is deployed.

Each pipeline execution automatically builds fresh Docker images using the latest source code.

---

# 📦 DockerHub Integration

Once Docker images are successfully built and scanned, Jenkins automatically pushes them to DockerHub.

This allows Kubernetes to pull the latest application images during deployment.

Automating image publishing removes manual intervention and keeps deployments consistent.

> 📸 **Screenshot Placeholder**
>
> Add your DockerHub repository screenshot showing the latest image.

---

# 💡 What I Learned

While building this CI/CD pipeline, I learned how different DevOps tools work together as a complete software delivery workflow.

Instead of learning Jenkins, Docker, SonarQube, Trivy, and Kubernetes separately, I understood how each tool contributes to automating modern application deployment.

This project also helped me understand the importance of code quality, container security, deployment automation, and reusable pipeline design.

---

## part 3

---

# ☸️ Kubernetes Deployment

## 📖 Overview

After successfully building and publishing the Docker images, the final step of the CI/CD pipeline is deploying the application to Kubernetes.

For this project, I used **Kind (Kubernetes in Docker)** as my local Kubernetes cluster to understand how container orchestration works before moving to a cloud environment.

Instead of manually managing containers, Kubernetes automatically handles application deployment, scaling, networking, and updates.

This project helped me understand how multiple containers communicate with each other while remaining highly available.

---

# 🏗️ Kubernetes Architecture

```text
                    Kubernetes Cluster (Kind)

                          Namespace
                              │
    ┌─────────────────────────┼─────────────────────────┐
    │                         │                         │
    ▼                         ▼                         ▼
Frontend Deployment     Backend Deployment      MongoDB Deployment
    │                         │                         │
    ▼                         ▼                         ▼
Frontend Service       Backend Service        MongoDB Service
          \                  │                 /
           \                 │                /
            └────────────────┼───────────────┘
                             │
                          Ingress
                             │
                             ▼
                          End User
```

---

# 📂 Kubernetes Resources

The Kubernetes manifests are organized into separate directories to keep the project modular and easy to maintain.

```text
K8s/

├── namespace/
│
├── frontend/
│
├── backend/
│
├── mongodb/
│
├── ingress/
│
└── config/
```

---

# 📦 Namespace

A dedicated namespace is created to isolate the application resources from other workloads running inside the cluster.

Using namespaces improves organization and simplifies resource management.

### Benefits

- Better resource organization
- Easy management
- Isolation between applications
- Cleaner Kubernetes environment

---

# 🚀 Frontend Deployment

The frontend application is deployed using a Kubernetes Deployment resource.

Kubernetes ensures that the desired number of frontend Pods remain running at all times.

If a Pod crashes, Kubernetes automatically creates a new one.

---

# ⚙️ Backend Deployment

The backend application is deployed separately from the frontend.

This separation allows independent updates, scaling, and maintenance without affecting other components.

---

# 🍃 MongoDB Deployment

MongoDB acts as the database layer of the application.

The backend communicates with MongoDB through an internal Kubernetes Service.

Separating the database from the application improves modularity and reflects a common production architecture.

---

# 🌐 Kubernetes Services

Each application component is exposed internally using Kubernetes Services.

Services provide a stable network endpoint for communication between Pods, even when Pods are recreated.

The project includes services for:

- Frontend
- Backend
- MongoDB

---

# 🌍 Ingress

Ingress is used to expose the application through a single entry point.

Instead of exposing every service individually, incoming traffic is routed to the appropriate backend service.

This provides a cleaner and more scalable networking approach.

---

# 🔄 Rolling Update Strategy

One of the most important deployment strategies I implemented in this project is the **Rolling Update**.

Whenever a new application version is deployed, Kubernetes gradually replaces the old Pods with new Pods.

This allows the application to remain available while the deployment is happening.

### Advantages

✅ Zero or minimal downtime

✅ Smooth application updates

✅ Safer deployments

✅ Automatic Pod replacement

---

### Rolling Update Workflow

```text
Version 1 Running

Pod 1

Pod 2

Pod 3

        │

Deploy New Version

        │

Create New Pod

        │

Terminate One Old Pod

        │

Repeat Process

        │

Version 2 Running Successfully
```

---

# ⏪ Rollback Strategy

During application deployment, unexpected issues can sometimes occur.

To recover quickly, I also implemented Kubernetes Rollback.

If a newly deployed version causes problems, Kubernetes can restore the previous stable version with a rollback operation.

This minimizes downtime and helps maintain application availability.

---

### Rollback Workflow

```text
Version 1

      │

Deploy Version 2

      │

Issue Detected

      │

kubectl rollout undo

      │

Application Restored

      │

Version 1 Running Again
```

---

# 📧 Email Notifications

To improve pipeline monitoring, Jenkins automatically sends email notifications after each pipeline execution.

These notifications help quickly identify whether the deployment completed successfully or failed.

Instead of manually checking the Jenkins dashboard, the pipeline status is delivered directly through email.

---

## 📸 Project Screenshots

The following screenshots demonstrate different stages of the project.

## 🚀 Jenkins Pipeline

<img width="1895" height="726" alt="Screenshot 2026-04-25 162224" src="https://github.com/user-attachments/assets/a377dbc8-ef66-40ba-aaae-5e7ea6eae0cb" />

<p align="center"> <em>Successful Jenkins CI/CD pipeline execution showing source code checkout, dependency installation, SonarQube analysis, Quality Gate verification, Docker image build, Trivy scan, DockerHub push, Kubernetes deployment, and email notification stages.</em> </p>

## 📚 Jenkins Shared Library

<img width="1492" height="767" alt="Screenshot 2026-06-26 213903" src="https://github.com/user-attachments/assets/3feab1ec-9eb3-4f07-b667-111e0c25ffe3" />


<p align="center"> <em>Declarative Jenkins Pipeline integrated with a Shared Library to improve reusability, maintainability, and pipeline organization.</em> </p>

## 🔍 SonarQube Dashboard

<img width="1919" height="929" alt="Screenshot 2026-04-25 162242" src="https://github.com/user-attachments/assets/f8416c0f-b7d9-4bb4-8830-3144d4d1e4fa" />


<p align="center"> <em>SonarQube analysis dashboard showing a successful Quality Gate with maintainability, reliability, and security checks.</em> </p>

## 📦 DockerHub Repository

<img width="1882" height="701" alt="Screenshot 2026-06-26 200010" src="https://github.com/user-attachments/assets/9e43b10c-2792-4c7b-887e-4441779a9496" />


<p align="center"> <em>DockerHub repositories containing frontend and backend application images automatically published by the Jenkins pipeline.</em> </p>

## ☸️ Kubernetes Pods & Services

<img width="813" height="528" alt="Screenshot 2026-04-25 162504" src="https://github.com/user-attachments/assets/ee6473d6-b418-41f0-a572-873d429568e3" />


<p align="center"> <em>Running Kubernetes Pods and Services for the frontend, backend, and MongoDB components inside the Kind cluster.</em> </p>

## Rolling Update Demo

<img width="1093" height="262" alt="Screenshot 2026-06-26 202204" src="https://github.com/user-attachments/assets/334b28d6-bacd-4b4e-8fdb-7bc19e1c0271" />

---

## Rollback Demo

<img width="1105" height="86" alt="Screenshot 2026-06-26 202548" src="https://github.com/user-attachments/assets/424463c4-13f2-4df4-8041-4e89315dfb6f" />


---

## 📧 Successful Email Notification

<img width="1517" height="717" alt="Screenshot 2026-06-26 200152" src="https://github.com/user-attachments/assets/a60a68cd-1afe-4f5b-8227-de36122676c8" />


<p align="center"> <em>Automated email notification sent by Jenkins after successful pipeline execution and deployment.</em> </p>

# 🔍 Useful Kubernetes Commands

### View Pods

```bash
kubectl get pods
```

### View Services

```bash
kubectl get svc
```

### View Deployments

```bash
kubectl get deployments
```

### Describe Pod

```bash
kubectl describe pod <pod-name>
```

### Check Rollout Status

```bash
kubectl rollout status deployment/<deployment-name>
```

### Rollback Deployment

```bash
kubectl rollout undo deployment/<deployment-name>
```

---

# 💡 What I Learned

This project helped me understand how Kubernetes manages containerized applications in a practical environment.

By deploying a three-tier application, I learned how Deployments, Services, Namespaces, Ingress, and rollout strategies work together to provide reliable application delivery.

Implementing Rolling Updates and Rollbacks also helped me understand how Kubernetes supports safer deployments with minimal downtime.

---


## PART 4 :-

---

# 🚀 Getting Started

This section explains how to set up and run the project in your local environment.

## 📋 Prerequisites

Before running this project, make sure the following tools are installed:

| Tool | Purpose |
|------|----------|
| Git | Clone the repository |
| Docker | Build and run container images |
| DockerHub Account | Store Docker images |
| Jenkins | CI/CD Automation |
| SonarQube | Static Code Analysis |
| Trivy | Docker Image Vulnerability Scanning |
| Kind | Local Kubernetes Cluster |
| kubectl | Kubernetes CLI |
| Node.js | Application Dependencies |

---

# 📥 Clone the Repository

```bash
git clone https://github.com/Rudra392-netizen/fullstack-devops-lab.git

cd fullstack-devops-lab
```

---

# 🐳 Build Docker Images

Build the required Docker images.

```bash
docker build -t frontend .

docker build -t backend .
```

---

# ☸️ Create Kind Cluster

```bash
kind create cluster --name devops-cluster
```

Verify the cluster:

```bash
kubectl get nodes
```

---

# 🚀 Deploy the Application

Deploy all Kubernetes manifests.

```bash
kubectl apply -f K8s/
```

Verify the deployment.

```bash
kubectl get pods

kubectl get svc

kubectl get ingress
```

---

# 🔄 Trigger the CI/CD Pipeline

Whenever code is pushed to GitHub:

- Jenkins automatically starts the pipeline.
- Performs static code analysis using SonarQube.
- Builds Docker images.
- Scans Docker images using Trivy.
- Pushes images to DockerHub.
- Deploys the latest version to Kubernetes.
- Sends an email notification after completion.

No manual deployment steps are required once the pipeline is configured.

---

# ⚠️ Challenges I Faced

Building this project was not just about using DevOps tools—it was also about learning how to troubleshoot and solve real-world issues.

Some of the challenges I encountered included:

- Configuring Jenkins with the required plugins.
- Integrating SonarQube into the CI/CD pipeline.
- Understanding Docker image creation and versioning.
- Troubleshooting Kubernetes deployment issues.
- Configuring Kubernetes networking using Services and Ingress.
- Learning Rolling Updates and Rollback strategies.
- Managing DockerHub authentication inside Jenkins.
- Configuring email notifications for pipeline execution.

Each challenge helped me better understand how DevOps tools work together in real deployment environments.

---

# 📚 Key Learnings

This project significantly improved my understanding of modern DevOps practices.

Through this project, I learned:

- Building an end-to-end CI/CD pipeline.
- Automating software delivery using Jenkins.
- Performing static code analysis with SonarQube.
- Scanning Docker images using Trivy.
- Building and managing Docker containers.
- Publishing container images to DockerHub.
- Deploying applications on Kubernetes.
- Understanding Deployments, Services, Namespaces, and Ingress.
- Performing Rolling Updates and Rollbacks.
- Automating deployment notifications.
- Organizing Jenkins pipelines using Shared Libraries.

This project also taught me how different DevOps tools integrate to automate software delivery from source code to a running Kubernetes application.

---

# 🛣️ Future Enhancements

This project is actively being improved. The following features are planned for future versions:

- ☁️ Deploy the application on Amazon EKS.
- 🏗️ Provision infrastructure using Terraform.
- 📦 Store container images in Amazon ECR.
- 📊 Integrate Prometheus for monitoring.
- 📈 Create Grafana dashboards for visualization.
- 📜 Add centralized logging using Loki.
- 🚀 Implement GitOps using Argo CD.
- 📦 Package Kubernetes resources using Helm Charts.
- 🔒 Integrate additional DevSecOps tools.
- 📡 Add OpenTelemetry for distributed tracing.
- 🔵 Implement Blue-Green Deployment strategy.
- 🟢 Implement Canary Deployment strategy.
- 📈 Configure Horizontal Pod Autoscaler (HPA).
- 🤖 Explore AIOps integrations for intelligent monitoring.

These enhancements will help evolve the project into a more production-ready DevOps platform.

---

# 📂 Project Highlights

✔️ End-to-End CI/CD Pipeline

✔️ Jenkins Shared Library

✔️ SonarQube Integration

✔️ Trivy Security Scanning

✔️ Docker & DockerHub Integration

✔️ Kubernetes Deployment

✔️ Rolling Update Strategy

✔️ Rollback Strategy

✔️ Email Notifications

✔️ Local Kubernetes Cluster using Kind

---

# 🤝 Contributing

Suggestions and improvements are always welcome.

If you would like to contribute:

1. Fork the repository.
2. Create a new feature branch.
3. Commit your changes.
4. Open a Pull Request.

Constructive feedback is always appreciated as it helps improve the project.

---

# 📜 License

This project is licensed under the **MIT License**.

You are free to use, modify, and distribute this project for educational and learning purposes.

---

# 👨‍💻 About Me

Hi, I'm **Rudra Pratap Singh**.

I am a B.Tech Computer Science student with a strong interest in **DevOps, Cloud Computing, Kubernetes, Infrastructure Automation, and CI/CD**.

I enjoy building hands-on projects that help me understand how modern software is developed, automated, secured, and deployed in production environments.

This repository is part of my continuous learning journey as I work toward becoming a DevOps and Cloud Engineer.

---

# 📬 Connect With Me

<p align="center">

<a href="https://github.com/Rudra392-netizen">
<img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github"/>
</a>

<a href="https://www.linkedin.com/in/rudra-pratap-singh-1b451b27a/">
<img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin"/>
</a>

<a href="mailto:rpsingh98188@gmail.com">
<img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white"/>
</a>

</p>

---

<div align="center">

## ⭐ Thank You for Visiting My Repository!

If you found this project useful or interesting, consider giving it a ⭐ on GitHub.

Your support motivates me to continue learning, building, and sharing more DevOps and Cloud projects.

🚀 Happy Learning!

</div>

