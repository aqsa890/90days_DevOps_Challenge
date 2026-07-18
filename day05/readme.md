# 🐧 Day 05 - Python for DevOps, Automation & Cron Jobs

## 📅 Date
18 July 2026

---

# 🚀 Introduction

Today, I continued my journey into **Python for DevOps automation**. I learned how Python logic can be used to create automation scripts, manage repetitive tasks, and improve system administration workflows.

I explored advanced Python concepts including **conditional statements, loops, functions, package management using pip**, and started automating Linux tasks using **Cron Jobs**.

---

# 📚 Topics Covered

- Python Conditional Statements
- Nested if-else Conditions
- Python Functions
- For Loops
- While Loops
- Package Installation using pip
- Python Automation Scripts
- Shell Scripting Automation
- Package Installation Automation
- Cron Tab Scheduling
- Automating Repetitive Tasks

---

# 🐍 Python for DevOps

Python is widely used in DevOps because it helps automate:

- Server management
- Cloud operations
- Deployment tasks
- Monitoring systems
- File management
- API integrations

Python scripts reduce manual work and improve efficiency.

---

# 🔀 Conditional Statements in Python

Conditional statements allow programs to make decisions based on conditions.

---

## if-else Statement

Example:

```python
age = 20

if age >= 18:
    print("User is allowed")
else:
    print("User is not allowed")
```

Output:

```
User is allowed
```

---

# 🌳 Nested if-else Conditions

Nested conditions are used when we need to check multiple conditions inside another condition.

Example:

```python
username = "admin"
password = "1234"

if username == "admin":

    if password == "1234":
        print("Login Successful")

    else:
        print("Wrong Password")

else:
    print("Invalid User")
```

Output:

```
Login Successful
```

---

# 🔁 Python Loops

Loops help automate repetitive tasks by executing a block of code multiple times.

---

# 🔄 For Loop

A `for` loop is used when we know the number of iterations.

Example:

```python
for i in range(5):
    print(i)
```

Output:

```
0
1
2
3
4
```

### DevOps Example:

Checking multiple servers:

```python
servers = ["server1", "server2", "server3"]

for server in servers:
    print("Checking", server)
```

---

# 🔁 While Loop

A `while` loop runs as long as a condition remains true.

Example:

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

Output:

```
1
2
3
4
5
```

---

# 🧩 Python Functions

Functions are reusable blocks of code that help organize automation scripts.

Example:

```python
def welcome():
    print("Welcome to DevOps")

welcome()
```

Output:

```
Welcome to DevOps
```

---

## Function with Parameters

Example:

```python
def install_package(package):

    print("Installing", package)


install_package("nginx")
```

Output:

```
Installing nginx
```

---

# 📦 Installing Python Packages Using pip

`pip` is Python's package manager used to install external libraries.

Check pip version:

```bash
pip --version
```

Install a package:

```bash
pip install requests
```

Install specific package version:

```bash
pip install requests==2.31.0
```

List installed packages:

```bash
pip list
```

Remove package:

```bash
pip uninstall requests
```

---

# ⚙️ Automation Using Python Scripts

Python can automate DevOps tasks like:

- Installing packages
- Checking system status
- Managing files
- Running commands
- Automating deployments

Example:

```python
import os

os.system("sudo apt update")

os.system("sudo apt install nginx -y")
```

This script automatically updates packages and installs Nginx.

---

# 🖥️ Shell Scripting Automation

Shell scripts can automate Linux administration tasks.

Examples:

- Installing software packages
- Running system updates
- Creating backups
- Monitoring services

Example:

```bash
#!/bin/bash

echo "Installing nginx..."

sudo apt update

sudo apt install nginx -y

echo "Installation completed"
```

---

# 🔁 Automation Using Loops in Scripts

Loops help execute repetitive commands automatically.

Example:

```bash
#!/bin/bash

for server in server1 server2 server3
do
    echo "Checking $server"
done
```

Output:

```
Checking server1
Checking server2
Checking server3
```

---

# ⏰ Cron Jobs Automation

Cron is a Linux scheduling tool used to automatically run commands or scripts at specific times.

Common uses:

- Automatic backups
- Log cleanup
- Server monitoring
- Database backups
- Scheduled deployments

---

# 📝 Cron Tab Commands

View current cron jobs:

```bash
crontab -l
```

Edit cron jobs:

```bash
crontab -e
```

Remove cron jobs:

```bash
crontab -r
```

---

# ⏱️ Cron Job Format

```
* * * * * command
```

Meaning:

```
| | | | |
| | | | └── Day of Week
| | | └──── Month
| | └────── Day of Month
| └──────── Hour
└────────── Minute
```

---

# Example Cron Job

Run backup script every day at midnight:

```bash
0 0 * * * /home/user/backup.sh
```

Run Python automation script every hour:

```bash
0 * * * * python3 /home/user/script.py
```

---

# 💻 Practice

Today I practiced:

### Python

- Writing if-else conditions
- Creating nested conditions
- Using for loops
- Using while loops
- Creating reusable functions
- Installing and managing Python packages using pip

### Automation Scripts

- Creating scripts for package installation
- Automating repetitive tasks using loops
- Writing reusable functions
- Automating Linux tasks

### Cron Jobs

- Creating scheduled tasks
- Running scripts automatically
- Understanding cron job syntax

---

# 🎯 Key Takeaways

- Python is a powerful language for DevOps automation.
- Conditional statements help scripts make intelligent decisions.
- Loops reduce repetitive manual work.
- Functions improve code reusability and maintainability.
- pip helps install and manage Python libraries.
- Shell scripts automate Linux administration tasks.
- Cron jobs allow automatic scheduling of DevOps tasks.

---

# 📈 Progress

- ✅ Day 01 - DevOps Roadmap
- ✅ Day 02 - Linux Fundamentals
- ✅ Day 03 - Advanced Linux, SSH & AWS Volume Management
- ✅ Day 04 - Basic Shell Scripting & Python Basics
- ✅ Day 05 - Python Automation, Scripting & Cron Jobs

**Completed:** 5 / 90 Days 🚀

---

# 💡 What's Next?

Next, I will continue learning Python for DevOps:

- Lists
- Tuples
- Dictionaries
- Sets
- File Handling
- Exception Handling
- Working with APIs
- Advanced Automation Scripts

---

⭐ Thank you for following my #90DaysOfDevOps journey!