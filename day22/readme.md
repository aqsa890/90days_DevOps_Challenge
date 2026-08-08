# 🐙 Day 22 - Docker Compose Orchestration

## 📅 Date

05 August 2026

---

# 🚀 Introduction

Day 22 of #90DaysOfDevOps ✅

Today, I moved beyond individual Docker commands and took full orchestration to the next level by building a multi-container environment for DevBoard using **Docker Compose**! 

Instead of manually starting containers, configuring networks, and running separate terminal commands, I configured a robust, production-ready `docker-compose.yml` file to handle service orchestration, environment variables, dependencies, and health checks seamlessly.

Automating multi-container orchestration with proper health checks and startup ordering makes local development predictable and mirroring production environments effortless! 🛠️

---

# 📚 Key Highlights & Implementations

## 🐙 1. Multi-Service Orchestration
I orchestrated a 3-tier setup featuring a PostgreSQL 16 Alpine database, a Golang backend, and a frontend application. With a single command (`docker compose up -d`), Docker Compose automatically provisions the network, builds the images, and starts all three services in the correct order.

## 🩺 2. Robust Health Checks & Dependencies
When a database container starts, it might take several seconds before it is ready to accept connections. If the backend tries to connect instantly, it will crash. 

To solve this, I implemented explicit health checks using `pg_isready` for Postgres and `wget` endpoints for the application services.

```yaml
  db:
    image: postgres:16-alpine
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U ${POSTGRES_USER}"]
      interval: 5s
      timeout: 5s
      retries: 5

  backend:
    depends_on:
      db:
        condition: service_healthy
```
This ensures the backend **only** connects when the database is strictly ready!

## 🔐 3. Environment Variables & Security
Hardcoding credentials inside `docker-compose.yml` is a major security risk. Instead, I configured dynamic environment variables (`${POSTGRES_USER}`, `${POSTGRES_PASSWORD}`, `${POSTGRES_URL}`) sourced from an external `.env` file. This keeps secrets safe and allows for easy configuration swaps between environments (Dev, Staging, Prod).

## 🔒 4. Hardened Base Images
Integrated distro-less runtime bases (`cgr.dev/chainguard/static`) in the multi-stage Go build process. Distroless images contain only your application and its runtime dependencies. They do not contain package managers, shells, or any other programs you would expect to find in a standard Linux distribution, massively minimizing attack vectors and shrinking image footprints.

## 💾 5. Data Persistence
Containers are ephemeral—if they are destroyed, all data inside them is lost. To preserve the database data across container teardowns and restarts, I defined **named volumes**.

```yaml
volumes:
  postgres_data:

services:
  db:
    volumes:
      - postgres_data:/var/lib/postgresql/data
```

## 🧪 6. End-to-End Testing
Tested and verified backend health endpoints (`/health` returning 200 OK) and frontend accessibility using `curl` requests directly from the terminal to ensure the orchestration was successful.

---

# 🔗 Resources

- **Explore the code & deployment setup:** [GitHub Repository](https://lnkd.in/dX8Cftq5)

---

# 🔗 LinkedIn Post

Day 22 of #90DaysOfDevOps ✅
Today, I moved beyond individual Docker commands and took full orchestration to the next level by building a multi-container environment for DevBoard using Docker Compose!
Instead of manually starting containers, configuring networks, and running separate terminal commands, I configured a robust, production-ready docker-compose.yml file to handle service orchestration, environment variables, dependencies, and health checks seamlessly.

📚 Key Highlights & Implementations:
🐙 Multi-Service Orchestration: Orchestrated a 3-tier setup featuring a PostgreSQL 16 Alpine database, a Golang backend, and a frontend application with a single command (docker compose up -d).
🩺 Robust Health Checks & Dependencies: Implemented explicit health checks using pg_isready for Postgres and wget endpoints for the application services. Leveraged depends_on with condition: service_healthy to ensure backend only connects when the database is strictly ready!
🔐 Environment Variables & Security: Configured dynamic environment variables (${POSTGRES_USER}, ${POSTGRES_PASSWORD}, ${POSTGRES_URL}) to keep secrets out of hardcoded configurations.
🔒 Hardened Base Images: Integrated distro-less runtime bases (cgr.dev/chainguard/static) in the multi-stage Go build process to minimize attack vectors and shrink image footprints.
💾 Data Persistence: Defined named volumes (postgres_data) to prevent data loss across container teardowns and restarts.
🧪 End-to-End Testing: Tested and verified backend health endpoints (/health returning 200 OK) and frontend accessibility using curl requests directly from the terminal.

Automating multi-container orchestration with proper health checks and startup ordering makes local development predictable and mirroring production environments effortless! 🛠️

🔗 Explore the code & deployment setup here: https://lnkd.in/dX8Cftq5

#90DaysOfDevOps #Docker #DockerCompose #Golang #PostgreSQL #DevOps #Containerization #BackendDevelopment #CloudComputing #LearningInPublic #TrainWithShubham
