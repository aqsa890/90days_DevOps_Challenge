# 🛡️ Day 18 - SAST, SCA & SonarQube (Manual Code Analysis)

## 📅 Date

01 August 2026

---

# 🚀 Introduction

Today, I continued my DevSecOps journey by learning about **Static Application Security Testing (SAST)**, **Software Composition Analysis (SCA)**, and performing **manual code analysis using SonarQube**.

I learned how these security tools help developers identify vulnerabilities, code quality issues, and dependency risks early in the Software Development Life Cycle (SDLC), following the **Shift Left Security** approach.

---

# 📚 Topics Covered

- What is SAST?
- What is SCA?
- Shift Left Security
- SonarQube
- Manual Code Analysis
- Code Smells
- Bugs
- Vulnerabilities
- Security Hotspots
- Quality Gates
- Code Coverage
- Technical Debt

---

# 🔐 Shift Left Security

Shift Left Security means integrating security checks **early** in the software development lifecycle rather than waiting until deployment.

```text
Traditional Approach

Develop
     │
     ▼
Test
     │
     ▼
Deploy
     │
     ▼
Security ❌


Shift Left

Develop
     │
     ▼
Security ✅
     │
     ▼
Test
     │
     ▼
Deploy
```

### Benefits

- Detect issues early
- Lower fixing costs
- Improve code quality
- Faster releases
- More secure applications

---

# 🔍 What is SAST?

**Static Application Security Testing (SAST)** scans the application's **source code** without executing it.

It helps identify security issues during development.

### Detects

- SQL Injection
- Cross-Site Scripting (XSS)
- Hardcoded Secrets
- Weak Authentication Logic
- Buffer Overflow
- Insecure Coding Practices

### Advantages

- Finds vulnerabilities early
- Faster feedback
- Easy CI/CD integration
- Improves secure coding practices

---

# 📦 What is SCA?

**Software Composition Analysis (SCA)** scans third-party libraries and open-source dependencies for known vulnerabilities.

Most modern applications rely heavily on external packages, making dependency scanning essential.

### Detects

- Outdated libraries
- Vulnerable packages
- License compliance issues
- Dependency risks

### Example

```text
Application
      │
      ▼
Dependencies

├── Spring Boot
├── Express.js
├── Flask
├── React
└── Log4j

↓

SCA scans these packages for known CVEs.
```

---

# 🛠️ SonarQube

SonarQube is a popular platform for continuous inspection of code quality and security.

It analyzes source code and generates detailed reports covering security, maintainability, and reliability.

### SonarQube Can Detect

- Bugs
- Vulnerabilities
- Code Smells
- Duplicate Code
- Security Hotspots
- Technical Debt

---

# 🔎 Manual Code Analysis with SonarQube

Today, I performed manual code analysis using SonarQube.

### Typical Workflow

1. Start SonarQube Server
2. Create a Project
3. Generate a Project Token
4. Run Sonar Scanner
5. Upload Results
6. Review Dashboard
7. Fix Reported Issues

---

# 📊 SonarQube Dashboard Metrics

## 🐞 Bugs
Issues that may cause incorrect application behavior.

---

## 🔐 Vulnerabilities
Security weaknesses that attackers could exploit.

---

## ⚠️ Code Smells
Poor coding practices that reduce maintainability.

Examples:

- Long Methods
- Duplicate Code
- Unused Variables
- Complex Functions

---

## 🔥 Security Hotspots

Potentially risky code that requires manual review.

Example:

```java
String password = request.getParameter("password");
```

This isn't necessarily a vulnerability but should be reviewed.

---

## 📈 Code Coverage

Shows how much of the code is covered by automated tests.

Higher coverage generally improves confidence in code quality.

---

## 🧾 Technical Debt

Represents the estimated effort required to fix maintainability issues in the codebase.

---

# 🚦 Quality Gates

Quality Gates define the minimum quality standards before code can be merged or deployed.

Common checks include:

- No critical vulnerabilities
- No blocker bugs
- Minimum code coverage
- No duplicated code beyond threshold

If the project fails the Quality Gate, developers should resolve the issues before proceeding.

---

# 🎯 Why SAST + SCA + SonarQube?

Using these together provides better application security.

- **SAST** → Finds vulnerabilities in source code.
- **SCA** → Finds vulnerabilities in third-party dependencies.
- **SonarQube** → Improves code quality, maintainability, and security.

Together, they help build secure, reliable, and production-ready applications.

---

# 🎯 Key Takeaways

- Learned the purpose of SAST and how it scans source code.
- Understood SCA for dependency and open-source package analysis.
- Performed manual code analysis using SonarQube.
- Learned about Bugs, Vulnerabilities, Code Smells, Security Hotspots, and Technical Debt.
- Understood the importance of Quality Gates and Shift Left Security.

---

# 📈 Progress

- ✅ Day 18 – SAST, SCA & SonarQube (Manual Code Analysis)

**Completed:** 18 / 90 Days 🚀

---

> **"The best time to fix a security issue is before it reaches production. Shift left, secure early, and build with confidence."** 🔐🚀