# 🐳 Day 21 - Advanced Containerization: Multi-Stage Builds & Security

## 📅 Date

04 August 2026

---

# 🚀 Introduction

"Hands-on practice is where real learning happens. 🐳🚀"

Today, I took my containerization skills a step further by deploying a Golang & Vanilla JS full-stack application with a MariaDB database. Instead of just making it work, I focused heavily on **multi-stage builds, minimal image sizing, and security scanning**.

Containerizing applications is one thing, but making them lightweight, secure, and production-ready is where the real value lies! 🔐

---

# 📚 Key Highlights & Implementations

## 📄 1. Multi-Stage Dockerfile Strategy

In compiled languages like Golang, you don't need the Go compiler or the source code in your final production image—you only need the compiled binary. A multi-stage build solves this by using multiple `FROM` statements.

**Example Multi-Stage Dockerfile:**
```dockerfile
# Stage 1: Build Environment
FROM golang:1.21-alpine AS builder
WORKDIR /app
COPY . .
RUN go build -o main .

# Stage 2: Minimal Runtime Environment
FROM alpine:3.21
WORKDIR /app
COPY --from=builder /app/main .
EXPOSE 8080
CMD ["./main"]
```
By copying only the compiled binary (`main`) into the lightweight `alpine:3.21` runtime, we discard all build dependencies.

## ⚡ 2. Extreme Size Optimization

Using the multi-stage build strategy, I successfully squashed the final application image size down to an impressive **3.86MB**!
- A standard `golang` image can easily exceed 800MB.
- `golang:alpine` reduces it to around 300MB.
- A multi-stage build with a bare `alpine` runtime brings it down to just a few megabytes.

## 🔒 3. Security Hardening (Non-Root User)

By default, Docker containers run as the `root` user. If an attacker breaches the container, they gain root privileges inside it. To prevent this, we enforce non-root user permissions (`appuser:appgroup`) directly in the Dockerfile.

```dockerfile
# Inside the runtime stage
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser
```
Now, the application executes safely under an unprivileged account.

## 🔍 4. Vulnerability Auditing with Docker Scout

I integrated `Docker Scout` to scan images and detect potential vulnerabilities before they reach production. Scout compares the layers and dependencies against a constantly updated vulnerability database (CVEs).

```bash
# Get a quick vulnerability summary
docker scout quickview my-golang-app:latest
```

## 🌐 5. Full-Stack Connectivity

Connected the Go backend, static frontend, and MariaDB server seamlessly into an active running container environment using a shared Docker network, ensuring the frontend could dynamically query the database via the secure Go API.

---

# 🔗 Resources

- **Project Code & Configuration:** [GitHub Repository](https://lnkd.in/dQ7z8-C8)

---

# 🔗 LinkedIn Post

Hands-on practice is where real learning happens. 🐳🚀
Day 21 of #90DaysOfDevOps ✅

Today, I took my containerization skills a step further by deploying a Golang & Vanilla JS full-stack application with a MariaDB database—focusing heavily on multi-stage builds, minimal image sizing, and security scanning.

📚 Key Highlights & Implementations:
📄 Multi-Stage Dockerfile Strategy: Configured multi-stage builds using golang:1.21-alpine for compiling the binary and a minimal alpine:3.21 runtime to keep the footprint light.
⚡ Extreme Size Optimization: Successfully squashed the final application image size down to an impressive 3.86MB!
🔒 Security Hardening: Enforced non-root user permissions (appuser:appgroup) directly in the Dockerfile to follow strict container security standards.
🔍 Vulnerability Auditing: Ran image security scans using Docker Scout to detect and address potential vulnerabilities early in the cycle.
🌐 Full-Stack Connectivity: Connected the Go backend, static frontend, and MariaDB server seamlessly into an active running container environment.

Containerizing applications is one thing, but making them lightweight, secure, and production-ready is where the real value lies! 🔐

🔗 Explore the project code & configuration here: https://lnkd.in/dQ7z8-C8

#90DaysOfDevOps #Docker #Golang #DevOps #DockerScout #ContainerSecurity #Microservices #CloudComputing #LearningInPublic #TrainWithShubham
