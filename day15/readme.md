# ☁️ Day 15 - AWS EC2, Auto Scaling, Load Balancer & S3 Static Website Hosting

## 📅 Date

29 July 2026

---

# 🚀 Introduction

Today was focused entirely on **Amazon Web Services (AWS)**. I learned how to launch and configure EC2 instances, the difference between Root User and IAM, Nginx installation on Ubuntu, Auto Scaling Groups, Load Balancers, Target Groups, AWS WAF, S3 Buckets, Static Website Hosting, and AWS CLI.

These services are the foundation of deploying scalable, secure, and highly available applications on AWS.

---

# 📚 Topics Covered

- AWS Fundamentals
- EC2 Instance Creation
- Root User vs IAM User
- Installing Nginx on Ubuntu EC2
- EC2 Pricing (On-Demand vs Spot Instances)
- Launch Templates
- User Data Scripts
- Auto Scaling Groups (ASG)
- Target Groups
- Application Load Balancer (ALB)
- Elastic Load Balancer (ELB)
- Internet-facing vs Internal Load Balancer
- AWS WAF
- Network ACL Basics
- Amazon S3
- Bucket Configuration
- Bucket Permissions
- Object Ownership
- Static Website Hosting
- Bucket Policies
- AWS CLI

---

# ☁️ What is AWS?

Amazon Web Services (AWS) is the world's leading cloud computing platform that provides on-demand cloud services such as virtual machines, storage, networking, databases, security, monitoring, and much more.

### Benefits

- High Availability
- Scalability
- Pay-as-you-go Pricing
- Secure Infrastructure
- Global Presence

---

# 💻 Amazon EC2

Amazon EC2 (Elastic Compute Cloud) provides virtual servers in the cloud.

### Steps to Launch an EC2 Instance

1. Login to AWS Console
2. Open EC2 Dashboard
3. Click **Launch Instance**
4. Enter Instance Name
5. Select an AMI (Ubuntu)
6. Choose Instance Type (e.g., t2.micro)
7. Create or Select a Key Pair
8. Configure Network & Security Group
9. Configure Storage
10. Launch the Instance

---

# 🔐 Root User vs IAM User

## Root User

- Has full access to all AWS services
- Created automatically with the AWS account
- Should only be used for account setup and billing
- Enable Multi-Factor Authentication (MFA)

## IAM User

- Created by the Root User
- Permissions are controlled using IAM Policies
- Used for daily administration and development
- Follows the Principle of Least Privilege

---

# 🌐 Install Nginx on Ubuntu EC2

Connect to the instance:

```bash
ssh -i key.pem ubuntu@<public-ip>
```

Update packages:

```bash
sudo apt update
```

Install Nginx:

```bash
sudo apt install nginx -y
```

Check status:

```bash
sudo systemctl status nginx
```

Enable Nginx:

```bash
sudo systemctl enable nginx
```

Visit:

```
http://<EC2-Public-IP>
```

You should see the Nginx welcome page.

---

# 💰 EC2 Pricing Models

## On-Demand Instances

- Pay only when the instance is running
- No long-term commitment
- Best for testing and short-term workloads

### Advantages

- Flexible
- Reliable
- No upfront payment

---

## Spot Instances

AWS sells unused EC2 capacity at discounted prices.

### Advantages

- Very low cost
- Ideal for batch jobs and testing

### Disadvantages

- AWS can terminate the instance with short notice

---

# 📦 Launch Templates

Launch Templates store EC2 configuration so it can be reused.

They include:

- AMI
- Instance Type
- Security Group
- Storage
- User Data
- IAM Role

### Create a Launch Template

```
EC2
↓

Actions

↓

Images & Templates

↓

Create Template
```

---

# 💾 EBS Volume Pricing

- **30 GB or less (depending on Free Tier eligibility)** → Typically covered under the AWS Free Tier.
- **More than 30 GB** → Additional storage charges apply.

Always check the current AWS Free Tier terms, as limits and eligibility can change.

---

# ✏️ Modify Launch Template

```
Launch Templates

↓

Select Template

↓

Actions

↓

Modify Template
```

---

# 📜 User Data

User Data automatically executes commands when an EC2 instance launches.

Example:

```bash
#!/bin/bash
apt update -y
apt install nginx -y
systemctl start nginx
systemctl enable nginx
```

### Two Ways to Add User Data

1. While creating the EC2 instance
2. Through the Launch Template

---

# 📈 Auto Scaling Group (ASG)

Auto Scaling automatically increases or decreases EC2 instances based on demand.

### Components

- Launch Template
- Minimum Size
- Desired Capacity
- Maximum Size

Example

```
Minimum = 2

Desired = 3

Maximum = 6
```

---

# 🛠️ Steps to Create an Auto Scaling Group

1. Create a Launch Template
2. Open Auto Scaling Groups
3. Create Auto Scaling Group
4. Select Launch Template
5. Configure Network (VPC & Subnets)
6. Attach Target Group / Load Balancer
7. Configure Scaling Policies and Review

---

# ⚖️ Elastic Load Balancer (ELB)

An ELB distributes incoming traffic across multiple EC2 instances.

Benefits:

- High Availability
- Fault Tolerance
- Better Performance

---

# 🌍 Application Load Balancer (ALB)

ALB works at Layer 7 (HTTP/HTTPS).

Features:

- Path-based routing
- Host-based routing
- HTTPS support
- Health checks

---

# 🌐 Internal vs Internet-facing Load Balancer

## Internet-facing

- Accessible from the Internet
- Used for public applications

## Internal

- Accessible only within the VPC
- Used for internal services

---

# 🎯 Target Group

A Target Group contains the EC2 instances that receive traffic from the Load Balancer.

Health checks ensure only healthy instances receive requests.

---

# 🤖 AWS WAF (Web Application Firewall)

AWS WAF protects web applications from common attacks.

It can block:

- SQL Injection
- Cross-Site Scripting (XSS)
- Bots
- Malicious IP addresses

---

# 🛡️ Network ACL (NACL)

Network ACLs provide stateless security at the subnet level.

They allow or deny inbound and outbound traffic using numbered rules.

---

# 🪣 Amazon S3

Amazon S3 is an object storage service for storing files such as images, videos, backups, and static websites.

---

# Bucket Configuration

While creating a bucket you can configure:

- Bucket Name
- AWS Region
- Versioning
- Encryption
- Object Ownership
- Public Access Settings

---

# 🔐 Bucket Permissions

Permissions control who can access bucket contents.

They can be managed using:

- Bucket Policies
- IAM Policies
- ACLs (if enabled)

---

# 👤 Object Ownership

Object Ownership determines who owns uploaded objects.

Recommended:

```
Bucket owner enforced
```

This disables ACLs and simplifies permission management.

---

# 🌍 Static Website Hosting

Amazon S3 can host static websites built with HTML, CSS, and JavaScript.

### Steps

1. Create an S3 Bucket
2. Upload Website Files
3. Enable Static Website Hosting
4. Set `index.html`
5. Disable Block Public Access (if appropriate)
6. Add a Bucket Policy
7. Access the Website using the generated endpoint

Example Bucket Policy:

```json
{
  "Version":"2012-10-17",
  "Statement":[{
      "Effect":"Allow",
      "Principal":"*",
      "Action":"s3:GetObject",
      "Resource":"arn:aws:s3:::your-bucket-name/*"
  }]
}
```

---

# 💻 AWS CLI

Configure AWS CLI:

```bash
aws configure
```

List S3 Buckets:

```bash
aws s3 ls
```

Create Bucket:

```bash
aws s3 mb s3://my-demo-bucket
```

Upload File:

```bash
aws s3 cp index.html s3://my-demo-bucket
```

List Files:

```bash
aws s3 ls s3://my-demo-bucket
```

Delete File:

```bash
aws s3 rm s3://my-demo-bucket/index.html
```

---

# 🎯 Key Takeaways

- Learned how to create and configure EC2 instances.
- Understood the difference between Root User and IAM User.
- Installed and managed Nginx on Ubuntu EC2.
- Compared On-Demand and Spot Instances.
- Learned Launch Templates and User Data automation.
- Configured Auto Scaling Groups using Launch Templates.
- Understood ALB, ELB, Target Groups, and Load Balancers.
- Explored AWS WAF and Network ACLs.
- Created and configured Amazon S3 Buckets.
- Hosted a static website on Amazon S3.
- Managed AWS resources using AWS CLI.

---

# 📈 Progress

- ✅ Day 15 – AWS EC2, Auto Scaling, Load Balancers & S3

**Completed:** 15 / 90 Days 🚀

---

> **"Cloud isn't just about running servers—it's about building scalable, secure, and highly available systems that can grow with demand."** ☁️🚀