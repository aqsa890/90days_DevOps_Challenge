# 🔧 Day 09 - Git, GitHub & AWS Python Automation

## 📅 Date

23 July 2026

---

# 🚀 Introduction

Today, I started learning one of the most essential tools for every DevOps Engineer: **Git & GitHub**.

Version control is the backbone of modern software development and DevOps. I learned how Git tracks changes, how GitHub enables collaboration, and how to use Git commands to manage repositories and branches.

I also explored **AWS Python Automation**, including **AWS Lambda** and **Boto3**, and how Python is used to automate cloud operations.

---

# 📚 Topics Covered

- What is Git?
- What is GitHub?
- Git vs GitHub
- Benefits of Git & GitHub
- Repository
- Default Branch
- Git Installation
- Git Configuration
- Authentication using SSH & PAT
- Git Workflow
- Git Commands
- Git Restore
- Branches
- Creating & Switching Branches
- Merging
- AWS Python Automation
- AWS Lambda
- Boto3
- API Requests

---

# 📖 What is Git?

Git is a **Distributed Version Control System (DVCS)** used to track changes in source code.

It allows developers to:

- Track file changes
- Collaborate with teams
- Maintain project history
- Roll back to previous versions
- Work on multiple features simultaneously

Git stores the complete history locally.

---

# 🌍 What is GitHub?

GitHub is a cloud platform that hosts Git repositories.

It provides:

- Cloud Backup
- Collaboration
- Pull Requests
- Code Reviews
- CI/CD Integrations
- Issue Tracking
- Project Management

Think of Git as the engine and GitHub as the online platform where repositories are stored.

---

# Git vs GitHub

| Git | GitHub |
|------|---------|
| Version Control System | Cloud Hosting Platform |
| Works locally | Works online |
| Tracks code changes | Stores Git repositories |
| Open Source | Provides collaboration features |

---

# 🎯 Benefits of Git & GitHub

- Version Control
- Easy Collaboration
- Backup of Code
- Branch Management
- Rollback Support
- Open Source Contribution
- CI/CD Integration
- Project Documentation

---

# 📂 What is a Repository?

A repository (repo) is a project folder managed by Git.

It contains:

- Source Code
- Documentation
- Images
- Commit History
- Branches

---

# 🌿 Default Branch

Most modern repositories use:

```
main
```

Older repositories may use:

```
master
```

Rename branch

```bash
git branch -M main
```

---

# ⚙️ Configure Git

Check version

```bash
git --version
```

Configure username

```bash
git config --global user.name "Your Name"
```

Configure email

```bash
git config --global user.email "your@email.com"
```

View configuration

```bash
git config --list
```

---

# 🔐 GitHub Authentication

## Method 1 — SSH (Recommended)

Generate SSH Key

```bash
ssh-keygen -t ed25519 -C "your@email.com"
```

Start SSH Agent

```bash
eval "$(ssh-agent -s)"
```

Add SSH Key

```bash
ssh-add ~/.ssh/id_ed25519
```

Copy Public Key

```bash
cat ~/.ssh/id_ed25519.pub
```

Paste it into:

GitHub → Settings → SSH and GPG Keys

Test Connection

```bash
ssh -T git@github.com
```

---

## Method 2 — Personal Access Token (PAT)

GitHub no longer supports passwords for Git operations.

Instead:

- Create a Personal Access Token
- Use the token instead of your password

---

# 🔄 Git Workflow

```
Working Directory
        │
git add
        │
        ▼
Staging Area
        │
git commit
        │
        ▼
Local Repository
        │
git push
        │
        ▼
GitHub Repository
```

---

# 💻 Common Git Commands

Initialize Git

```bash
git init
```

Clone Repository

```bash
git clone <repository-url>
```

Check Status

```bash
git status
```

Add All Files

```bash
git add .
```

Add Specific File

```bash
git add README.md
```

Commit Changes

```bash
git commit -m "Initial Commit"
```

View Commit History

```bash
git log
```

Compact Log

```bash
git log --oneline
```

Push Changes

```bash
git push origin main
```

Pull Latest Changes

```bash
git pull origin main
```

Fetch Changes

```bash
git fetch
```

---

# ↩️ Git Restore

Discard changes in a file

```bash
git restore file.txt
```

Restore staged file

```bash
git restore --staged file.txt
```

---

# 🌿 Git Branches

Branches allow developers to work on different features independently.

Main branch

```
main
```

Create Branch

```bash
git branch feature-login
```

View Branches

```bash
git branch
```

Switch Branch

```bash
git switch feature-login
```

or

```bash
git checkout feature-login
```

Create & Switch

```bash
git switch -c feature-login
```

Delete Branch

```bash
git branch -d feature-login
```

Merge Branch

```bash
git merge feature-login
```

---

# 🐍 Python API Requests

Python can communicate with APIs using the `requests` library.

Example

```python
import requests

response = requests.get("https://jsonplaceholder.typicode.com/users")

print(response.status_code)
print(response.json())
```

---

# ☁️ AWS Python Automation

Python is widely used to automate AWS resources.

Examples

- Start EC2
- Stop EC2
- Create S3 Bucket
- Upload Files
- Delete Resources
- Create IAM Users

Automation saves time and reduces manual errors.

---

# ⚡ AWS Lambda

AWS Lambda is a serverless compute service that lets you run code without managing servers.

### Why Lambda?

- No server management
- Pay only when code runs
- Auto scaling
- Event-driven execution

Common Triggers

- S3 Upload
- API Gateway
- CloudWatch Events
- SNS
- DynamoDB Streams

---

# 📦 Boto3

Boto3 is the official AWS SDK for Python.

It allows Python programs to interact with AWS services.

Install

```bash
pip install boto3
```

Example

```python
import boto3

ec2 = boto3.client("ec2")

response = ec2.describe_instances()

print(response)
```

---

# 🔥 Where is Boto3 Used?

- EC2 Automation
- S3 File Management
- Lambda Functions
- IAM Management
- CloudWatch Monitoring
- DynamoDB
- SNS
- SQS

---

# 🎯 Key Takeaways

- Learned the fundamentals of Git and GitHub.
- Understood the complete Git workflow.
- Practiced essential Git commands.
- Learned repository and branch management.
- Configured Git authentication using SSH and PAT.
- Explored Git restore and branching strategies.
- Learned how Python interacts with APIs.
- Explored AWS Lambda and serverless computing.
- Learned how Boto3 automates AWS resources.

---

# 📈 Progress

- ✅ Day 09 – Git, GitHub & AWS Python Automation

**Completed:** 9 / 90 Days 🚀

---

⭐ "Version control is not just about saving code—it's about collaborating, tracking progress, and building software with confidence."