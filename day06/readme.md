# 🌐 Day 06 - Networking, AWS VPC & Shell Scripting Projects

## 📅 Date

20 July 2026

---

# 🚀 Introduction

Today, I explored one of the most important foundations of Cloud and DevOps: **Computer Networking** and **AWS Networking**.

I learned how communication happens over networks, how AWS isolates cloud resources using VPCs, and how public and private resources communicate securely.

Along with networking concepts, I built three practical DevOps automation projects using shell scripting:

* 📦 Automated Backup Script
* 📧 Website Health Monitoring with Email Alerts
* ⏰ Cron Job Automation for Scheduled Tasks

---

# 📚 Topics Covered

* Networking Basics
* IP Address
* IPv4 & IPv6
* CIDR
* AWS VPC
* Public & Private Subnets
* Internet Gateway
* NAT Gateway
* EC2 Instance
* Network ACL (NACL)
* Shell Scripting
* Cron Jobs
* Linux Automation

---

# 🌐 What is Networking?

Networking is the process of connecting computers and devices so they can communicate and exchange data.

Examples:

* Internet
* Office Networks
* Cloud Infrastructure

---

# 🌍 IP Address

An IP Address is a unique identifier assigned to every device connected to a network.

Example:

```text
192.168.1.10
```

It allows devices to locate and communicate with each other.

---

# IPv4

IPv4 uses **32-bit** addresses.

Example:

```text
192.168.1.1
```

Supports approximately **4.3 billion** addresses.

---

# IPv6

IPv6 uses **128-bit** addresses.

Example:

```text
2001:db8::1
```

IPv6 provides a massive number of unique addresses and is designed for future internet growth.

---

# CIDR (Classless Inter-Domain Routing)

CIDR defines the range of IP addresses available inside a network.

Example:

```text
10.0.0.0/16
```

Details:

* Network Address: `10.0.0.0`
* Prefix Length: `/16`

Common CIDR ranges:

| CIDR | Total IP Addresses |
| ---- | ------------------ |
| /24  | 256                |
| /16  | 65,536             |
| /8   | 16 Million         |

---

# ☁️ AWS VPC (Virtual Private Cloud)

A VPC is a logically isolated virtual network in AWS where cloud resources are deployed securely.

A VPC provides control over:

* IP Address Range
* Routing
* Security
* Internet Access

---

# Public Subnet

A subnet connected to the Internet Gateway.

Resources inside it can communicate directly with the internet.

Examples:

* Web Servers
* Load Balancers
* Bastion Hosts

---

# Private Subnet

A subnet that does not allow direct inbound internet access.

Resources remain protected.

Examples:

* Database Servers
* Backend Applications
* Internal Services

---

# Internet Gateway (IGW)

An Internet Gateway enables communication between a VPC and the public internet.

Without an IGW, public resources cannot be accessed externally.

---

# NAT Gateway

A NAT Gateway allows resources inside a private subnet to access the internet for updates and downloads without allowing inbound internet traffic.

Example:

A private EC2 instance downloads security updates while remaining hidden from the internet.

---

# EC2 Instance

Amazon EC2 provides virtual servers running inside an AWS VPC.

Instances can be deployed in:

* Public Subnets
* Private Subnets

---

# Network ACL (NACL)

A Network ACL is a stateless firewall that controls traffic at the subnet level.

Features:

* Allow Rules
* Deny Rules
* Inbound Rules
* Outbound Rules

---

# AWS Networking Architecture

```text
                    Internet
                        │
                Internet Gateway
                        │
                +----------------+
                |      VPC       |
                +----------------+
                  │           │
        Public Subnet    Private Subnet
              │                │
          EC2 Instance     EC2 Instance
              │                │
              └──── NAT Gateway┘
```

---

# 🛠️ Shell Scripting Projects

# 📦 Project 1 - Automated Backup Script

## Objective

Create automatic backups of important files and directories with timestamp-based naming.

## Workflow

```text
Source Folder
      │
      ▼
Backup Script
      │
      ▼
Timestamped Backup File
```

## Script (backup.sh)

```bash
#!/bin/bash

# Source directory
SOURCE="/home/ec2-user/project"

# Backup directory
BACKUP="/home/ec2-user/backups"

# Current date and time
DATE=$(date +"%Y-%m-%d_%H-%M-%S")

# Create backup directory
mkdir -p $BACKUP

# Create compressed backup
tar -czf $BACKUP/backup_$DATE.tar.gz $SOURCE

echo "✅ Backup completed successfully!"
echo "Backup saved at: $BACKUP/backup_$DATE.tar.gz"
```

## Make Script Executable

```bash
chmod +x backup.sh
```

## Run Script

```bash
./backup.sh
```

## Output

```text
✅ Backup completed successfully!

Backup saved at:
/home/ec2-user/backups/backup_2026-07-20_10-30-45.tar.gz
```

---

# 📧 Project 2 - Website Monitoring with Email Alerts

## Objective

Monitor website availability and send an email alert when the website becomes unavailable.

## Workflow

```text
Website
    │
    ▼
Shell Script
    │
    ▼
HTTP Status Check
    │
    ▼
Website Down?
    │
    ▼
Send Email Alert
```

## Script (website-monitor.sh)

```bash
#!/bin/bash

# Website URL
URL="https://yourwebsite.com"

# Email Address
EMAIL="your-email@example.com"

# Check HTTP Status
STATUS=$(curl -o /dev/null -s -w "%{http_code}" $URL)

if [ $STATUS -ne 200 ]
then
    echo "Website is DOWN! Status Code: $STATUS" | mail -s "Website Alert 🚨" $EMAIL
    echo "Alert email sent."
else
    echo "Website is UP ✅"
fi
```

## Make Script Executable

```bash
chmod +x website-monitor.sh
```

## Run Script

```bash
./website-monitor.sh
```

## Website Running Output

```text
Website is UP ✅
```

## Website Down Output

```text
Alert email sent.
```

Example Email:

```text
Subject: Website Alert 🚨

Website is DOWN!
Status Code: 500
```

Note:

The `mail` command requires a mail utility such as `mailx` and SMTP configuration.

Production systems commonly use:

* Amazon SES
* SendGrid
* SMTP Servers

---

# ⏰ Project 3 - Cron Job Automation

## Objective

Automate DevOps tasks by scheduling shell scripts to run automatically at specific times.

Cron is a Linux scheduling service used for automation.

---

## Backup Automation

Run backup every day at midnight:

```bash
0 0 * * * /home/ec2-user/backup.sh
```

---

## Website Monitoring Automation

Check website availability every 5 minutes:

```bash
*/5 * * * * /home/ec2-user/website-monitor.sh
```

---

## Benefits of Cron Jobs

* Reduces manual work
* Automates repetitive tasks
* Improves system reliability
* Useful for production monitoring and maintenance

---

# 🎯 Key Takeaways

* Learned networking fundamentals and IP addressing.
* Understood IPv4 and IPv6 concepts.
* Learned CIDR for network planning.
* Explored AWS VPC architecture.
* Understood Public and Private Subnets.
* Learned Internet Gateway and NAT Gateway usage.
* Learned EC2 deployment inside VPC.
* Explored Network ACL security.
* Built an automated backup system using Bash.
* Built website monitoring with email alerts.
* Automated scripts using Linux Cron Jobs.

---

# 📈 Progress

* ✅ Day 01 - DevOps Roadmap
* ✅ Day 02 - Linux Fundamentals
* ✅ Day 03 - Advanced Linux
* ✅ Day 04 - Linux Permissions & Shell Basics
* ✅ Day 05 - Shell Scripting
* ✅ Day 06 - Networking, AWS VPC & Shell Scripting Projects

## Completed: 6 / 90 Days 🚀

---

# 💡 What's Next?

Next, I will continue exploring AWS services, cloud architecture, infrastructure automation, and advanced DevOps practices.

---

⭐ Thanks for following my #90DaysOfDevOps journey!

## Projects Completed

🛠️ Automated Backup Script
📧 Website Monitoring with Email Alerts
⏰ Cron Job Automation
