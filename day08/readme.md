# 🔐 Day 08 - Network Security, System Design & Python APIs

## 📅 Date

22 July 2026

---

# 🚀 Introduction

Today, I focused on understanding the fundamentals of **network security**, **system design**, and **Python APIs**. I explored how cloud infrastructures are secured, how applications communicate over the internet, and the basics of designing scalable systems.

---

# 📚 Topics Covered

- Firewall
- Ingress & Egress Traffic
- SSL & TLS
- NAT (Network Address Translation)
- UFW (Uncomplicated Firewall)
- Protocols, IP Addresses & Ports
- VPC, Internet Gateway, Public & Private Subnets
- System Design & Architecture
- Python Sets
- APIs
- Request & Response

---

# 🔥 Firewall

A **Firewall** is a security system that monitors and controls incoming and outgoing network traffic based on predefined rules.

### Why use a Firewall?

- Block unauthorized access
- Protect servers from attacks
- Allow only trusted traffic
- Secure cloud resources

---

# 🌐 Ingress vs Egress

| Ingress | Egress |
|----------|---------|
| Incoming network traffic | Outgoing network traffic |
| Example: User accessing a website | Example: Server sending data to another server |

Example:

```
Internet
    │
    ▼
Ingress → EC2 Instance → Egress
```

---

# 🔒 SSL & TLS

### SSL (Secure Sockets Layer)

An older protocol used to encrypt communication between clients and servers.

### TLS (Transport Layer Security)

The modern and more secure replacement for SSL.

### Why SSL/TLS?

- Encrypts data in transit
- Prevents data theft
- Protects sensitive information
- Enables HTTPS

Example:

```
Browser
    │
 HTTPS (TLS)
    │
Web Server
```

---

# 🌍 NAT (Network Address Translation)

NAT allows private IP addresses to communicate with the internet using a public IP address.

### Benefits

- Conserves public IP addresses
- Improves security
- Allows private subnet instances to access the internet

---

# 🛡️ UFW (Uncomplicated Firewall)

UFW is a user-friendly firewall tool for Ubuntu.

### Common Commands

Enable UFW

```bash
sudo ufw enable
```

Allow SSH

```bash
sudo ufw allow 22
```

Allow HTTP

```bash
sudo ufw allow 80
```

Allow HTTPS

```bash
sudo ufw allow 443
```

Check Status

```bash
sudo ufw status
```

---

# 🌐 Protocols, IP & Ports

A **Protocol** defines how devices communicate over a network.

### Common Protocols

| Protocol | Port | Purpose |
|----------|-----:|---------|
| HTTP | 80 | Web Traffic |
| HTTPS | 443 | Secure Web Traffic |
| SSH | 22 | Remote Login |
| FTP | 21 | File Transfer |
| DNS | 53 | Domain Name Resolution |

---

# ☁️ AWS Networking Recap

### VPC

A logically isolated virtual network in AWS.

### Internet Gateway

Allows resources in a public subnet to communicate with the internet.

### Public Subnet

- Internet accessible
- Used for web servers, load balancers

### Private Subnet

- No direct internet access
- Used for databases and backend services

---

# 🏗️ System Design

System Design is the process of planning how different components of an application work together to build scalable, reliable, and efficient systems.

### Why is System Design Important?

- Scalability
- High Availability
- Reliability
- Performance
- Maintainability

### Basic Architecture

```
Users
   │
   ▼
Load Balancer
   │
   ▼
Application Servers
   │
   ▼
Database
```

---

# 🐍 Python Sets

A **Set** is an unordered collection of unique elements.

Example

```python
numbers = {1, 2, 3, 3, 4}

print(numbers)
```

Output

```
{1, 2, 3, 4}
```

### Features

- No duplicate values
- Fast lookups
- Mutable collection

---

# 🌐 API (Application Programming Interface)

An API allows different applications to communicate with each other.

Example:

```
Client
   │
Request
   ▼
API
   │
Response
   ▼
Client
```

---

# 📨 Request & Response

### Request

Data sent by the client to the server.

Example

```http
GET /users
```

### Response

Data returned by the server.

Example

```json
{
  "name": "John",
  "age": 25
}
```

---

# 🎯 Key Takeaways

- Learned how firewalls secure networks.
- Understood the difference between ingress and egress traffic.
- Explored SSL/TLS for secure communication.
- Learned the purpose of NAT and UFW.
- Reviewed networking concepts like protocols, ports, VPCs, and subnets.
- Studied the basics of system design and architecture.
- Practiced Python Sets.
- Learned how APIs work through requests and responses.

---

# 📈 Progress

- ✅ Day 01 – DevOps Roadmap
- ✅ Day 02 – Linux Fundamentals
- ✅ Day 03 – Advanced Linux
- ✅ Day 04 – Linux Permissions
- ✅ Day 05 – Shell Scripting
- ✅ Day 06 – AWS Networking
- ✅ Day 07 – Networking & Python Basics
- ✅ Day 08 – Network Security, System Design & Python APIs

**Completed:** 8 / 90 Days 🚀

---

⭐ Every day is another step toward becoming a better DevOps Engineer!