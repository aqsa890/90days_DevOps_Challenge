# 🐳 Day 20 - 3-Tier Microservices with Docker

## 📅 Date

03 August 2026

---

# 🚀 Introduction

"Hands-on practice is where real learning happens. 🐳🚀"

Today, I worked on a 3-tier microservices application using Docker and focused on both deployment and security. A 3-tier architecture is a well-established software application architecture that organizes applications into three logical and physical computing tiers: the presentation tier (frontend), the application tier (backend), and the data tier (database).

Today's hands-on session gave me practical experience in containerizing applications and understanding how security fits into the container lifecycle.

---

# 📚 Topics Covered

## 🐳 1. Dockerizing Frontend, Backend & Database Services

Containerizing a 3-tier application means taking each tier and packaging it into its own isolated environment (container). 
- **Frontend**: A React or Vanilla JS application served via a web server like Nginx.
- **Backend**: An API built in Node.js, Python, or Golang.
- **Database**: A database engine like PostgreSQL, MySQL, or MongoDB.

By splitting these services into separate containers, we ensure they can scale independently and are easier to manage and deploy.

## 📄 2. Creating Dockerfiles for Each Service

To run our services in Docker, we need instructions. This is done via `Dockerfile`.

**Example: Backend Node.js Dockerfile**
```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

**Example: Database (using official image)**
Instead of a Dockerfile, databases are often instantiated directly from the official images (e.g., `postgres:15-alpine`) using Docker network commands or Docker Compose.

## 🖼️ 3. Building Docker Images & Running Containers

Once the `Dockerfile` is ready, the next step is building the image and running the container.

```bash
# Build the backend image
docker build -t my-backend:v1 .

# Run the container
docker run -d --name backend-server -p 3000:3000 my-backend:v1
```

## 🌐 4. Connecting Containers Through a Docker Network

For the backend to talk to the database, and the frontend to talk to the backend, they need to be on the same network.

```bash
# Create a custom bridge network
docker network create my-app-network

# Run the database on the network
docker run -d --name db-server --network my-app-network -e POSTGRES_PASSWORD=secret postgres:15-alpine

# Run the backend on the network
docker run -d --name backend-server --network my-app-network -e DB_HOST=db-server my-backend:v1
```

## 🔄 5. Container-to-Container Communication

Thanks to Docker's internal DNS resolution on custom bridge networks, containers can communicate with each other using their container names as hostnames. For example, the backend can reach the database at `postgres://user:secret@db-server:5432/db`.

## 🔍 6. Scanning Images with Docker Scout

Security should not be an afterthought. Docker Scout analyzes image contents and generates a detailed report of packages and vulnerabilities.

```bash
# Analyze image for vulnerabilities
docker scout cves my-backend:v1
```

## 🛡️ 7. Identifying and Reducing Image Vulnerabilities

Best practices for reducing vulnerabilities include:
1. **Use Minimal Base Images**: Prefer `alpine` or `distroless` images. They have fewer OS packages, resulting in a smaller attack surface.
2. **Keep Base Images Updated**: Frequently pull the latest base images to patch known vulnerabilities.
3. **Run as Non-Root**: Avoid running applications as the root user within the container.

---

# 🔗 LinkedIn Post

Hands-on practice is where real learning happens. 🐳🚀

Day 20 of #90DaysOfDevOps ✅

Today, I worked on a 3-tier microservices application using Docker and focused on both deployment and security.

📚 Topics Covered:

🐳 Dockerizing Frontend, Backend & Database services 
📄 Creating Dockerfiles for each service 
🖼️ Building Docker Images & Running Containers 
🌐 Connecting containers through a Docker Network 
🔄 Container-to-container communication 
🔍 Scanning images with Docker Scout 
🛡️ Identifying and reducing image vulnerabilities using Docker best practices 

Today's hands-on session gave me practical experience in containerizing applications and understanding how security fits into the container lifecycle.

#90DaysOfDevOps #Docker #DevOps #DockerScout #ContainerSecurity #Microservices #CloudComputing #LearningInPublic #TrainWithShubham
