# 🐧 Day 03 - Advanced Linux, SSH, Volume Management & AWS EBS

## 📅 Date
16 July 2026

---

# 🚀 Introduction

Today, I explored some advanced Linux concepts that are essential for DevOps engineers. I learned about SSH authentication, user and group management, process management, Linux links, and how storage volumes are attached and mounted on AWS EC2 instances.

---

# 📚 Topics Covered

- Advanced Linux Commands
- SSH Key Authentication
- User & Group Management
- Process Management
- File Ownership & Permissions
- Hard Link vs Soft Link
- Linux Volume Management
- AWS EBS Volume Attachment & Mounting
- Temporary vs Permanent Mounting
- Linux Password Storage

---

# 🔑 SSH Key-Based Authentication

Instead of using passwords, Linux servers can authenticate using SSH keys.

### Workflow

```text
Server A (Client)
│
├── Generate Public Key
├── Generate Private Key
│
└── Copy Public Key
            │
            ▼
Server B (Remote Server)
│
└── Public Key stored in ~/.ssh/authorized_keys
            ▲
            │
Server A connects using its Private Key
```

Example:

Generate keys

```bash
ssh-keygen
```

Copy public key

```bash
ssh-copy-id user@serverB
```

Connect

```bash
ssh -i ~/.ssh/id_rsa user@serverB
```

### Why SSH Keys?

- More secure than passwords
- Prevents brute-force attacks
- Widely used in cloud environments
- Enables automated deployments

---

# 👥 User & Group Management

Check current user's sudo permissions

```bash
sudo -l
```

Check group membership

```bash
groups username
```

Display user information

```bash
id username
```

Check another user's sudo access

```bash
sudo -l -U username
```

---

# ⚙️ Process & Service Management

Linux uses **systemd** to manage services.

Common commands:

Start a service

```bash
sudo systemctl start nginx
```

Stop a service

```bash
sudo systemctl stop nginx
```

Restart

```bash
sudo systemctl restart nginx
```

Enable on boot

```bash
sudo systemctl enable nginx
```

Check status

```bash
systemctl status nginx
```

---

# 📁 File Ownership & Groups

View owner and group

```bash
ls -l file.txt
```

Change group

```bash
sudo chgrp developers file.txt
```

Change only group

```bash
sudo chown :developers file.txt
```

Change owner and group

```bash
sudo chown john:developers file.txt
```

Recursive group change

```bash
sudo chgrp -R developers folder/
```

---

# 🔗 Hard Link vs Soft Link

| Hard Link | Soft Link |
|-----------|-----------|
| Points directly to the file's inode | Points to the file path |
| Survives if original filename is deleted | Breaks if original file is deleted |
| Cannot span different file systems | Can span different file systems |
| Cannot link directories (normally) | Can link directories |

Create Hard Link

```bash
ln file.txt hardlink.txt
```

Create Soft Link

```bash
ln -s file.txt softlink.txt
```

---

# 💾 Linux Volume Management

A volume is a storage device attached to a Linux system.

Examples:

- Hard Disk
- SSD
- AWS EBS Volume

Useful command

```bash
lsblk
```

Shows all attached storage devices.

---

# ☁️ AWS EBS: Attach vs Mount

These are two different operations.

## Attach

- AWS operation
- Connects an EBS volume to an EC2 instance
- The operating system can detect the disk
- The disk is **not yet usable**

Example:

```
EC2
      +
EBS Volume
```

---

## Mount

- Linux operation
- Makes the attached disk accessible through a directory

Example:

```bash
sudo mkdir /data
sudo mount /dev/xvdf /data
```

Now everything inside `/data` is stored on the EBS volume.

### Difference

| Attach | Mount |
|---------|-------|
| AWS Operation | Linux Operation |
| Connects storage to EC2 | Makes storage usable |
| Done from AWS Console/CLI | Done using Linux `mount` command |
| Device appears in `lsblk` | Files become accessible |

---

# 📌 Temporary vs Permanent Mount

### Temporary Mount

```bash
sudo mount /dev/xvdf /data
```

Works until the server reboots.

---

### Permanent Mount

Add the volume to:

```text
/etc/fstab
```

Example:

```text
/dev/xvdf   /data   ext4   defaults   0   2
```

Now the volume mounts automatically after every reboot.

---

# 🔐 Linux Password Storage

Encrypted user passwords are stored in

```bash
cat /etc/shadow
```

The file contains password hashes, not plain-text passwords.

Only the root user can access this file.

---

# 🎯 Key Takeaways

- Learned password-less SSH authentication using public/private keys.
- Explored Linux user, group, and permission management.
- Understood how `systemctl` manages Linux services.
- Learned the difference between hard links and soft links.
- Understood the difference between attaching and mounting EBS volumes.
- Learned the difference between temporary (`mount`) and permanent (`/etc/fstab`) mounts.
- Explored how Linux securely stores user passwords in `/etc/shadow`.

---

# 📈 Progress

- ✅ Day 01 - DevOps Roadmap
- ✅ Day 02 - Linux Fundamentals
- ✅ Day 03 - Advanced Linux, SSH & AWS Volume Management

**Completed:** 3 / 90 Days 🚀

---

# 💡 What's Next?

Next, I plan to dive deeper into Linux networking, file permissions, and shell scripting.

---

⭐ Thank you for following my #90DaysOfDevOps journey!