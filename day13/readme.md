# 🔐 Day 13 - DevSecOps Pipeline, Security Automation & Python Projects

## 📅 Date

27 July 2026

---

# 🚀 Introduction

Today, I explored the **DevSecOps pipeline**, understanding how security is integrated into every stage of the Software Development Lifecycle (SDLC). I learned about security scanning tools used during Build, Test, Deploy, and Monitor phases, completed multiple Python projects, created a shell script for vulnerability scanning, and revised common DevOps interview questions.

---

# 📚 Topics Covered

## 🔐 DevSecOps Architecture
- Secure Software Development Lifecycle (SSDLC)
- Build, Test, Deploy & Monitor Pipeline
- SAST
- SCA
- Secrets Scanning
- DAST
- Artifact Scanning
- Image Scanning
- Infrastructure as Code (IaC) Security
- Policy Checks
- Compliance Controls
- Auditing & Monitoring

## 🐍 Python
- Built 2–3 practice projects
- Improved problem-solving using Python

## 📜 Shell Scripting
- Automated vulnerability scanning
- GitLeaks integration

## 💼 Interview Preparation
- Basic DevOps interview questions
- Linux, Git & AWS revision

---

# 🏗️ DevSecOps Pipeline

A DevSecOps pipeline integrates **security checks into every stage** of software development instead of testing only at the end.

```text
Developer
     │
     ▼
 Source Code
     │
     ▼
   BUILD
(SAST • SCA • Secret Scan)
     │
     ▼
    TEST
(DAST • Artifact Scan)
     │
     ▼
   DEPLOY
(IaC Security • Policy Checks • Compliance)
     │
     ▼
   MONITOR
(Auditing • Logging • Alerts)
```

---

# 🔍 Build Stage Security

During the Build stage, the source code is scanned before creating application artifacts.

### SAST (Static Application Security Testing)

Analyzes source code without executing it.

Detects:
- SQL Injection
- Cross-Site Scripting (XSS)
- Hardcoded Credentials
- Buffer Overflow
- Coding Mistakes

### SCA (Software Composition Analysis)

Scans third-party libraries and dependencies for known vulnerabilities.

Example:
- Outdated npm packages
- Vulnerable Python libraries
- Insecure Java dependencies

### Secret Scanning

Detects accidentally committed secrets such as:
- AWS Access Keys
- GitHub Tokens
- API Keys
- Database Passwords

---

# 🧪 Test Stage Security

### DAST (Dynamic Application Security Testing)

Tests a running application from an attacker's perspective.

Finds:
- Authentication Issues
- Broken Access Control
- XSS
- SQL Injection

### Artifact Scanning

Scans generated application packages before deployment.

Examples:
- Docker Images
- JAR Files
- ZIP Packages

---

# 🚀 Deploy Stage Security

### IaC Security

Scans Infrastructure as Code files (Terraform, CloudFormation, Kubernetes YAML) for misconfigurations.

### Policy Checks

Ensures cloud resources comply with security policies.

Examples:
- No public S3 buckets
- Encrypted storage
- Restricted security groups

### Compliance Controls

Verifies compliance with standards such as:
- ISO 27001
- SOC 2
- PCI DSS
- HIPAA

---

# 📊 Monitor Stage

After deployment, continuous monitoring helps detect suspicious activities.

Includes:
- Security Audits
- Log Monitoring
- Alerts
- Incident Detection
- Continuous Compliance

---

# 🐍 Python Practice Projects

Today, I completed multiple Python practice projects to strengthen my programming fundamentals.

Skills practiced:
- Functions
- Classes
- File Handling
- Automation
- Problem Solving

---

# 📜 Shell Script - Security Scanner

Created a shell script that automates repository security checks.

### Features

- Scan repository using GitLeaks
- Scan filesystem using Trivy
- Display vulnerability summary
- Generate reports

Example:

```bash
#!/bin/bash

echo "Running GitLeaks Scan..."
gitleaks detect

echo "Running Trivy Scan..."
trivy fs .

echo "Security Scan Completed."
```

Run the script:

```bash
chmod +x security_scan.sh
./security_scan.sh
```

---

# 🔐 GitLeaks

Used to detect leaked secrets inside Git repositories.

```bash
gitleaks detect
```

---

# 🛡️ Trivy

Scans:
- File Systems
- Docker Images
- Kubernetes
- Git Repositories

```bash
trivy fs .
```

---

# 💼 Interview Preparation

Revised commonly asked DevOps interview topics including:

- Linux Basics
- Git Commands
- Git Branching
- AWS Fundamentals
- IAM
- EC2
- Networking Basics
- DevSecOps Concepts

---

# 🎯 Key Takeaways

- Understood the complete DevSecOps architecture.
- Learned where different security tools fit into the CI/CD pipeline.
- Practiced Python through mini-projects.
- Built a shell script to automate vulnerability and secret scanning.
- Revised core DevOps interview questions.

---

# 📈 Progress

- ✅ Day 13 – DevSecOps Pipeline, Security Automation & Python Practice

**Completed:** 13 / 90 Days 🚀

---

> **"Security is everyone's responsibility. Automating it makes software faster, safer, and more reliable."** 🔐🚀