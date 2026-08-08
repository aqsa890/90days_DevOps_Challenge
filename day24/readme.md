# 🚀 Day 24 - First Steps into CI/CD Automation with GitHub Actions

## 📅 Date

07 August 2026

---

# 🚀 Introduction

"Every push to a repository is an opportunity to automate, validate, and improve software quality. 🚀"
 
Day 24 of #90DaysOfDevOps
 
Today, I took my first step into **Continuous Integration / Continuous Deployment (CI/CD)** automation by building a GitHub Actions workflow for a Node.js application. Instead of manually checking whether my application builds correctly, I automated the validation process using GitHub's built-in CI platform.

---

# 📚 What I Learned
 
## 🚀 1. GitHub Actions Fundamentals

CI/CD is a method to frequently deliver apps to customers by introducing automation into the stages of app development. 
- **Continuous Integration (CI)** automatically builds and tests code when changes are pushed.
- **Continuous Deployment (CD)** automatically deploys the validated code to a production environment.

**GitHub Actions Structure:**
- **Workflows**: Automated processes added to a repository. Defined in a `.yml` file in the `.github/workflows/` directory.
- **Events (Triggers)**: What causes a workflow to run (e.g., `push`, `pull_request`).
- **Jobs**: A set of steps that execute on the same runner. Jobs can run sequentially or in parallel.
- **Runners**: A server that runs your workflows (GitHub-hosted or self-hosted).
- **Steps**: Individual tasks that run commands or actions.

## ⚙️ 2. Created My First CI Pipeline

I created a CI pipeline to automatically test a Node.js application whenever code is pushed.

**Example: `.github/workflows/ci.yml`**
```yaml
name: Node.js CI

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    # Step 1: Check out the repository code onto the runner
    - name: Checkout code
      uses: actions/checkout@v4

    # Step 2: Set up Node.js
    - name: Use Node.js 18
      uses: actions/setup-node@v4
      with:
        node-version: 18

    # Step 3: Install dependencies
    - name: Install dependencies
      run: npm install

    # Step 4: Run basic validation/tests
    - name: Run tests
      run: npm test
```
This simple file completely eliminates the "it works on my machine" problem by verifying the application builds on a fresh Ubuntu environment every single time.

## 📊 3. Workflow Execution

Watching each stage execute successfully in the GitHub UI—from repository checkout to dependency installation and server validation—gave me a clear understanding of how CI pipelines automate repetitive development tasks. If a test fails, the developer gets an immediate alert, and the code won't be merged!

---

# 💡 Key Takeaway
 
CI/CD isn't just about automation—it's about building **confidence** in every code change. Even a simple workflow helps ensure that every commit is validated before moving further in the development lifecycle.
 
Looking forward to expanding this pipeline with testing, Docker image builds, security scanning, and automated deployments in the coming days.

---

# 🔗 Resources

- **GitHub Repository:** [Project Repo](https://lnkd.in/dfK96iiQ)

---

# 🔗 LinkedIn Post

"Every push to a repository is an opportunity to automate, validate, and improve software quality. 🚀"
 
Day 24 of #90DaysOfDevOps
 
Today, I took my first step into CI/CD automation by building a GitHub Actions workflow for a Node.js application. Instead of manually checking whether my application builds correctly, I automated the validation process using GitHub's built-in CI platform.
 
📚 What I Learned
 
🚀 GitHub Actions Fundamentals
- What CI/CD is and why it's important 
- Workflows, Jobs, Runners, Events, and Steps 
- Understanding GitHub-hosted runners 
 
⚙️ Created My First CI Pipeline
- Triggered automatically on push and pull requests 
- Checked out the repository using actions/checkout 
- Set up Node.js 18 using actions/setup-node 
- Installed project dependencies with npm install 
- Performed a basic server validation to ensure the application starts successfully 
 
📊 Workflow Execution
Watching each stage execute successfully—from repository checkout to dependency installation and server validation—gave me a clear understanding of how CI pipelines automate repetitive development tasks.
 
💡 Key Takeaway
 
CI/CD isn't just about automation—it's about building confidence in every code change. Even a simple workflow helps ensure that every commit is validated before moving further in the development lifecycle.
 
📂 GitHub Repository:
https://lnkd.in/dfK96iiQ
 
Looking forward to expanding this pipeline with testing, Docker image builds, security scanning, and automated deployments in the coming days.
 
#90DaysOfDevOps #GitHubActions #CI #CD #CICD #DevOps #Automation #NodeJS #GitHub #SoftwareEngineering #CloudComputing #LearningInPublic #TrainWithShubham
