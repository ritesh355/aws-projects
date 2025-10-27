# AWS CI/CD Node.js Application

![AWS CI/CD Pipeline](https://img.shields.io/badge/AWS-CodePipeline-blue) ![Node.js](https://img.shields.io/badge/Node.js-v20.19.5-green) ![GitHub](https://img.shields.io/badge/GitHub-Repository-brightgreen)

Welcome to the **AWS CI/CD Node.js Application** repository! This project showcases a production-ready Node.js application deployed on AWS EC2 using a fully automated CI/CD pipeline with AWS CodePipeline, CodeBuild, and CodeDeploy. Integrated with GitHub for seamless source control, this pipeline automates building and deploying the application.

## 🚀 Project Overview

This repository hosts a Node.js application (`my-app`) that serves a "Hello from AWS CI/CD!" message on port 3000. Deployed on an AWS EC2 instance (`ip-172-31-19-118`), it leverages a robust CI/CD pipeline to demonstrate modern DevOps practices and cloud infrastructure management.

- **Purpose**: Showcase expertise in building, testing, and deploying a Node.js application using AWS services.
- **Technologies**: Node.js, AWS CodePipeline, CodeBuild, CodeDeploy, EC2, GitHub.
- **Key Achievement**: Resolved deployment issues (e.g., `ScriptFailed` error with `EACCES` permissions) to achieve a stable, automated pipeline.

## 🛠️ Features

- **Node.js Application**: Lightweight Express.js server running on port 3000.
- **Automated CI/CD Pipeline**:
  - **Source**: GitHub repository (`ritesh/my-aws-cicd-app`, `main` branch).
  - **Build**: AWS CodeBuild generates `build-artifact.zip`.
  - **Deploy**: AWS CodeDeploy deploys to EC2 (`MyAppDeploy`, `ProductionGroup`).
- **Error Handling**: Fixed permissions issues with `npm install` by optimizing `buildspec.yml` and `install_deps.sh`.
- **Scalability**: Ready for scaling with additional EC2 instances or load balancers.
- **Monitoring**: Application logs (`app.log`) for debugging and verification.

## 📁 Repository Structure


## 🛠️ Setup and Deployment

### Prerequisites
- **AWS Account**: Permissions for CodePipeline, CodeBuild, CodeDeploy, EC2, and S3.
- **GitHub Account**: Repository `ritesh/my-aws-cicd-app` with push access.
- **Node.js**: Version 20.19.5 (with npm 10.8.2).
- **EC2 Instance**: Ubuntu with CodeDeploy agent installed.

### Local Setup
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/ritesh/my-aws-cicd-app.git
   cd my-aws-cicd-app
   ```
2. **Install dependencies**:
   ```
   npm install
   ```
3. **Run Locally:**:
   ```
   node index.js
   ```
- Access at http://localhost:3000.

---


