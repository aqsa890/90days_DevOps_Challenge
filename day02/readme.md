# 🐧 Day 02 - Linux Architecture & Basic Linux Commands

## 📅 Date

15 July 2026

---

# 🚀 Introduction

Welcome to **Day 02** of my **#90DaysOfDevOps** challenge.

Today, I learned the fundamentals of Linux, including how the Linux operating system is structured and some of the most commonly used Linux commands that every DevOps Engineer uses daily.

Linux is the backbone of modern cloud infrastructure, servers, and DevOps tools, making it one of the most important skills to master.

---

# 🏗️ Linux Architecture

Linux follows a layered architecture where every layer has a specific responsibility.

```text
+-----------------------+
|     Applications      |
+-----------------------+
           │
           ▼
+-----------------------+
|        Shell          |
+-----------------------+
           │
           ▼
+-----------------------+
|       Kernel          |
+-----------------------+
           │
           ▼
+-----------------------+
|      Hardware         |
+-----------------------+
```

---

## 1️⃣ Applications

Applications are the programs used by users.

Examples:

- Google Chrome
- VS Code
- Docker
- Jenkins
- Git
- Python

Applications cannot directly communicate with hardware.

Instead, they send requests to the Shell.

---

## 2️⃣ Shell

The Shell acts as an interpreter between the user and the Linux Kernel.

It accepts commands from users and translates them into instructions that the kernel understands.

Examples of Shells:

- Bash
- Zsh
- Fish
- Sh

Example:

```bash
ls
```

The shell interprets this command and asks the kernel to list files.

---

## 3️⃣ Kernel

The Kernel is the heart of the Linux Operating System.

It directly communicates with the hardware and manages system resources.

### Responsibilities

- Memory Management
- Process Management
- Device Management
- File System Management
- Security
- CPU Scheduling

Without the kernel, Linux cannot function.

---

## 4️⃣ Hardware

Hardware includes physical components such as:

- CPU
- RAM
- Hard Disk
- Keyboard
- Mouse
- Network Card

The kernel manages all hardware communication.

---

# 📌 Flow of Execution

```
User
   │
   ▼
Application
   │
   ▼
Shell
   │
   ▼
Kernel
   │
   ▼
Hardware
```

The response follows the reverse path back to the user.

---

# 💻 Linux Commands Learned Today

---

## 📂 pwd

Displays the current working directory.

```bash
pwd
```

Example Output

```
/home/shubham
```

---

## 📂 ls

Lists files and directories.

```bash
ls
```

Useful options

```bash
ls -l
```

(Long listing)

```bash
ls -a
```

(Show hidden files)

```bash
ls -lh
```

(Human-readable file sizes)

---

## 📂 cd

Changes the current directory.

```bash
cd Documents
```

Go back

```bash
cd ..
```

Go to home directory

```bash
cd ~
```

Go to previous directory

```bash
cd -
```

---

## 📄 cat

Displays file contents.

```bash
cat file.txt
```

Create a file

```bash
cat > file.txt
```

Append data

```bash
cat >> file.txt
```

---

## 🧠 free -h

Displays memory usage.

```bash
free -h
```

Example

```
              total   used   free
Mem:          15Gi   4Gi    9Gi
Swap:         2Gi    0Gi    2Gi
```

The **-h** option displays output in a human-readable format.

---

## 🐚 which

Shows the location of an executable command.

```bash
which bash
```

Output

```
/usr/bin/bash
```

Another example

```bash
which python3
```

---

## 🐚 bash

Starts a new Bash shell.

```bash
bash
```

Exit Bash

```bash
exit
```

---

# 📚 Commands Summary

| Command | Purpose |
|----------|---------|
| `pwd` | Show current directory |
| `ls` | List files and folders |
| `cd` | Change directory |
| `cat` | View or create files |
| `free -h` | Display RAM usage |
| `which` | Locate executable |
| `bash` | Start Bash shell |

---

# 🎯 Key Takeaways

- Linux architecture consists of **Applications → Shell → Kernel → Hardware**.
- The Shell acts as a bridge between the user and the kernel.
- The Kernel manages CPU, memory, devices, and filesystems.
- Understanding Linux commands is the first step toward becoming a DevOps Engineer.
- Practicing Linux daily is essential for working with cloud platforms and servers.

---

# 📈 Progress

- ✅ Day 01 - DevOps Roadmap
- ✅ Day 02 - Linux Architecture & Basic Commands

**Completed:** 2 / 90 Days

---

# 🔥 What's Next?

Tomorrow, I plan to learn:

- Linux File System
- Directory Structure
- Absolute vs Relative Paths
- More File Management Commands

---

# 💬 Connect With Me

I'm documenting my **#90DaysOfDevOps** journey publicly to stay consistent, build in public, and help others who are starting their DevOps journey.

⭐ If you found this repository helpful, don't forget to star it!

#90DaysOfDevOps #Linux #DevOps #OpenSource #Cloud #LearningInPublic #GitHub