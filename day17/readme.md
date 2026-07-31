# 🐳 Day 17 - Docker Fundamentals & AWS NoSQL Database

## 📅 Date

31 July 2026

---

# 🚀 Introduction

Today, I started learning **Docker**, one of the most important tools in the DevOps ecosystem. I learned why Docker was created, how it works internally, the difference between virtualization and containerization, Docker architecture, Docker images, containers, Dockerfile, Docker Hub, and essential Docker commands.

On the AWS side, I explored **NoSQL databases** and learned how to create a managed non-relational database.

---

# 📚 Topics Covered

## 🐳 Docker Fundamentals
- What is Docker?
- Why Docker?
- How Docker Works
- Virtualization
- Containerization
- Virtualization vs Containerization
- Docker Architecture
- Docker Client
- Docker Daemon
- containerd
- Docker Registry
- Docker Hub
- Dockerfile
- Docker Image
- Docker Container
- Installing Docker Desktop
- Installing Docker on AWS EC2
- Essential Docker Commands

## ☁️ AWS
- Non-Relational Database
- Amazon DynamoDB Basics

---

# 🐳 What is Docker?

Docker is an **open-source containerization platform** that allows developers to package an application along with all its dependencies into lightweight, portable containers.

This ensures the application runs consistently across different environments.

---

# ❓ Why Docker?

Before Docker:

- "It works on my machine" problems
- Dependency conflicts
- Difficult deployments
- Environment inconsistencies

Docker solves these issues by packaging everything required for an application into a single container.

### Benefits

- Lightweight
- Fast deployment
- Portability
- Consistent environments
- Easy scaling
- Better resource utilization

---

# ⚙️ How Docker Works

Docker uses the host operating system's kernel to run isolated containers.

Unlike virtual machines, Docker does not require a separate operating system for every application.

```text
Application
      │
Docker Container
      │
Docker Engine
      │
Host Operating System
      │
Hardware
```

---

# 🖥️ Virtualization

Virtualization creates **multiple virtual machines (VMs)** on a single physical server.

Each VM contains:

- Guest OS
- Libraries
- Dependencies
- Application

Example:

```text
Hardware
     │
Hypervisor
     │
 ├── VM 1
 ├── VM 2
 └── VM 3
```

### Advantages

- Strong isolation
- Multiple operating systems

### Disadvantages

- Heavy
- Slow startup
- High resource usage

---

# 📦 Containerization

Containerization packages applications with their dependencies while sharing the host operating system kernel.

Example:

```text
Hardware
     │
Host OS
     │
Docker Engine
     │
 ├── Container 1
 ├── Container 2
 └── Container 3
```

### Advantages

- Lightweight
- Fast startup
- Efficient resource usage
- Portable

---

# ⚖️ Virtualization vs Containerization

| Virtualization | Containerization |
|---------------|------------------|
| Uses Hypervisor | Uses Docker Engine |
| Each VM has its own OS | Containers share Host OS |
| Heavyweight | Lightweight |
| Slower | Faster |
| More resource consumption | Less resource consumption |

---

# 🏗️ Docker Architecture

Docker consists of several components:

### Docker Client

The command-line interface where users execute Docker commands.

Example:

```bash
docker run nginx
```

---

### Docker Daemon (`dockerd`)

The background service responsible for:

- Building Images
- Running Containers
- Managing Networks
- Managing Volumes

---

### containerd

A container runtime responsible for managing the lifecycle of containers.

Responsibilities:

- Pull Images
- Start Containers
- Stop Containers
- Delete Containers

---

### Docker Registry

A storage service for Docker images.

Examples:

- Docker Hub
- Amazon ECR
- GitHub Container Registry

---

# 🐙 Docker Hub

Docker Hub is the default public registry used to store and share Docker images.

Examples:

```bash
docker pull nginx
```

```bash
docker pull ubuntu
```

---

# 📄 Dockerfile

A Dockerfile is a text file containing instructions for building a Docker image.

Example:

```dockerfile
FROM ubuntu:22.04

RUN apt update

RUN apt install nginx -y

CMD ["nginx","-g","daemon off;"]
```

---

# 🖼️ Docker Image

A Docker Image is a read-only blueprint used to create Docker containers.

Build an image:

```bash
docker build -t myapp .
```

---

# 📦 Docker Container

A container is a running instance of a Docker image.

```text
Dockerfile
      │
docker build
      ▼
Docker Image
      │
docker run
      ▼
Docker Container
```

---

# 💻 Install Docker Desktop

1. Download Docker Desktop
2. Install the application
3. Start Docker Desktop
4. Verify installation

```bash
docker --version
```

---

# ☁️ Install Docker on Ubuntu EC2

Update packages

```bash
sudo apt update
```

Install Docker

```bash
sudo apt install docker.io -y
```

Start Docker

```bash
sudo systemctl start docker
```

Enable Docker

```bash
sudo systemctl enable docker
```

Verify

```bash
docker --version
```

---

# 🐳 Essential Docker Commands

### Check Docker Version

```bash
docker --version
```

---

### Docker Service Status

```bash
sudo systemctl status docker
```

---

### Search Image

```bash
docker search nginx
```

---

### Download Image

```bash
docker pull nginx
```

---

### List Images

```bash
docker images
```

---

### Run Container

```bash
docker run nginx
```

Interactive Mode

```bash
docker run -it ubuntu
```

Detached Mode

```bash
docker run -d nginx
```

Port Mapping

```bash
docker run -p 8080:80 nginx
```

Environment Variable

```bash
docker run -e APP_ENV=production nginx
```

TTY Allocation

```bash
docker run -t ubuntu
```

---

### Running Containers

```bash
docker ps
```

All Containers

```bash
docker ps -a
```

---

### Execute Commands

```bash
docker exec -it container_id bash
```

---

### Stop Container

```bash
docker stop container_id
```

---

### Kill Container

```bash
docker kill container_id
```

---

### Remove Container

```bash
docker rm container_id
```

---

### Remove Image

```bash
docker rmi image_name
```

---

# ☁️ AWS NoSQL Database

Today I also explored **Amazon DynamoDB**, AWS's fully managed NoSQL database service.

### What is DynamoDB?

Amazon DynamoDB is a serverless NoSQL database designed for high performance and scalability.

### Features

- Fully Managed
- Serverless
- High Availability
- Automatic Scaling
- Low Latency

---

# Relational vs Non-Relational Database

| Relational Database | NoSQL Database |
|---------------------|----------------|
| Tables | Key-Value / Document |
| Fixed Schema | Flexible Schema |
| SQL | NoSQL |
| Example: MySQL | Example: DynamoDB |

---

# Steps to Create a DynamoDB Table

1. Login to AWS Console
2. Open **DynamoDB**
3. Click **Create Table**
4. Enter Table Name
5. Define Partition Key
6. Configure Capacity Mode
7. Create Table

---

# 🎯 Key Takeaways

- Learned Docker fundamentals and containerization.
- Understood the difference between virtualization and containers.
- Explored Docker architecture (Client, Daemon, containerd, Registry).
- Learned how Dockerfiles build images that run as containers.
- Practiced essential Docker commands.
- Installed Docker on an Ubuntu EC2 instance.
- Learned about Docker Hub and public image repositories.
- Explored Amazon DynamoDB as a managed NoSQL database service.

---

# 📈 Progress

- ✅ Day 17 – Docker Fundamentals & AWS NoSQL Database

**Completed:** 17 / 90 Days 🚀

---

> **"Containers package applications, but understanding how they work is what transforms a developer into a DevOps engineer."** 🐳🚀