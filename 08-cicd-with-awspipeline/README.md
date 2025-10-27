 # AWS CI/CD Node.js Application

![AWS CI/CD Pipeline](https://img.shields.io/badge/AWS-CodePipeline-blue) ![Node.js](https://img.shields.io/badge/Node.js-v20.19.5-green) ![GitHub](https://img.shields.io/badge/GitHub-Repository-brightgreen)
![](assets/final.png)

Welcome to the **AWS CI/CD Node.js Application** repository! This project showcases a production-ready Node.js application deployed on AWS EC2 using a fully automated CI/CD pipeline with AWS CodePipeline, CodeBuild, and CodeDeploy. Integrated with GitHub for seamless source control, this pipeline automates building and deploying the application.

---
## 🚀 Project Overview

This repository hosts a Node.js application (`my-app`) that serves a "Hello from AWS CI/CD!" message on port 3000. Deployed on an AWS EC2 instance (`ip-172-31-19-118`), it leverages a robust CI/CD pipeline to demonstrate modern DevOps practices and cloud infrastructure management.

- **Purpose**: Showcase expertise in building, testing, and deploying a Node.js application using AWS services.
- **Technologies**: Node.js, AWS CodePipeline, CodeBuild, CodeDeploy, EC2, GitHub.
- **Key Achievement**: Resolved deployment issues (e.g., `ScriptFailed` error with `EACCES` permissions) to achieve a stable, automated pipeline.

---
## 🛠️ Features

- **Node.js Application**: Lightweight Express.js server running on port 3000.
- **Automated CI/CD Pipeline**:
  - **Source**: GitHub repository (`ritesh/my-aws-cicd-app`, `main` branch).
  - **Build**: AWS CodeBuild generates `build-artifact.zip`.
  - **Deploy**: AWS CodeDeploy deploys to EC2 (`MyAppDeploy`, `ProductionGroup`).
- **Error Handling**: Fixed permissions issues with `npm install` by optimizing `buildspec.yml` and `install_deps.sh`.
- **Scalability**: Ready for scaling with additional EC2 instances or load balancers.
- **Monitoring**: Application logs (`app.log`) for debugging and verification.

 --- 

## 📁 Repository Structure
![](assets/repostructure.png)

## 🛠️ Setup and Deployment

### Prerequisites
- **AWS Account**: Permissions for CodePipeline, CodeBuild, CodeDeploy, EC2, and S3.
- **GitHub Account**: Repository `ritesh/my-aws-cicd-app` with push access.
- **Node.js**: Version 20.19.5 (with npm 10.8.2).
- **EC2 Instance**: Ubuntu with CodeDeploy agent installed.
---
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

# AWS CI/CD Pipeline Setup

## GitHub Source
- Connected via AWS Connector for GitHub (connection: MyAppGitHubConnection).
- Webhook triggers pipeline on main branch pushes.

## CodeBuild (MyAppBuild)
Uses `buildspec.yml` to:
- Install Node.js 18.
- Run `npm install`.
- Create `build-artifact.zip`.

Artifact stored in `s3://myapp-cicd-artifacts-123`.

## CodeDeploy (MyAppDeploy)
- Deploys to EC2 (ProductionGroup, instance ip-172-31-19-118).
- `appspec.yml` defines deployment steps.
- `install_deps.sh` handles npm install with permissions fixes.

## CodePipeline (MyAppPipeline)
### Stages:
1. **Source:** GitHub (ritesh/my-aws-cicd-app, main).
2. **Build:** CodeBuild (MyAppBuild).
3. **Deploy:** CodeDeploy (MyAppDeploy, ProductionGroup).

- Automatic retries enabled for transient failure recovery.
---
 
## Deployment Verification
- **Check Logs:**
```
ssh -i <key.pem> ubuntu@<ec2-public-ip>
cd /home/ubuntu/my-app
cat app.log
```
- **Test Application:**
  - Open http://<ec2-public-ip>:3000 in a browser (displays “Hello from AWS CI/CD!MYSELF RITESH”).
---
# 🐞 Troubleshooting

## Common Issue:
ScriptFailed error (exit code 243) due to EACCES permissions.

## Solution:
Ensured `buildspec.yml` excludes `node_modules/` and `package-lock.json`; `install_deps.sh` clears residuals and sets permissions.

## Logs:
```bash
bash sudo tail -n 100 /var/log/aws/codedeploy-agent/codedeploy-agent.log
cat /home/ubuntu/.npm/_logs/*.log
```
---
# Why This Project Stands Out

- **DevOps Expertise:** End-to-end CI/CD pipeline with AWS services.  
- **Problem-Solving:** Resolved complex permissions issues (EACCES on `node_modules/.package-lock.json`).  
- **Automation:** Fully automated deployments with GitHub webhooks.  
- **Clean Code:** Well-structured repository with clear configurations.  

# 📬 Contact

- **GitHub:** (https://github.com/ritesh355/)   
- **LinkedIn:** (https://www.linkedin.com/in/ritesh-singh-092b84340/) 

Feel free to explore, fork, or contribute to this project! 🚀


    
