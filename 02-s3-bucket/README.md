# Project 2: Create & Manage an S3 Bucket

## 🎯 Objective
Learn how to create, configure, and use an Amazon S3 bucket for storage.  
Understand features like **bucket policies, versioning, encryption, and lifecycle rules**.

---

## 🛠️ AWS Services Used
- **S3 (Simple Storage Service):** Object storage
- **IAM:** User access and permissions
- **Bucket Policies:** Control access
- **Lifecycle Rules:** Automate object management

---

## 📋 Steps

### 1. Create an S3 Bucket
1. Go to **AWS Console → S3 → Create Bucket**.
2. Provide a **unique bucket name** (e.g., `my-aws-project-bucket`).  
3. Select a **region** close to you.  
4. Disable **Block all public access** if you want public website access (for testing).  
5. Click **Create Bucket**.

---

### 2. Upload Files to S3
- Upload any files (HTML, text, images) to your bucket via console.  
- OR via AWS CLI:
```bash
aws s3 cp myfile.txt s3://my-aws-project-bucket/

