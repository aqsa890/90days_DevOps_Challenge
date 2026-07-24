# 🔐 Day 11 - DevSecOps Fundamentals, OWASP Threat Dragon & GitHub Secrets

## 📅 Date

25 July 2026

---

# 🚀 Introduction

Today, I stepped into the world of **DevSecOps**, where security is integrated into every stage of the software development lifecycle instead of being treated as an afterthought.

I learned about **threat modeling**, **secret management**, **vulnerability scanning**, and best practices for securing Git repositories and applications.

---

# 📚 Topics Covered

- OWASP Threat Dragon
- AI for Threat Modeling & Risk Mitigation
- `.gitignore`
- `.env` Files
- GitLeaks
- Trivy
- Vulnerabilities & Security Issues
- GitHub Secrets
- GitHub Environment Variables

---

# 🛡️ What is DevSecOps?

**DevSecOps** stands for:

- **Dev** → Development
- **Sec** → Security
- **Ops** → Operations

The goal is to integrate **security into every phase** of software development instead of checking security only before deployment.

### Benefits

- Early vulnerability detection
- Secure CI/CD pipelines
- Reduced security risks
- Faster and safer deployments

---

# 🐉 OWASP Threat Dragon

**OWASP Threat Dragon** is an open-source threat modeling tool that helps identify security risks during the application design phase.

Instead of finding vulnerabilities after deployment, Threat Dragon helps developers think about possible attacks while designing the system.

---

## Why Use Threat Dragon?

- Identify security threats early
- Visualize application architecture
- Generate threat models
- Improve secure system design
- Reduce security vulnerabilities

---

## Basic Workflow

```text
Application Architecture
          │
          ▼
Threat Modeling
          │
          ▼
Identify Risks
          │
          ▼
Suggest Mitigations
          │
          ▼
Secure Application Design
```

---

# 🤖 Using AI for Threat Modeling

AI can assist in security analysis by:

- Identifying possible attack vectors
- Suggesting security controls
- Prioritizing vulnerabilities
- Generating mitigation plans
- Creating security documentation

Example:

Instead of manually analyzing an API, AI can recommend:

- Authentication
- Authorization
- Input Validation
- Encryption
- Rate Limiting

---

# 📄 .gitignore

The `.gitignore` file tells Git which files and folders should **not** be tracked.

Example:

```gitignore
.env
node_modules/
*.log
__pycache__/
venv/
```

### Why Use `.gitignore`?

- Prevent committing sensitive files
- Ignore temporary files
- Keep repositories clean
- Reduce repository size

---

# 🔐 .env File

A `.env` file stores sensitive configuration values.

Example

```env
DATABASE_URL=mysql://localhost
AWS_ACCESS_KEY=xxxxxxxx
AWS_SECRET_KEY=xxxxxxxx
API_KEY=xxxxxxxx
```

### Why use `.env`?

- Keeps secrets separate from source code
- Easy configuration across environments
- Prevents accidental exposure

⚠️ Never commit your `.env` file to GitHub.

---

# 🔍 GitLeaks

GitLeaks is an open-source security tool that scans Git repositories for leaked secrets.

It can detect:

- AWS Keys
- GitHub Tokens
- API Keys
- Passwords
- SSH Keys
- Database Credentials

### Install

```bash
brew install gitleaks
```

### Scan Repository

```bash
gitleaks detect
```

### Benefits

- Prevents secret leaks
- Improves repository security
- Can be integrated into CI/CD

---

# 🛡️ Trivy

**Trivy** is an open-source vulnerability scanner.

It scans:

- Docker Images
- Git Repositories
- Kubernetes
- File Systems
- Infrastructure as Code (IaC)

---

## Install

```bash
brew install trivy
```

---

## Scan a Docker Image

```bash
trivy image nginx:latest
```

---

## Scan Current Directory

```bash
trivy fs .
```

---

## Why Trivy?

- Detect vulnerabilities
- Scan secrets
- Scan misconfigurations
- Generate security reports

---

# 🚨 What are Vulnerabilities?

A vulnerability is a weakness in software, systems, or infrastructure that attackers can exploit.

Examples include:

- Weak passwords
- Outdated software
- SQL Injection
- Cross-Site Scripting (XSS)
- Hardcoded secrets
- Misconfigured permissions
- Unpatched operating systems

---

# 🔐 GitHub Secrets

GitHub Secrets securely store sensitive information used in GitHub Actions workflows.

Examples:

- AWS Access Keys
- API Keys
- Docker Credentials
- Database Passwords

Example:

```yaml
${{ secrets.AWS_ACCESS_KEY_ID }}
```

### Benefits

- Encrypted storage
- Hidden in workflow logs
- Secure CI/CD authentication

---

# 🌍 GitHub Environment Variables

Environment Variables store non-sensitive configuration values.

Example:

```yaml
env:
  APP_NAME: DevOpsApp
  ENVIRONMENT: Production
```

Access in GitHub Actions:

```yaml
echo $APP_NAME
```

### Difference Between Secrets & Environment Variables

| GitHub Secrets | Environment Variables |
|----------------|-----------------------|
| Encrypted | Plain text |
| Used for sensitive data | Used for configuration |
| Hidden in logs | Visible if printed |
| API Keys, Tokens | App Name, Environment |

---

# 🔒 Security Best Practices

- Never commit `.env` files.
- Use `.gitignore` for sensitive files.
- Store credentials in GitHub Secrets.
- Regularly scan repositories with GitLeaks.
- Scan images and files with Trivy.
- Perform threat modeling before development.
- Rotate credentials periodically.
- Follow the Principle of Least Privilege (PoLP).

---

# 🎯 Key Takeaways

- Learned the basics of DevSecOps.
- Explored OWASP Threat Dragon for threat modeling.
- Understood how AI can assist in identifying risks and suggesting mitigations.
- Learned the purpose of `.gitignore` and `.env` files.
- Used GitLeaks to detect leaked secrets.
- Learned how Trivy scans for vulnerabilities and misconfigurations.
- Understood common software security vulnerabilities.
- Explored GitHub Secrets and Environment Variables for secure configuration management.

---

# 📈 Progress

- ✅ Day 11 – DevSecOps Fundamentals, OWASP Threat Dragon & GitHub Security

**Completed:** 11 / 90 Days 🚀

---

> **"Security is not a feature you add at the end—it's a mindset you build from the beginning."** 🔐