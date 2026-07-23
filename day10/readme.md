# ☁️ Day 10 - Git Advanced, AWS Cloud Fundamentals & Python OOP

## 📅 Date

24 July 2026

---

# 🚀 Introduction

Day 10 was focused on advancing my knowledge of **Git**, understanding **Cloud Computing and AWS fundamentals**, and learning the basics of **Object-Oriented Programming (OOP)** in Python.

I explored different Git merge strategies, branching, rebasing, cloud deployment models, AWS infrastructure, pricing, IAM, and built a simple **Log Analyzer** project using Python classes.

---

# 📚 Topics Covered

## 🔄 Git & GitHub
- Git Merge
- Merge Commit
- Fast-Forward Merge
- Git Rebase
- Commit Hashes
- Git Fetch
- Git Fetch --all
- Git Log (`--oneline`)
- Branching

## ☁️ AWS Cloud
- What is Cloud Computing?
- Public, Private & Hybrid Cloud
- Data Centers
- AWS Regions
- Availability Zones
- AWS Pricing Calculator
- AWS Access Methods
- AWS CLI
- AWS SDK
- AWS Console
- Root User
- IAM
- IAM Policies
- IaaS, PaaS & SaaS
- CapEx vs OpEx

## 🐍 Python
- Classes
- Objects
- Log Analyzer Project

---

# 🔄 Git Merge

Git Merge combines changes from one branch into another.

Example:

```bash
git checkout main
git merge feature-login
```

---

# Merge Types

## 1️⃣ Merge Commit

A new merge commit is created to preserve branch history.

```text
A---B---C (main)
     \
      D---E (feature)

After Merge

A---B---C---------M
     \           /
      D---------E
```

Command

```bash
git merge feature
```

---

## 2️⃣ Fast-Forward Merge

Occurs when the target branch has no new commits.

Git simply moves the branch pointer forward.

```text
A---B---C (main)
         \
          D---E (feature)

↓

A---B---C---D---E
```

Command

```bash
git merge feature
```

---

# Git Rebase

Rebase moves commits from one branch on top of another, creating a cleaner history.

Command

```bash
git checkout feature
git rebase main
```

### Merge vs Rebase

| Merge | Rebase |
|--------|--------|
| Preserves history | Creates a cleaner history |
| Adds merge commits | No merge commits |
| Better for team collaboration | Better for keeping history linear |

---

# Commit Hash

Every commit in Git has a unique SHA hash.

Example

```text
f2c1d89
```

View commits

```bash
git log
```

Compact view

```bash
git log --oneline
```

---

# Git Fetch

Downloads changes from the remote repository without merging them.

```bash
git fetch
```

---

# Git Fetch All

Fetches updates from all configured remotes.

```bash
git fetch --all
```

---

# ☁️ What is Cloud Computing?

Cloud Computing is the delivery of computing services such as servers, storage, databases, networking, and software over the internet.

### Benefits

- Scalability
- Cost Efficiency
- High Availability
- Security
- Global Access

---

# Cloud Deployment Models

## Public Cloud

Resources are owned and managed by cloud providers.

Examples:

- AWS
- Azure
- Google Cloud

---

## Private Cloud

Infrastructure dedicated to a single organization.

Examples:

- VMware
- OpenStack

---

## Hybrid Cloud

A combination of Public and Private Cloud environments.

---

# How Cloud Works

```text
Users
   │
Internet
   │
AWS Data Center
   │
Region
   │
Availability Zone
   │
Virtual Server (EC2)
```

---

# Data Center

A physical building that houses servers, networking devices, and storage systems.

---

# AWS Region

A geographical location containing multiple Availability Zones.

Examples:

- us-east-1
- ap-south-1
- eu-west-1

---

# Availability Zone (AZ)

An isolated data center within a region.

Benefits:
- Fault Tolerance
- High Availability
- Disaster Recovery

---

# AWS Pricing Calculator

The AWS Pricing Calculator helps estimate the monthly cost of AWS services before deployment.

Common uses:
- Budget planning
- Cost comparison
- Architecture estimation

---

# Ways to Access AWS

## AWS Management Console

A web-based graphical interface for managing AWS services.

---

## AWS CLI

Command-line interface to interact with AWS services.

Example

```bash
aws s3 ls
```

Configure CLI

```bash
aws configure
```

---

## AWS SDK

Software libraries for interacting with AWS using programming languages.

Example (Python - Boto3)

```python
import boto3

s3 = boto3.client("s3")
```

---

# Root User

The Root User has unrestricted access to all AWS services.

Best Practice:
- Use only for account setup.
- Enable MFA.
- Avoid daily use.

---

# IAM (Identity and Access Management)

IAM manages authentication and authorization in AWS.

It allows you to create:

- Users
- Groups
- Roles
- Policies

---

# IAM Policy

Policies define permissions for AWS resources.

Example:

- Allow EC2 access
- Deny S3 deletion
- Read-only access

---

# Cloud Service Models

| Model | Description | Example |
|--------|-------------|---------|
| IaaS | Infrastructure as a Service | Amazon EC2 |
| PaaS | Platform as a Service | AWS Elastic Beanstalk |
| SaaS | Software as a Service | Gmail, Microsoft 365 |

---

# CapEx vs OpEx

| CapEx | OpEx |
|--------|------|
| Capital Expenditure | Operational Expenditure |
| Buy servers | Pay-as-you-go cloud |
| High upfront cost | Low upfront cost |
| Maintenance required | Managed by cloud provider |

---

# 🐍 Python OOP

## Class

A blueprint for creating objects.

```python
class Server:
    pass
```

---

## Object

An instance of a class.

```python
server1 = Server()
```

---

# Project - Log Analyzer

### Objective

Analyze log files and count different log levels.

Example Log

```text
INFO Server Started
ERROR Database Failed
WARNING Low Memory
ERROR Connection Lost
```

### Python Example

```python
class LogAnalyzer:

    def __init__(self, logs):
        self.logs = logs

    def count_errors(self):
        count = 0

        for log in self.logs:
            if "ERROR" in log:
                count += 1

        return count


logs = [
    "INFO Server Started",
    "ERROR Database Failed",
    "WARNING Low Memory",
    "ERROR Connection Lost"
]

analyzer = LogAnalyzer(logs)

print("Total Errors:", analyzer.count_errors())
```

### Output

```text
Total Errors: 2
```

---

# 🎯 Key Takeaways

- Learned advanced Git concepts including Merge, Fast-Forward, Rebase, Fetch, and Commit Hashes.
- Understood cloud deployment models and AWS global infrastructure.
- Learned about Regions, Availability Zones, IAM, Root User, and AWS CLI.
- Explored IaaS, PaaS, SaaS, and CapEx vs OpEx.
- Practiced Object-Oriented Programming in Python.
- Built a simple Log Analyzer using Python classes.

---

# 📈 Progress

- ✅ Day 10 – Git Advanced, AWS Cloud Fundamentals & Python OOP

**Completed:** 10 / 90 Days 🚀

---

> "Every commit, every command, and every concept learned today is another step toward becoming a DevOps Engineer."