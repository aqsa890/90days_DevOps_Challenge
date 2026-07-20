# 🌐 Day 07 - Networking Fundamentals, OSI Model & Python Basics

## 📅 Date

21 July 2026

---

# 🚀 Introduction

Day 07 was focused on understanding the core networking concepts that power the internet and cloud infrastructure. I learned how devices communicate, how data travels across networks, and the protocols involved in secure communication.

In Python, I explored **Tuples**, **Dictionaries**, and learned how to create and manage **Virtual Environments** for isolated project dependencies.

---

# 📚 Topics Covered

## 🌐 Networking Fundamentals

- Physical Network Components
- Router
- Switch
- Hub
- Server Rack
- IP Addressing
- Public & Private IP
- Subnetting
- CIDR Notation
- CDN (Content Delivery Network)
- DNS (Domain Name System)
- OSI Model (7 Layers)
- TCP/IP Model
- TCP 3-Way Handshake

---

# 🖥️ Physical Network Components

## 🗄️ Server Rack

A server rack is a metal frame used to organize and mount servers, switches, routers, and networking equipment in data centers.

### Benefits
- Better cable management
- Efficient cooling
- Easy maintenance
- Space optimization

---

## 📡 Hub

A Hub is a basic networking device that broadcasts incoming data to **every connected device**.

### Characteristics
- Works on Layer 1 (Physical Layer)
- No intelligence
- High network traffic
- Less secure

---

## 🔀 Switch

A Switch forwards data only to the intended device using **MAC addresses**.

### Characteristics
- Works on Layer 2 (Data Link Layer)
- Faster than Hub
- Reduces network congestion
- More secure

---

## 🌍 Router

A Router connects different networks together and routes packets using **IP addresses**.

### Example

```
Home Network
      │
   Router
      │
   Internet
```

Responsibilities:
- Connect different networks
- Route packets
- Assign local IP addresses (DHCP)
- Internet connectivity

---

# 🌐 IP Address

An IP Address uniquely identifies a device on a network.

Example

```
192.168.1.10
```

---

# 🌍 Public vs Private IP

## Public IP

- Accessible over the Internet
- Assigned by ISP or Cloud Provider
- Globally unique

Example

```
54.213.10.15
```

---

## Private IP

- Used inside local networks
- Not accessible directly from the Internet

Examples

```
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
```

---

# 📌 CIDR (Classless Inter-Domain Routing)

CIDR defines the size of a network.

Example

```
192.168.1.0/24
```

| CIDR | Hosts |
|------|------:|
| /24 | 256 |
| /16 | 65,536 |
| /8 | 16+ Million |

---

# 🌍 CDN (Content Delivery Network)

A CDN stores cached copies of website content across multiple global servers to deliver content faster to users.

### Benefits

- Faster website loading
- Reduced latency
- Lower server load
- Better availability

Popular CDNs:
- CloudFront
- Cloudflare
- Akamai

---

# 🌍 DNS (Domain Name System)

DNS translates domain names into IP addresses.

Example

```
google.com
        │
        ▼
142.250.xxx.xxx
```

Without DNS, users would need to remember IP addresses instead of domain names.

---

# 🌐 OSI Model (7 Layers)

| Layer | Name | Function |
|--------|------|----------|
| 7 | Application | User interaction (HTTP, FTP, SMTP) |
| 6 | Presentation | Encryption & Data Formatting |
| 5 | Session | Session Management |
| 4 | Transport | TCP, UDP |
| 3 | Network | IP Routing |
| 2 | Data Link | MAC Addressing |
| 1 | Physical | Cables & Signals |

---

# 🌐 TCP/IP Model

| Layer | Protocols |
|--------|-----------|
| Application | HTTP, HTTPS, FTP, DNS, SMTP |
| Transport | TCP, UDP |
| Internet | IP, ICMP |
| Network Access | Ethernet, Wi-Fi |

---

# 🤝 TCP 3-Way Handshake

TCP establishes a reliable connection using three steps:

```
Client                    Server

SYN  -------------------->

      <------------------- SYN-ACK

ACK  -------------------->

Connection Established ✅
```

### Steps

1. Client sends **SYN**
2. Server replies with **SYN-ACK**
3. Client sends **ACK**

Now data transmission begins.

---

# 🐍 Python Basics

## Tuples

A Tuple is an ordered and immutable collection.

```python
fruits = ("Apple", "Banana", "Orange")

print(fruits[0])
```

Output

```
Apple
```

---

## Dictionaries

A Dictionary stores data as key-value pairs.

```python
student = {
    "Name": "John",
    "Age": 22,
    "City": "New York"
}

print(student["Name"])
```

Output

```
John
```

---

# 🐍 Python Virtual Environment

A Virtual Environment creates an isolated Python environment for each project.

### Create Environment

```bash
python3 -m venv myenv
```

### Activate

Linux / macOS

```bash
source myenv/bin/activate
```

Windows

```bash
myenv\Scripts\activate
```

### Deactivate

```bash
deactivate
```

### Benefits

- Isolated dependencies
- Avoid version conflicts
- Better project management
- Industry best practice

---

# 🎯 Key Takeaways

- Learned how routers, switches, hubs, and racks form the backbone of physical networks.
- Understood IP addressing, subnetting, and CIDR notation.
- Explored the roles of DNS and CDN in web communication.
- Learned the OSI Model and TCP/IP Model for network communication.
- Understood how the TCP 3-Way Handshake establishes reliable connections.
- Practiced Python Tuples and Dictionaries.
- Created and managed Python Virtual Environments.

---

# 📈 Progress

- ✅ Day 01 – DevOps Roadmap
- ✅ Day 02 – Linux Fundamentals
- ✅ Day 03 – Advanced Linux
- ✅ Day 04 – Linux Permissions & Shell Basics
- ✅ Day 05 – Shell Scripting
- ✅ Day 06 – AWS Networking & Shell Projects
- ✅ Day 07 – Networking Fundamentals & Python Basics

**Completed:** 7 / 90 Days 🚀

---

# 💡 What's Next?

Next, I'll continue exploring AWS services, Python scripting, and core DevOps tools.

---

⭐ Thanks for following my #90DaysOfDevOps journey!