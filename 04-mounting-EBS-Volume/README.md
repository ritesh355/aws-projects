# Project 4: Mounting an EBS Volume on EC2

## 🎯 Objective
Learn how to **attach, mount, and use an EBS volume** with an EC2 instance for persistent storage in AWS.

---

## 🛠️ AWS Services Used
- **EC2 (Elastic Compute Cloud)**: Instance to attach volume  
- **EBS (Elastic Block Store)**: Persistent block storage  
- **IAM**: Proper permissions for EC2 access  

---

## 📋 Steps

### 1. Create an EBS Volume
1. Go to **AWS Console → EC2 → Elastic Block Store → Volumes → Create Volume**  
2. Choose **Volume type** (e.g., General Purpose SSD `gp3`)  
3. Set **Size** (e.g., 1 GB for testing)  
4. Select the **same Availability Zone** as your EC2 instance  
5. Click **Create Volume**  

**Screenshot: Create EBS Volume**  
![Create EBS Volume](images/create-ebs.png)

---

### 2. Attach Volume to EC2
1. Select the volume → **Actions → Attach Volume**  
2. Choose the **EC2 instance**  
3. Click **Attach**  

**Screenshot: Attach Volume**  
![Attach Volume](images/attach-ebs.png)

---

### 3. Connect to EC2 & Mount Volume
1. SSH into your EC2 instance:  
```bash
ssh -i mykey.pem ec2-user@<EC2-Public-IP>
```
2.  After ssh switch into root user
```
sudo su -
```
3.    List block devices to identify your new volume: 
```
df -h
```
or 
```
lsblk
```
4. Format the Volume (if needed)
Check if filesystem exists:

```
sudo file -s /dev/nvme1n1
```
If output shows data, format it:

```
sudo mkfs -t ext4 /dev/nvme1n1
```
***Note —> replace with your disk name like /dev/xvdf in my case it is not xvdf it is nvme1n1***
### 4. Mount the Volume


Create a mount point:

    ```
    sudo mkdir /mnt/myvolume
    ```
   
 Mount it:
 
    ```
    sudo mount /dev/nvme1n1 /mnt/myvolume
    
    ```
 Verify

    ```
    df -h 
    lsblk
    ```
    
    

    
 




