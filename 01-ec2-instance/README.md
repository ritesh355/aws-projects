# Project 1: Launch an EC2 Instance

## 🎯 Objective
Learn how to launch, configure, and connect to an Amazon EC2 instance.  
This project will give you hands-on experience with AWS compute services and basic networking.

---

## 🛠️ AWS Services Used
- **EC2 (Elastic Compute Cloud):** Virtual server hosting
- **IAM:** Secure access with least privilege
- **Security Groups:** Firewall rules
- **Key Pairs:** Secure SSH login

---

## 📋 Steps

### 1. Create an IAM User
1. Go to **IAM Console → Users → Add User**.
2. Create user with **Programmatic + Console access**.
3. Attach policy `AmazonEC2FullAccess`.
4. Save **Access Key & Secret Key** for AWS CLI.

---

### 2. Launch an EC2 Instance
1. Go to **EC2 Console → Launch Instance**.
2. Choose **Amazon Linux 2 AMI (Free Tier Eligible)**.
3. Select instance type: **t2.micro** (Free Tier).
4. Create a new **Key Pair** → download `mykey.pem`.
5. Configure **Security Group**:
   - Allow **SSH (22)** from My IP
   - (Optional) Allow **HTTP (80)** for web access
6. Launch instance.

---

### 3. Connect to Instance
1. Open terminal and set correct permissions for key:
   ```bash
   chmod 400 mykey.pem

