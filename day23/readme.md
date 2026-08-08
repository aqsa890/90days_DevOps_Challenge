# 🛡️ Day 23 - Containerizing Microservices & DevSecOps Best Practices

## 📅 Date

06 August 2026

---

# 🚀 Introduction

"Security and optimization are not optional in DevOps—they are fundamental to building scalable, reliable, and production-ready applications." 🚀
 
Day 23 of #90DaysOfDevOps
 
Today's session was focused on containerizing a microservices-based application while following modern Docker and **DevSecOps best practices**. The goal wasn't just to get the application running, but to build lean, secure, and maintainable container images from the ground up.

---

# 📚 What I Worked On
 
## 🐳 1. Containerized Multiple Microservices
Unlike a monolithic application where everything runs together, a microservices architecture splits functions into small, independent services.
- Built Docker images for: `sv-auth` (Authentication), `sv-tasks` (Task Management), `sv-notes` (Note Taking), and `sv-frontend` (UI).
- Created dedicated Dockerfiles for each individual service to ensure they can be updated and scaled completely independently of one another.
 
## ⚡ 2. Implemented Multi-Stage Docker Builds
To keep images small and secure:
- Used `Builder` and `Runner` stages to separate the build environment from the runtime environment. 
- By copying over only the compiled assets (like Python wheels or React static files) into the final stage, I successfully reduced the image size by excluding unnecessary build dependencies (like compilers, dev tools, and test libraries) from the final image. 
 
## 🛡️ 3. Image Hardening & Optimization
- **Backend Services:** Used lightweight Alpine Linux base images (`python:3.12-alpine`). Alpine is heavily stripped down, which significantly reduces the potential attack surface.
- **Frontend Serving:** Configured an **unprivileged NGINX image** (`nginxinc/nginx-unprivileged:1.27-alpine-slim`) for serving the frontend securely. Standard Nginx runs as root on port 80, which is dangerous. The unprivileged version runs as an unprivileged user on port 8080, entirely eliminating root-level escalation risks.
 
## 🔧 4. Dependency & Environment Management
- **OS Dependencies:** Installed required Linux packages using Alpine's `apk --no-cache` to prevent bloated cache files from expanding the image size.
- **Python Dependencies:** Configured Python virtual environments (`python -m venv`) inside the containers for strictly isolated dependency management. 
- **Layer Caching:** Ordered Dockerfile commands intelligently (copying `requirements.txt` and installing dependencies *before* copying the main source code) to optimize Docker layers for much faster rebuilds.
 
## ✅ 5. Testing Before Deployment
A core tenet of DevSecOps is validating code continuously:
- Integrated unit tests into the image build process itself using intermediate testing stages.
- Verified backend APIs (Authentication, Tasks, etc.) before the final production-ready images were generated. If the tests fail, the image doesn't build—preventing broken code from reaching the registry.

---

# 🎯 Key Takeaways
 
This hands-on project reinforced several critical DevOps principles:
1. **Build small and secure Docker images.** 
2. **Prefer minimal base images** (Alpine/Distroless) for production. 
3. **Run applications with non-root users** whenever technically possible. 
4. **Use multi-stage builds** to radically improve efficiency and security. 
5. **Validate applications through automated testing** before deployment. 
6. **Treat security and optimization as part of the development lifecycle**, not as a post-deployment afterthought. 

Every hands-on project deepens my understanding of how modern applications are built, secured, and deployed in real-world DevOps environments. Looking forward to exploring Kubernetes and taking these containers to the next level! 🚀

---

# 🔗 Resources

- **GitHub Repository:** [Project Repo](https://lnkd.in/dJD--sCK)

---

# 🔗 LinkedIn Post

"Security and optimization are not optional in DevOps—they are fundamental to building scalable, reliable, and production-ready applications." 🚀
 
Day 23 of #90DaysOfDevOps
 
Today's session was focused on containerizing a microservices-based application while following modern Docker and DevSecOps best practices. The goal wasn't just to get the application running, but to build lean, secure, and maintainable container images.
 
📚 What I Worked On
 
🐳 Containerized Multiple Microservices
- Built Docker images for: sv-auth, sv-tasks, sv-notes, sv-frontend
- Created dedicated Dockerfiles for each service
- Followed a modular microservices architecture
 
⚡ Implemented Multi-Stage Docker Builds
- Used Builder and Runner stages to separate the build environment from the runtime environment
- Reduced image size by excluding unnecessary build dependencies from the final image
 
🛡️ Image Hardening & Optimization
- Used lightweight Alpine Linux base images (python:3.12-alpine) for backend services
- Configured an unprivileged NGINX image (nginxinc/nginx-unprivileged:1.27-alpine-slim) for serving the frontend securely
- Reduced the attack surface while improving container performance
 
🔧 Dependency & Environment Management
- Installed required packages using Alpine's apk --no-cache to keep images clean
- Configured Python virtual environments for isolated dependency management
- Optimized Docker layers for faster builds and improved caching
 
✅ Testing Before Deployment
- Integrated unit tests into the build process
- Verified backend APIs (Authentication, Tasks, etc.) before creating production-ready images
- Reinforced the importance of validating code before deployment
 
🎯 Key Takeaways
This hands-on project reinforced several important DevOps principles:
- Build small and secure Docker images
- Prefer minimal base images for production
- Run applications with non-root users whenever possible
- Use multi-stage builds to improve efficiency
- Validate applications through automated testing before deployment
- Treat security and optimization as part of the development lifecycle, not as post-deployment tasks
 
📂 GitHub Repository:
🔗 https://lnkd.in/dJD--sCK
 
Every hands-on project deepens my understanding of how modern applications are built, secured, and deployed in real-world DevOps environments. Looking forward to exploring Kubernetes and taking these containers to the next level! 🚀
 
#90DaysOfDevOps #DevOps #Docker #Microservices #Containerization #DevSecOps #DockerSecurity #AlpineLinux #NGINX #Python #CloudComputing #SoftwareEngineering #LearningInPublic #GitHub #AWS #TrainWithShubham
