# 🐳 Day 19 - Advanced Docker: Multi-Stage Builds, Volumes & Networking

## 📅 Date

02 August 2026

---

# 🚀 Introduction

Today, I explored advanced Docker concepts that are widely used in production environments. I learned how to optimize Docker images using **Multi-Stage Builds**, persist application data using **Docker Volumes**, understand **Volume Mounting** for databases, and configure different **Docker Network Drivers** for container communication. I also got introduced to **Docker Swarm**, Docker's native container orchestration platform.

---

# 📚 Topics Covered

## 🐳 Docker Advanced
- Multi-Stage Dockerfile
- Builder Stage
- Runner Stage
- Docker Volumes
- Volume Mounting
- Persistent Storage
- Docker Networks
- Bridge Network
- User-defined Bridge
- Host Network
- None Network
- Overlay Network
- Macvlan Network
- IPvlan Network
- Docker Swarm

---

# 🏗️ What is a Multi-Stage Docker Build?

A **Multi-Stage Build** allows you to use multiple `FROM` statements in a single Dockerfile.

It helps create **smaller, cleaner, and production-ready Docker images** by separating the build environment from the runtime environment.

### Benefits

- Smaller image size
- Faster deployments
- Better security
- Removes unnecessary build tools
- Optimized production images

---

# 🔨 Builder Stage

The **Builder Stage** contains everything required to build the application.

Example:

- Source Code
- Dependencies
- Build Tools
- Compilers

Example Dockerfile:

```dockerfile
FROM node:20 AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build
```

---

# 🚀 Runner Stage

The **Runner Stage** contains only the files required to run the application.

```dockerfile
FROM nginx:latest

COPY --from=builder /app/build /usr/share/nginx/html
```

This significantly reduces the final image size.

---

# 📦 Complete Multi-Stage Dockerfile Example

```dockerfile
# Builder Stage
FROM node:20 AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

# Runner Stage
FROM nginx:latest

COPY --from=builder /app/build /usr/share/nginx/html

EXPOSE 80

CMD ["nginx","-g","daemon off;"]
```

---

# 💾 Docker Volumes

Docker Volumes provide **persistent storage** for containers.

Without volumes:

```
Container Deleted

↓

All Data Lost
```

With volumes:

```
Container Deleted

↓

Volume Remains

↓

Data Preserved
```

---

# Why Use Docker Volumes?

- Persistent Data
- Database Storage
- Data Backup
- Share Data Between Containers
- Better Performance

---

# Create a Volume

```bash
docker volume create my-volume
```

View Volumes

```bash
docker volume ls
```

Inspect Volume

```bash
docker volume inspect my-volume
```

Remove Volume

```bash
docker volume rm my-volume
```

---

# Mount a Volume

```bash
docker run -d \
-v my-volume:/app/data \
nginx
```

---

# Using Volumes with Databases

## PostgreSQL

```bash
docker run -d \
--name postgres-db \
-v postgres-data:/var/lib/postgresql/data \
postgres
```

---

## MySQL

```bash
docker run -d \
--name mysql-db \
-v mysql-data:/var/lib/mysql \
mysql
```

---

## MongoDB

```bash
docker run -d \
--name mongo-db \
-v mongo-data:/data/db \
mongo
```

Volumes ensure database data is retained even if the container is removed.

---

# 🌐 Docker Networking

Docker Networks allow containers to communicate securely with each other and external systems.

---

# Types of Docker Networks

## 1️⃣ Bridge Network (Default)

Default network for standalone containers.

```bash
docker network ls
```

---

## 2️⃣ User-defined Bridge

A custom bridge network that provides automatic DNS resolution between containers.

Create:

```bash
docker network create my-network
```

Run container:

```bash
docker run --network my-network nginx
```

---

## 3️⃣ Host Network

The container shares the host machine's network stack.

```bash
docker run --network host nginx
```

Best for high-performance networking.

---

## 4️⃣ None Network

The container has no network connectivity.

```bash
docker run --network none nginx
```

Useful for isolated workloads.

---

## 5️⃣ Overlay Network

Used in **Docker Swarm** to connect containers running on different Docker hosts.

Supports multi-host communication.

---

## 6️⃣ Macvlan Network

Assigns a unique MAC address to each container.

Containers appear as physical devices on the network.

Best for:

- Legacy Applications
- Network Appliances

---

## 7️⃣ IPvlan Network

Similar to Macvlan but shares the parent MAC address while assigning unique IP addresses.

Benefits:

- Better scalability
- Lower network overhead

---

# 🐝 Docker Swarm

Docker Swarm is Docker's native container orchestration platform.

It allows multiple Docker hosts to work together as a cluster.

### Features

- High Availability
- Load Balancing
- Service Scaling
- Rolling Updates
- Fault Tolerance

Initialize Swarm:

```bash
docker swarm init
```

View Nodes:

```bash
docker node ls
```

Create a Service:

```bash
docker service create --name web nginx
```

List Services:

```bash
docker service ls
```

Scale Service:

```bash
docker service scale web=3
```

---

# 🎯 Key Takeaways

- Learned how Multi-Stage Dockerfiles create optimized production images.
- Understood the roles of Builder Stage and Runner Stage.
- Learned how Docker Volumes provide persistent storage.
- Practiced mounting volumes for PostgreSQL, MySQL, and MongoDB containers.
- Explored the seven Docker network drivers and their use cases.
- Got introduced to Docker Swarm for container orchestration and clustering.

---

# 📈 Progress

- ✅ Day 19 – Advanced Docker: Multi-Stage Builds, Volumes & Networking

**Completed:** 19 / 90 Days 🚀

---

> **"Containers make applications portable, but mastering storage, networking, and orchestration makes them production-ready."** 🐳🚀