## 🚀 CI/CD Pipeline using GitHub Actions & AWS ECR

This project uses **GitHub Actions** to implement a complete **CI/CD pipeline** with **AWS Elastic Container Registry (ECR)** and Docker.

### 🔁 Workflow Overview

The pipeline is triggered automatically on every push to the `main` branch.

### 🧪 Continuous Integration (CI)
- Checkout source code
- Run lint checks
- Execute unit tests

### 📦 Continuous Delivery (CD – Build & Push)
- Authenticate with AWS using GitHub Secrets
- Login to Amazon ECR
- Build Docker image
- Push Docker image to AWS ECR

### 🚀 Continuous Deployment
- Runs on a self-hosted runner (EC2)
- Pulls latest Docker image from ECR
- Stops existing container (if running)
- Runs the updated Docker container
- Cleans unused Docker images

### 🔐 Secrets Used
All sensitive values are securely stored using **GitHub Secrets**:
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_REGION`
- `ECR_REPOSITORY_NAME`
- `AWS_ECR_LOGIN_URI`

This ensures security and prevents credentials from being exposed in code.
