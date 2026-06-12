# ⚡ 21-GitHub-Actions-Deep-Dive.md

# GitHub Actions Deep Dive

## Modern CI/CD Automation Using GitHub Workflows

> GitHub stores your code.
>
> GitHub Actions automates what happens after your code changes.
>
> Every time you push code, GitHub Actions can:
>
> * Build your application
> * Run tests
> * Scan security vulnerabilities
> * Build Docker images
> * Deploy to AWS
> * Deploy to Kubernetes
>
> This is CI/CD in action.

---

# 📚 Table of Contents

1. What is GitHub Actions?
2. Why GitHub Actions Exists
3. CI vs CD
4. GitHub Actions Architecture
5. Workflow Fundamentals
6. Events
7. Jobs
8. Steps
9. Runners
10. Actions Marketplace
11. Secrets
12. Environment Variables
13. Artifacts
14. Docker Integration
15. AWS Deployment
16. Kubernetes Deployment
17. Self-Hosted Runners
18. GitHub Actions vs Jenkins
19. Real Production Pipeline
20. Interview Questions

---

# Chapter 1: What is GitHub Actions?

GitHub Actions is:

```text
CI/CD Platform
Automation Platform
Workflow Engine
```

built directly into GitHub.

---

It allows:

```text
Build
Test
Deploy
Automate
```

applications automatically.

---

Simple Definition:

```text
GitHub Actions automates tasks triggered by GitHub events.
```

---

# Chapter 2: Why GitHub Actions Exists

Without Automation:

```text
Developer
   ↓
Build Code
   ↓
Run Tests
   ↓
Deploy
```

Manually.

---

Problem:

```text
Slow
Error-Prone
Repetitive
```

---

Solution:

```text
Developer
   ↓
Git Push
   ↓
GitHub Actions
   ↓
Automation
```

---

# Chapter 3: CI vs CD

## Continuous Integration (CI)

Automatically:

```text
Build
Test
Validate
```

code changes.

---

Flow:

```text
Developer
   ↓
Push Code
   ↓
Build
   ↓
Test
```

---

## Continuous Delivery / Deployment (CD)

Automatically:

```text
Deploy
```

applications.

---

Flow:

```text
Build
 ↓
Deploy
 ↓
Production
```

---

# Chapter 4: GitHub Actions Architecture

Architecture:

```text
Developer
   ↓
Git Push
   ↓
GitHub Repository
   ↓
Workflow YAML
   ↓
Runner
   ↓
Build / Test / Deploy
```

---

Main Components:

```text
Workflows
Events
Jobs
Steps
Runners
Actions
```

---

# Chapter 5: Workflow Fundamentals

Workflow:

```text
Automation Definition
```

stored in:

```text
.github/workflows/
```

---

Example:

```yaml
name: Build

on:
  push

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - run: echo "Building"
```

---

Think:

```text
Workflow
   =
Pipeline Definition
```

---

# Chapter 6: Events

Events trigger workflows.

---

Common Events:

```text
push
pull_request
workflow_dispatch
schedule
release
```

---

Example:

```yaml
on:
  push
```

---

Meaning:

```text
Run Workflow
When Code Is Pushed
```

---

# Chapter 7: Jobs

A workflow contains jobs.

---

Example:

```yaml
jobs:

  build:

  test:

  deploy:
```

---

Architecture:

```text
Workflow
   ↓
Build Job
Test Job
Deploy Job
```

---

# Chapter 8: Steps

Jobs contain steps.

---

Example:

```yaml
steps:

  - checkout code

  - install dependencies

  - run tests

  - build application
```

---

Flow:

```text
Job
  ↓
Step 1
Step 2
Step 3
```

---

# Chapter 9: Runners

Runners execute workflows.

---

GitHub Hosted:

```text
ubuntu-latest
windows-latest
macos-latest
```

---

Example:

```yaml
runs-on: ubuntu-latest
```

---

Architecture:

```text
GitHub
   ↓
Runner VM
   ↓
Execute Workflow
```

---

# Chapter 10: Actions Marketplace

GitHub provides reusable actions.

---

Examples:

```text
Checkout Code
Docker Login
AWS Login
Kubernetes Deployment
```

---

Example:

```yaml
- uses: actions/checkout@v4
```

---

Think:

```text
Action
    =
Reusable Automation Component
```

---

# Chapter 11: Secrets

Never hardcode:

```text
Passwords
API Keys
Tokens
```

---

Store securely:

```text
GitHub Secrets
```

---

Example:

```yaml
${{ secrets.AWS_ACCESS_KEY_ID }}
```

---

Benefits:

```text
Security
Compliance
Protection
```

---

# Chapter 12: Environment Variables

Reusable configuration values.

---

Example:

```yaml
env:
  APP_NAME: myapp
```

---

Usage:

```yaml
echo $APP_NAME
```

---

# Chapter 13: Artifacts

Artifacts store workflow outputs.

---

Examples:

```text
Build Files
Reports
Logs
Packages
```

---

Flow:

```text
Build
 ↓
Artifact
 ↓
Download
```

---

# Chapter 14: Docker Integration

Build Docker Images automatically.

---

Example:

```yaml
- name: Build Docker Image

  run: docker build -t myapp .
```

---

Flow:

```text
Git Push
 ↓
GitHub Actions
 ↓
Docker Build
 ↓
Docker Image
```

---

# Chapter 15: AWS Deployment

Deploy automatically to AWS.

---

Architecture:

```text
GitHub Actions
      ↓
AWS Credentials
      ↓
EC2
ECS
Lambda
```

---

Common Services:

```text
EC2
ECS
EKS
Lambda
```

---

# Chapter 16: Kubernetes Deployment

Deploy automatically to Kubernetes.

---

Example:

```yaml
kubectl apply -f deployment.yaml
```

---

Architecture:

```text
GitHub Actions
      ↓
kubectl
      ↓
Kubernetes Cluster
```

---

# Chapter 17: Self-Hosted Runners

Instead of GitHub VMs:

```text
Use Your Own Server
```

---

Architecture:

```text
GitHub
   ↓
Self Hosted Runner
   ↓
Your Infrastructure
```

---

Advantages:

```text
More Control
Custom Software
Private Network Access
```

---

# Chapter 18: GitHub Actions vs Jenkins

Most Asked Interview Question.

---

## Jenkins

```text
Separate Server
```

You manage:

```text
Installation
Plugins
Updates
Infrastructure
```

---

## GitHub Actions

Built into GitHub.

---

Comparison:

| GitHub Actions   | Jenkins       |
| ---------------- | ------------- |
| Managed Platform | Self Managed  |
| YAML Based       | Jenkinsfile   |
| Easier Setup     | More Flexible |
| GitHub Native    | Tool Agnostic |

---

Easy Memory:

```text
Jenkins
   =
Own The Server

GitHub Actions
   =
GitHub Owns The Server
```

---

# Chapter 19: Real Production Pipeline

Modern Flow:

```text
Developer
   ↓
Git Push
   ↓
GitHub
   ↓
GitHub Actions
   ↓
Build
   ↓
Unit Tests
   ↓
Security Scan
   ↓
Docker Build
   ↓
Push Image
   ↓
Deploy AWS
   ↓
Deploy Kubernetes
```

---

Production Architecture:

```text
Developer
     ↓
GitHub
     ↓
GitHub Actions
     ↓
Docker Registry
     ↓
Kubernetes
     ↓
Users
```

---

# Chapter 20: Why GitHub Actions Matters In DevOps

GitHub Actions automates:

```text
Testing
Building
Deployments
Security Checks
Infrastructure Automation
```

Without CI/CD:

```text
Slow Releases
Human Errors
Manual Processes
```

---

# 🔥 Interview Questions

### What Is GitHub Actions?

A CI/CD and workflow automation platform built into GitHub.

---

### What Is A Workflow?

A YAML-defined automation pipeline.

---

### What Triggers A Workflow?

Events such as:

```text
Push
Pull Request
Release
Schedule
```

---

### What Is A Runner?

A machine that executes workflow jobs.

---

### What Is An Action?

A reusable automation component used inside workflows.

---

### What Are GitHub Secrets?

Securely stored credentials used by workflows.

---

### GitHub Actions vs Jenkins?

GitHub Actions is GitHub-native and managed.

Jenkins is self-hosted and highly customizable.

---

### Where Are Workflow Files Stored?

```text
.github/workflows/
```

---

### Can GitHub Actions Deploy To AWS?

Yes.

It can deploy to:

```text
EC2
ECS
EKS
Lambda
```

---

### Can GitHub Actions Deploy To Kubernetes?

Yes.

Using:

```text
kubectl
helm
argoCD
```

---

# Mental Model

```text
Git Push
    ↓
GitHub Event
    ↓
Workflow YAML
    ↓
Runner
    ↓
Build
    ↓
Test
    ↓
Deploy
```

---

# GitHub Actions Ecosystem

```text
GitHub
     ↓
Events
     ↓
Workflow
     ↓
Jobs
     ↓
Steps
     ↓
Runner
     ↓
Automation
```

---

# One-Line Summary

GitHub Actions is a GitHub-native CI/CD and automation platform that executes YAML-defined workflows to build, test, secure, and deploy applications automatically in modern DevOps environments.
