# AWS EC2 Automation Guide

Automate the deployment and management of AWS EC2 instances, EBS volumes, snapshots, and retention policies. This repository provides step-by-step instructions and scripts to help launch Ubuntu EC2 instances, attach storage volumes, create encrypted EBS snapshots, and configure AWS Recycle Bin retention rules for snapshot management.

---

## Features

- Launch Ubuntu EC2 instances
- Create and attach EBS volumes
- Create encrypted EBS snapshots
- Configure AWS Recycle Bin retention rules for snapshots
- Step-by-step instructions for each process
- Secure and cost-effective cloud resource management

---

## Prerequisites

- AWS Account with appropriate permissions
- AWS CLI installed and configured (optional for automation scripts)
- SSH client for EC2 instance access
- Key pair for secure SSH login

---

## Usage

### Step 1: Launch EC2 (Ubuntu)

1. Sign in to the AWS Console.
2. Navigate to EC2 service and choose **Instances > Launch instances**.
3. Select an Ubuntu Server AMI (e.g., Ubuntu 22.04 LTS).
4. Configure instance details:
   - Choose instance type (e.g., t2.micro/t3.micro).
   - Enable HTTP, HTTPS, and SSH traffic.
   - Add storage (default usually works).
   - Select or create a Key pair for SSH access.
   - Enable Auto-assign public IP.
5. Review and launch the instance.
6. Wait until the instance state is **running** and status checks pass.

### Step 2: Create & Attach Volume

1. Go to **EC2 > Volumes** and click **Create volume**.
2. Configure volume:
   - Type: General Purpose SSD (gp3)
   - Size: 1 GiB (or as needed)
   - Availability Zone: Match the EC2 instance AZ
3. Create the volume and note the volume ID.
4. Select the volume, click **Actions > Attach volume**.
5. Attach it to your instance (device name: `/dev/sdf` or `/dev/xvdf`).
6. The volume status becomes **in-use**.

### Step 3: Create an EBS Snapshot

1. Navigate to **Elastic Block Store > Snapshots**.
2. Click **Create snapshot**.
3. Choose resource type: Volume.
4. Select the volume ID to back up.
5. Add a description (e.g., "EBS snapshot test").
6. Create the snapshot and wait until status is **completed**.

### Step 4: Setup AWS Recycle Bin Retention Rule

1. Search for **Recycle Bin** in the AWS Console and open it.
2. In the left navigation, click **Retention rules > Create retention rule**.
3. Enter retention rule name (e.g., `retain-ebs-snapshot`).
4. Set resource type to **EBS_SNAPSHOT**.
5. Configure retention period (1 to 365 days).
6. Review and create the rule.

---

## Contributing

Feel free to open issues or submit pull requests to improve this guide or add automation scripts.

---

## License

This project is licensed under the MIT License.

---

## Contact & Socials

<p align="center">
  <a href="https://github.com/ShaikhAteeb02" target="_blank" style="text-decoration:none;padding:8px 16px;background:#333;color:#fff;border-radius:5px;margin-right:10px;">GitHub</a>
  <a href="https://www.linkedin.com/in/ateeb-ahmed-shaikh-932234192" target="_blank" style="text-decoration:none;padding:8px 16px;background:#0077b5;color:#fff;border-radius:5px;">LinkedIn</a>
</p>
