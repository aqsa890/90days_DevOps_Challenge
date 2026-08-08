# 🚀 Day 25 - End-to-End Multi-Tier Deployment Pipeline

## 📅 Date

08 August 2026

---

# 🚀 Introduction

"A containerized application is only as good as its deployment pipeline. True automation means bridging code, containers, and cloud with zero manual steps. 🚀"

Day 25 of #90DaysOfDevOps

Today, I took my CI/CD journey to the next level by building an **end-to-end multi-tier deployment pipeline**. Instead of simply validating code, this pipeline now handles the complete journey:

**Code → Test → Build → Push to Docker Hub → Deploy to AWS EC2 → Production**

---

# 📚 What I Learned
 
## 📦 1. Containerization & Orchestration
Wired a multi-tier application (React frontend, Go backend, and Postgres database) using Docker and Docker Compose. This involved:
- Setting up the correct `docker-compose.yml` to be used in production.
- Using environment variable overrides passed securely from GitHub Actions to the EC2 server.

## ⚙️ 2. Reusable Workflows & Security
Instead of writing one massive `main.yml` file, I designed modular GitHub Actions pipelines using **reusable workflows**.
- `ci.yml`: Runs tests and linters.
- `docker.yml`: Builds images and pushes them to Docker Hub.
- `cd.yml`: SSHs into the server and deploys the new images.

I used `secrets: inherit` to securely pass Docker Hub credentials (like `DOCKER_USERNAME` and `DOCKER_PASSWORD`) down through the nested workflow jobs.

**Example snippet calling a reusable workflow:**
```yaml
jobs:
  build-and-push:
    uses: ./.github/workflows/docker.yml
    secrets: inherit
```

## ☁️ 3. Continuous Deployment (CD) on AWS EC2
Deploying to AWS required a robust script to handle the environment. 
- **Self-Hosted / Remote Runner Execution**: The CD pipeline securely connects to the AWS EC2 instance.
- **Automated Bootstrap Script**: The pipeline runs a script to install Docker and Docker Compose on the host VM if they aren't already present.
- **Silent Installations**: I prevented interactive prompts (like Ubuntu's `needrestart`) from hanging CI runs by setting `DEBIAN_FRONTEND=noninteractive` and environment flags under `sudo -E`.

**Deploy Script Logic (Snippet):**
```bash
# Pull the latest images from Docker Hub
docker compose pull

# Restart the services with the new images in detached mode
docker compose up -d
```
Instead of performing heavy, resource-intensive local compilation on a cheap/resource-limited EC2 VM, the EC2 instance simply pulls the pre-built `latest` tags from Docker Hub. This optimization is crucial for production speed.

## 📊 4. Workflow Execution
Watching the workflow run was incredibly satisfying! The pipeline successfully ran lints/tests, pushed multi-stage frontend and backend images to Docker Hub, booted up/updated Docker on the EC2 runner, and updated the production stack with a single `docker compose up -d` in under a minute.

---

# 💡 Key Takeaway
 
Building a pipeline isn't just about making it work; it's about making it resilient and optimized. Shifting the build phase to GitHub's cloud runners and pulling pre-built images onto AWS EC2 turned what would have been a 30-minute compilation bottleneck into a 10-second deployment.

Looking forward to expanding this setup with SSL/TLS configurations, reverse proxy setups, and monitoring tools in the next phase!

---

# 🔗 Resources

- **GitHub Repository:** [Project Repo](https://lnkd.in/d5PdNcUc)

---

# 🔗 LinkedIn Post

"A containerized application is only as good as its deployment pipeline. True automation means bridging code, containers, and cloud with zero manual steps. 🚀"
🚀 Day 25 of #90DaysOfDevOps
Today, I took my CI/CD journey to the next level by building an end-to-end multi-tier deployment pipeline. Instead of simply validating code, this pipeline now handles the complete journey:

Code → Test → Build → Docker Images → Docker Hub → AWS EC2 → Production

📚 What I Learned
📦 Containerization & Orchestration
Wiring a multi-tier application (React frontend, Go backend, and Postgres database) using Docker and Docker Compose.
Understanding environment variable overrides and network isolation between containers.
⚙️ Reusable Workflows & Security
Designing modular GitHub Actions pipelines using reusable workflows (ci.yml calling docker.yml calling cd.yml).
Using secrets: inherit to securely pass Docker Hub credentials down through nested workflow jobs.
Upgrading build runtime parameters (Node.js 22) to avoid runner deprecation warnings.
☁️ Continuous Deployment (CD) on AWS EC2
Deploying on a self-hosted GitHub Actions runner running on an AWS EC2 instance.
Building an automated bootstrap script to install Docker and Docker Compose on the host VM if not already present.
Preventing interactive prompts (like Ubuntu's needrestart) from hanging CI runs by setting DEBIAN_FRONTEND=noninteractive and environment flags under sudo -E.
Optimizing deployment speeds by pulling pre-built tags (IMAGE_TAG=latest) from Docker Hub instead of performing heavy local compilation on a resource-limited EC2 VM.
📊 Workflow Execution
Watching the workflow run was incredibly satisfying! The pipeline successfully ran lints/tests, pushed multi-stage frontend and backend images to Docker Hub, booted up/updated Docker on the EC2 runner, and updated the production stack with a single docker compose up -d in under a minute.

💡 Key Takeaway
Building a pipeline isn't just about making it work; it's about making it resilient and optimized. Shifting the build phase to GitHub's cloud runners and pulling pre-built images onto AWS EC2 turned what would have been a 30-minute compilation bottleneck into a 10-second deployment.

📂 GitHub Repository: https://lnkd.in/d5PdNcUc
Looking forward to expanding this setup with SSL/TLS configurations, reverse proxy setups, and monitoring tools in the next phase!

#90DaysOfDevOps #GitHubActions #Docker #DockerCompose #AWS #EC2 #CI #CD #DevOps #Automation #ReactJS #Golang #SoftwareEngineering #CloudComputing #LearningInPublic #TrainWithShubham
