# 📚 03-Git-GitHub-Webhooks.md

# Git, GitHub & Webhooks — The Complete DevOps Foundation

> Before Jenkins can build code, before Docker can package code, before Kubernetes can run code, before AWS can host code...
>
> We need a way to manage code.
>
> That is where Git begins.

---

# 📖 Table of Contents

1. Why Git Exists
2. The Problem Before Git
3. What Git Actually Is
4. Git Architecture
5. Working Directory, Staging Area, Repository
6. Git Workflow
7. Commits Explained
8. Branches Explained
9. Merge vs Rebase
10. What GitHub Is
11. Git vs GitHub
12. SSH vs HTTPS
13. Pull Requests
14. Code Review Process
15. What Is A Webhook?
16. How Jenkins Knows New Code Arrived
17. End-to-End Flow
18. Industry Git Workflow
19. Interview Questions

---

# Chapter 1: Why Git Exists

Imagine 10 developers working on one project.

Developer A:

```python
login.py
```

Developer B:

```python
payment.py
```

Developer C:

```python
search.py
```

Everyone modifies files daily.

Question:

How do we know:

```text
Who changed code?
When changed?
Why changed?
Can we undo changes?
Can we recover deleted code?
```

Without version control:

```text
project_final.zip
project_final_v2.zip
project_final_v3.zip
project_latest.zip
project_latest_final.zip
```

Disaster.

---

# Chapter 2: What Is Git?

Git is a:

# Distributed Version Control System (DVCS)

Simple definition:

```text
Git tracks changes in source code over time.
```

Think of Git as:

```text
Google Docs Version History
                +
Source Code Tracking
```

---

# What Problems Does Git Solve?

Git remembers:

```text
Who changed?
What changed?
When changed?
Why changed?
```

Git allows:

```text
Undo Changes
Restore Files
Compare Versions
Work With Teams
```

---

# Chapter 3: Git Architecture

Most beginners think:

```text
Git = GitHub
```

Wrong.

Git and GitHub are different.

Git exists on your laptop.

```text
Your Laptop
     |
     |
     v
    Git
```

GitHub is only a remote storage location.

---

# Git Internals

Git has 3 major areas:

```text
Working Directory
       ↓
Staging Area
       ↓
Local Repository
```

---

# Working Directory

Your actual files.

Example:

```python
app.py
```

You edit:

```python
print("Hello")
```

File changes exist here.

---

# Staging Area

Temporary waiting room.

Command:

```bash
git add app.py
```

Meaning:

```text
I want this file included
in my next commit.
```

---

# Repository

Permanent history.

Command:

```bash
git commit
```

Now Git stores snapshot forever.

---

# Visual Flow

```text
File Edited
     ↓
Working Directory
     ↓
git add
     ↓
Staging Area
     ↓
git commit
     ↓
Repository
```

---

# Chapter 4: What Is A Commit?

A commit is:

# A Snapshot Of Your Project

Imagine saving a game.

```text
Level 1 Save
Level 2 Save
Level 3 Save
```

Git commits work similarly.

---

Example:

```bash
git commit -m "Added Login Feature"
```

Git creates:

```text
Commit ID
Author
Timestamp
Message
Changes
```

Example:

```text
7a92f2c
```

Every commit gets a unique hash.

---

# Commit History

```text
Commit 1
     ↓
Commit 2
     ↓
Commit 3
     ↓
Commit 4
```

Git stores all history.

---

# Chapter 5: Branches

Imagine two developers.

Developer A:

```text
Fix Bug
```

Developer B:

```text
New Feature
```

Should both modify same code?

Dangerous.

Need isolation.

---

Git creates:

# Branches

```text
main
 │
 ├── feature-login
 │
 ├── feature-payment
 │
 └── bugfix-auth
```

Each developer works independently.

---

# Why Branches Exist

Without branches:

```text
Everyone modifies same code
```

Chaos.

With branches:

```text
Everyone works safely
```

---

# Create Branch

```bash
git checkout -b feature-login
```

Meaning:

```text
Create Branch
Switch To Branch
```

---

# Chapter 6: Merge

Eventually feature is complete.

Need to combine branches.

```text
feature-login
      ↓
     main
```

Command:

```bash
git merge feature-login
```

---

Result:

```text
main contains login feature
```

---

# Merge Conflict

Suppose:

Developer A changes:

```python
name="john"
```

Developer B changes:

```python
name="smith"
```

Git doesn't know which version wins.

Conflict occurs.

Developer resolves manually.

---

# Chapter 7: What Is GitHub?

Git stores code locally.

Problem:

```text
Laptop Lost
Code Lost
```

Need central storage.

Enter GitHub.

GitHub provides:

```text
Remote Repository
Code Collaboration
Code Review
CI/CD Integration
Issue Tracking
```

---

# Git vs GitHub

| Git             | GitHub            |
| --------------- | ----------------- |
| Tool            | Platform          |
| Local           | Remote            |
| Version Control | Code Hosting      |
| Works Offline   | Requires Internet |

---

# Architecture

```text
Developer
      ↓
Local Git Repository
      ↓
GitHub Repository
```

---

# Push

Upload changes.

```bash
git push
```

Meaning:

```text
Local Repository
        ↓
GitHub Repository
```

---

# Pull

Download changes.

```bash
git pull
```

Meaning:

```text
GitHub Repository
         ↓
Local Repository
```

---

# Chapter 8: SSH vs HTTPS

How do we communicate with GitHub?

Two methods.

---

# HTTPS

Example:

```text
https://github.com/company/project.git
```

Authentication required.

Usually:

```text
Personal Access Token
```

---

# SSH

Example:

```text
git@github.com:company/project.git
```

Uses key pair.

```text
Private Key
Public Key
```

Most companies prefer SSH.

---

# Chapter 9: Pull Requests (PR)

One of the most important concepts.

Developer creates:

```text
feature-login
```

Finished feature.

Should code directly enter main?

No.

Need review.

---

Workflow:

```text
Developer
    ↓
Push Branch
    ↓
Create PR
    ↓
Review
    ↓
Approve
    ↓
Merge
```

---

# Why PR Exists

Benefits:

```text
Code Review
Knowledge Sharing
Bug Detection
Security Review
Quality Improvement
```

---

# Chapter 10: What Is A Webhook?

This is where DevOps begins.

Question:

How does Jenkins know:

```text
Developer pushed code?
```

Possible solution:

```text
Jenkins asks GitHub every second.
```

Bad idea.

Wasteful.

---

Need event-driven communication.

Solution:

# Webhook

Definition:

```text
A webhook is an HTTP callback
triggered when an event occurs.
```

Simple meaning:

```text
Something happened.
Let me inform another system.
```

---

# Real Example

Developer:

```bash
git push
```

GitHub detects:

```text
New Commit
```

GitHub immediately sends message.

```text
GitHub
     ↓
HTTP POST
     ↓
Jenkins
```

This message is called:

# Webhook

---

# Chapter 11: How Webhook Works

Inside GitHub:

```text
Settings
     ↓
Webhooks
```

Example:

```text
https://jenkins.company.com/github-webhook
```

Stored URL.

---

When push occurs:

GitHub sends:

```http
POST /github-webhook
```

Payload:

```json
{
 "event":"push",
 "branch":"main",
 "commit":"7a92f2c"
}
```

---

Jenkins receives.

```text
New Commit Detected
Starting Pipeline
```

---

# Full Webhook Flow

```text
Developer
     ↓
git push
     ↓
GitHub
     ↓
Webhook
     ↓
Jenkins
     ↓
Build
     ↓
Test
```

This is the beginning of CI/CD.

---

# Chapter 12: End-To-End Industry Flow

```text
Developer Writes Code
          ↓
git add
          ↓
git commit
          ↓
git push
          ↓
GitHub
          ↓
Webhook
          ↓
Jenkins Triggered
          ↓
CI Pipeline Starts
          ↓
Build
          ↓
Test
          ↓
Docker Build
          ↓
Deployment
```

---

# Chapter 13: Git Workflow Used In Companies

Most companies use:

```text
main
 │
 ├── feature/*
 ├── bugfix/*
 └── hotfix/*
```

---

Feature Development:

```text
Create Branch
      ↓
Write Code
      ↓
Commit
      ↓
Push
      ↓
Create PR
      ↓
Review
      ↓
Merge
```

---

# Mental Model

Think:

```text
Git = Version Control Engine

GitHub = Remote Storage

Pull Request = Review Process

Webhook = Notification System

Jenkins = Automation Engine
```

Together they form the first half of the DevOps pipeline.

---

# 🔥 Interview Questions

### What is Git?

Git is a distributed version control system used to track source code changes.

---

### Difference Between Git and GitHub?

Git is the version control tool.

GitHub is a cloud-based hosting platform for Git repositories.

---

### What is a Commit?

A commit is a snapshot of project changes stored in Git history.

---

### Why Use Branches?

Branches allow isolated development without affecting the main codebase.

---

### What is a Pull Request?

A pull request is a request to merge code from one branch into another after review.

---

### What is a Webhook?

A webhook is an HTTP callback that automatically notifies another system when an event occurs.

---

### How Does Jenkins Know New Code Was Pushed?

GitHub sends a webhook request to Jenkins whenever configured repository events occur.

---

### Why Are Webhooks Better Than Polling?

Polling continuously asks for updates.

Webhooks send updates only when events happen, reducing resource usage.
