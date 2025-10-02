How to Attach and Mount Extra EBS Volume to Linux EC2 in AWS | Mounting EBS Volume

🎯 Objective

Learn how to attach, mount, and use an EBS volume with an EC2 instance for persistent storage in AWS.

🛠️ AWS Services Used

EC2 (Elastic Compute Cloud): Instance to attach volume

EBS (Elastic Block Store): Persistent block storage

IAM: Proper permissions for EC2 access

📋 Steps

1. Create an EBS Volume

Go to AWS Console → EC2 → Elastic Block Store → Volumes → Create Volume

Choose Volume type (e.g., General Purpose SSD gp3)

Set Size (e.g., 1 GB for testing)

Select the same Availability Zone as your EC2 instance

Click Create Volume

2. Attach Volume to EC2

firstly launce an ec2 instance in same availability zone

Select the volume → Actions → Attach Volume

Choose the EC2 instance

Click Attach

3. Connect to EC2 & Mount Volume

SSH into your EC2 instance:

ssh -i mykey.pem ec2-user@<EC2-Public-IP>

2 . After ssh switch into root user

sudo su -

3 . use command

df -h

4 . Format the Volume (if needed)

Check if filesystem exists:

sudo file -s /dev/nvme1n1

If output shows data, format it:

sudo mkfs -t ext4 /dev/nvme1n1

Note —> replace with your disk name like /dev/xvdf in my case it is not xvdf it is nvme1n1

4. Mount the Volume

Create a mount point:

sudo mkdir /mnt/myvolume

Mount it:

sudo mount /dev/nvme1n1 /mnt/myvolume

Verify:

  df -h

🌐 Connect With Me

💻 GitHub: ritesh355

📝 Blog: ritesh-devops.hashnode.dev

💼 LinkedIn: Ritesh Singh


