# 🚀 Day 12 - Advanced Git & AWS EC2, IAM and S3

## 📅 Date

26 July 2026

---

# 🚀 Introduction

Today, I explored advanced Git concepts used in real-world software development and DevOps workflows. I learned different Git history management techniques such as **Rebase, Squash, Cherry-pick, Stash, Reset, Revert, Merge Conflicts, Tags, Hooks**, and more.

On the AWS side, I learned how to create an **EC2 instance**, understood **IAM (Users, Groups, Roles, Policies, Identity Providers)**, configured the **AWS CLI**, and worked with **Amazon S3 Buckets**.

---

# 📚 Topics Covered

## 🔄 Git

- Git Log
- Git Rebase
- Merge vs Rebase
- Squash Commits
- Git Blame
- Git Revert
- Git Reset
- Git Cherry-pick
- Git Stash
- Git Merge Conflicts
- Abort Merge
- Git Tags
- Git Hooks
- Git Diff
- Git Status

## ☁️ AWS

- EC2 Instance Creation
- IAM
- IAM Users
- IAM Groups
- IAM Roles
- IAM Policies
- Identity Providers
- AWS CLI
- Amazon S3

---

# 📖 Git Log

Displays the commit history.

```bash
git log
```

Compact version

```bash
git log --oneline
```

Graph view

```bash
git log --oneline --graph --all
```

---

# 🌿 Git Rebase

Rebase moves your commits on top of another branch to maintain a clean and linear history.

Example

```bash
git checkout feature
git rebase main
```

---

# Merge vs Rebase

## Merge

- Preserves complete history
- Creates a merge commit
- Best for shared branches

```bash
git merge feature
```

---

## Rebase

- Creates a cleaner history
- No extra merge commits
- Best before opening a Pull Request

```bash
git rebase main
```

---

## When to Use Merge?

✅ Team collaboration

✅ Shared branches

✅ Preserve project history

---

## When to Use Rebase?

✅ Feature branches

✅ Before creating Pull Requests

✅ Clean commit history

---

# 📦 Squash Commits

Squashing combines multiple commits into one.

Example

```
Commit 1
Commit 2
Commit 3

↓

Single Commit
```

Interactive Rebase

```bash
git rebase -i HEAD~3
```

Replace

```
pick
```

with

```
squash
```

---

# 🕵️ Git Blame

Shows who last modified each line.

```bash
git blame README.md
```

Useful for debugging.

---

# ↩️ Git Revert

Creates a new commit that undoes an existing commit.

```bash
git revert <commit-hash>
```

Safe for shared repositories.

---

# 🔄 Git Reset

## Soft Reset

Moves HEAD but keeps changes staged.

```bash
git reset --soft HEAD~1
```

---

## Mixed Reset (Default)

Keeps changes but unstages them.

```bash
git reset --mixed HEAD~1
```

---

## Hard Reset

Deletes commits and changes permanently.

```bash
git reset --hard HEAD~1
```

⚠️ Use carefully.

---

# 🍒 Git Cherry-pick

Copies a specific commit from another branch.

```bash
git cherry-pick <commit-hash>
```

Useful for applying bug fixes without merging an entire branch.

---

# 📦 Git Stash

Temporarily saves uncommitted changes.

Save changes

```bash
git stash push
```

List stashes

```bash
git stash list
```

Show stash

```bash
git stash show
```

Restore stash

```bash
git stash pop
```

---

# ⚠️ Merge Conflicts

Occurs when Git cannot automatically merge changes.

Resolve conflict manually, then:

```bash
git add .
git commit
```

Abort merge

```bash
git merge --abort
```

---

# 🏷️ Git Tags

Tags mark important versions such as releases.

Create tag

```bash
git tag v1.0
```

View tags

```bash
git tag
```

Push tag

```bash
git push origin v1.0
```

---

# 🪝 Git Hooks

Git Hooks are scripts that automatically execute before or after Git events.

Examples

- pre-commit
- commit-msg
- pre-push
- post-merge

Uses

- Run tests
- Check formatting
- Prevent bad commits

---

# 📊 Git Diff

Shows differences between files.

```bash
git diff
```

Compare staged changes

```bash
git diff --staged
```

---

# 📋 Git Status

Shows the current repository state.

```bash
git status
```

---

# ☁️ Amazon EC2

Amazon EC2 (Elastic Compute Cloud) provides scalable virtual servers in AWS.

### EC2 Creation Steps

1. Login to AWS Console
2. Open EC2 Dashboard
3. Launch Instance
4. Choose an Amazon Machine Image (AMI)
5. Select Instance Type
6. Create or Select Key Pair
7. Configure Network (VPC/Subnet)
8. Configure Security Group
9. Review & Launch
10. Connect using SSH

Example

```bash
ssh -i key.pem ubuntu@<public-ip>
```

---

# 🔐 IAM (Identity and Access Management)

IAM manages authentication and permissions in AWS.

---

## IAM Users

Individual identities for people or applications.

Example

- Developer
- DevOps Engineer
- Administrator

---

## IAM Groups

A collection of IAM users sharing common permissions.

Example

```
Developers
```

```
DevOps
```

```
Admins
```

---

## IAM Roles

Roles provide temporary permissions for AWS services or users.

Examples

- EC2 Role
- Lambda Role
- Cross-account Role

---

## IAM Policies

Policies define what actions are allowed or denied.

Example

```json
Allow EC2 Read Access
```

Policies can be:

- AWS Managed
- Customer Managed
- Inline Policies

---

# 🌐 Identity Providers

Identity Providers enable users to log in using external identity systems.

Examples

- Google
- Microsoft Azure AD
- Okta
- Active Directory

---

# 💻 AWS CLI

AWS CLI allows managing AWS services from the terminal.

Configure

```bash
aws configure
```

Check identity

```bash
aws sts get-caller-identity
```

List S3 buckets

```bash
aws s3 ls
```

---

# 🪣 Amazon S3

Amazon Simple Storage Service (S3) is an object storage service.

Used for

- Backups
- Static Websites
- Logs
- Images
- Videos
- Data Storage

---

## Create Bucket

AWS Console

```
S3
↓

Create Bucket

↓

Choose Bucket Name

↓

Select Region

↓

Configure Permissions

↓

Create Bucket
```

AWS CLI

```bash
aws s3 mb s3://my-demo-bucket
```

Upload File

```bash
aws s3 cp image.png s3://my-demo-bucket
```

List Files

```bash
aws s3 ls s3://my-demo-bucket
```

Download File

```bash
aws s3 cp s3://my-demo-bucket/image.png .
```

Delete File

```bash
aws s3 rm s3://my-demo-bucket/image.png
```

---

# 🎯 Key Takeaways

- Learned advanced Git workflows including Rebase, Cherry-pick, Squash, Reset, Revert, Stash, Tags, Hooks, and Merge Conflict resolution.
- Understood when to use Merge versus Rebase in collaborative projects.
- Created and managed AWS EC2 instances.
- Learned IAM concepts including Users, Groups, Roles, Policies, and Identity Providers.
- Configured AWS CLI.
- Created and managed Amazon S3 buckets using both the AWS Console and CLI.

---

# 📈 Progress

- ✅ Day 12 – Advanced Git & AWS EC2, IAM and S3

**Completed:** 12 / 90 Days 🚀

---

> **"Mastering DevOps isn't about memorising commands—it's about understanding how the tools work together to build reliable, secure, and scalable systems."** 🌟