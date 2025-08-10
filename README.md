# Deploy-PythonApp-Docker-Terraform
🚀 Deploying Python Application using Docker & Terraform

📖 Project Overview

In this project, I deployed a Python web application in a containerized environment using Docker and automated the infrastructure provisioning with Terraform.

The workflow implemented:

Containerized the Python application with Docker

Pushed the Docker image to Docker Hub repository

Provisioned an AWS EC2 instance using Terraform

Pulled and ran the Docker container automatically on the EC2 instance


This setup follows Infrastructure as Code (IaC) principles to ensure deployment is repeatable, scalable, and easy to maintain.


---

🛠 Technology Stack

Tool	Purpose

Python 3.x	Application codebase
Docker	Containerizing the application
Terraform	Provisioning cloud infrastructure
AWS EC2	Hosting environment
Docker Hub	Storing Docker images



---

📂 Project Structure

├── app/
│   ├── main.py               # Python application entry point
│   ├── requirements.txt      # Dependencies
├── Dockerfile                # Docker image configuration
├── terraform/
│   ├── main.tf               # Terraform configuration file
│   ├── variables.tf          # Variables for Terraform
│   ├── outputs.tf            # Outputs after provisioning
│   ├── provision.sh          # Script to run the container in EC2
├── README.md                 # Project documentation


---

⚙️ Prerequisites

Before running the project, ensure:

Python 3.x installed locally

Docker installed and running

Terraform installed (v1.x or above)

AWS account configured with CLI access

Docker Hub account

---

📦 Step 1 — Build & Push Docker Image

# Navigate to application directory
cd app

# Install dependencies locally (optional)
pip install -r requirements.txt

# Build Docker image
docker build -t <dockerhub-username>/python-app:latest .

# Login to Docker Hub
docker login

# Push the image to Docker Hub repository
docker push <dockerhub-username>/python-app:latest


---

🌍 Step 2 — Deploy with Terraform

# Navigate to Terraform configuration
cd terraform

# Initialize Terraform
terraform init

# Validate configuration
terraform validate

# Review plan
terraform plan

# Apply configuration
terraform apply -auto-approve

Terraform Actions:

Creates an AWS EC2 instance

Installs Docker on it

Pulls the Docker image from Docker Hub

Runs the Python application container



---

🔍 Step 3 — Verify Deployment

Retrieve Public IP from Terraform output

Access in browser:


http://<EC2-PUBLIC-IP>:<PORT>


---

🧹 Step 4 — Destroy Infrastructure

To avoid charges, clean up resources:

terraform destroy -auto-approve


---


---

📌 Key Learning

Docker simplifies environment setup

Terraform enables scalable cloud provisioning

AWS EC2 provides reliable hosting

Combining Docker & Terraform automates deployment workflows
