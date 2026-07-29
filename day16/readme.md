# 🚀 Day 16 - GitOps with Jira, AWS Auto Scaling & Amazon RDS

## 📅 Date

30 July 2026

---

# 🚀 Introduction

Today, I learned how **GitOps** can be implemented using **GitHub and Jira**, making Jira the **single source of truth** for tracking development work. I also performed hands-on AWS labs where I created **Auto Scaling Groups**, worked with **Launch Templates**, and connected an **Amazon RDS database with an EC2 instance** inside a VPC.

This session helped me understand how development workflows integrate with cloud infrastructure in real-world DevOps environments.

---

# 📚 Topics Covered

## 🔄 GitOps
- What is GitOps?
- Jira & GitHub Integration
- Source of Truth
- Smart Commits
- Pull Requests
- Merge Requests
- Issue Tracking

## ☁️ AWS
- Launch Templates
- Auto Scaling Groups (ASG)
- Creating Templates from Scratch
- Creating Templates from Existing Templates
- Amazon RDS
- Connecting EC2 with RDS
- VPC Configuration
- Security Groups
- Database Connectivity
- Troubleshooting & Debugging

---

# 🔄 What is GitOps?

GitOps is an operational framework where **Git becomes the single source of truth** for both application code and infrastructure.

Every infrastructure or application change is managed through Git.

### Benefits

- Version Control
- Audit Trail
- Easy Rollbacks
- Team Collaboration
- Automated Deployments
- Better Change Tracking

---

# 🎫 Jira + GitHub Integration

Jira can be connected with GitHub so that development activities are automatically linked to project tasks.

Once integrated:

- Commits appear in Jira issues
- Pull Requests are linked automatically
- Merge events are displayed
- Deployment history can be tracked
- Developers and managers have complete visibility

Example

```
JIRA-101 Add Login API
```

Commit message:

```bash
git commit -m "JIRA-101 Added login validation"
```

The commit automatically appears inside the **JIRA-101** ticket after pushing to GitHub.

---

# 📌 Why Use Jira as the Source of Truth?

Jira provides one central location for:

- Task Management
- Sprint Planning
- Bug Tracking
- Development Progress
- Pull Requests
- Code Reviews
- Deployment Tracking

Instead of checking multiple tools separately, the complete development lifecycle can be viewed from a Jira ticket.

---

# ☁️ AWS Launch Templates

A Launch Template stores reusable EC2 configuration.

It includes:

- AMI
- Instance Type
- Security Groups
- Storage
- IAM Role
- User Data
- Key Pair

---

# Creating a Launch Template from Scratch

Steps:

1. Open EC2 Console
2. Navigate to **Launch Templates**
3. Click **Create Launch Template**
4. Enter Template Name
5. Select AMI
6. Select Instance Type
7. Configure Security Groups
8. Configure Storage
9. Add User Data (Optional)
10. Save Template

---

# Creating a Template from an Existing Template

Instead of configuring everything again:

```
Launch Templates

↓

Select Existing Template

↓

Actions

↓

Create New Template from Existing
```

Advantages:

- Saves time
- Ensures consistency
- Reduces manual errors
- Ideal for production environments

---

# 📈 Auto Scaling Group (ASG)

Auto Scaling Groups automatically adjust the number of EC2 instances based on demand.

### Components

- Launch Template
- Minimum Capacity
- Desired Capacity
- Maximum Capacity
- Scaling Policies

Example

```
Minimum = 2

Desired = 3

Maximum = 6
```

Benefits:

- High Availability
- Automatic Scaling
- Fault Tolerance
- Cost Optimization

---

# 🗄️ Amazon RDS

Amazon RDS (Relational Database Service) is a managed database service provided by AWS.

Supported databases include:

- MySQL
- PostgreSQL
- MariaDB
- Oracle
- SQL Server

---

# Connecting EC2 to RDS

To allow an EC2 instance to communicate with an RDS database:

### Step 1

Create an RDS database.

---

### Step 2

Ensure the EC2 instance and RDS are inside the same VPC (or have appropriate network connectivity).

---

### Step 3

Configure Security Groups.

Example:

```
EC2 Security Group

↓

Allow Outbound MySQL (3306)

↓

RDS Security Group

↓

Allow Inbound MySQL (3306)
```

---

### Step 4

Connect from the EC2 instance.

For MySQL:

```bash
mysql -h <RDS-ENDPOINT> -u admin -p
```

---

# 🛠️ Database Configuration

After connecting:

- Create Databases
- Create Tables
- Insert Data
- Verify Connectivity
- Test Application Access

---

# 🐞 Debugging Connectivity Issues

During the hands-on lab, common troubleshooting steps included:

### Check Security Groups

Ensure port **3306** (MySQL) is allowed.

---

### Verify VPC

Both resources should be in the correct VPC or connected through routing.

---

### Check Subnets

Verify subnet configuration and routing.

---

### Verify Database Endpoint

Use the correct RDS endpoint.

---

### Check Credentials

Ensure username and password are correct.

---

### Test Network Connectivity

Example:

```bash
telnet <RDS-ENDPOINT> 3306
```

or

```bash
nc -zv <RDS-ENDPOINT> 3306
```

---

### Verify Database Service

Ensure the RDS instance is in the **Available** state.

---

# 🎯 Key Takeaways

- Learned how GitOps uses Git as the source of truth.
- Integrated Jira with GitHub for automatic commit and pull request tracking.
- Created Launch Templates from scratch and from existing templates.
- Performed hands-on practice with Auto Scaling Groups.
- Connected an EC2 instance to an Amazon RDS database.
- Understood VPC networking and Security Group configuration.
- Practiced debugging common database connectivity issues.

---

# 📈 Progress

- ✅ Day 16 – GitOps with Jira, AWS Auto Scaling & Amazon RDS

**Completed:** 16 / 90 Days 🚀

---

> **"In DevOps, automation builds speed, but visibility builds confidence. GitOps brings both together by making Git the single source of truth."** 🚀