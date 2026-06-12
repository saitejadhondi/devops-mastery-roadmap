# 🎯 30-DevOps-Interview-Master-Handbook.md

# DevOps Interview Master Handbook

## Ultimate Last-Minute Revision Guide

> Read this file 1–2 days before an interview.
>
> Goal:
>
> * Revise all major DevOps topics quickly
> * Recall key concepts
> * Review commands
> * Refresh architecture understanding
> * Prepare for technical discussions

---

# 🗺 Complete DevOps Flow

```text
User
 ↓
DNS
 ↓
Load Balancer
 ↓
Nginx
 ↓
Application
 ↓
Redis
 ↓
Database
 ↓
Monitoring
 ↓
Alerts
 ↓
Engineer
```

---

# 🌍 Internet

### What happens when you type google.com?

```text
Browser
 ↓
DNS Lookup
 ↓
IP Address
 ↓
TCP Handshake
 ↓
TLS Handshake
 ↓
HTTP Request
 ↓
Response
```

---

### DNS

```text
Domain Name
      ↓
IP Address
```

Example:

```text
google.com
     ↓
142.x.x.x
```

---

# ☁️ Cloud

### Cloud Computing

Using computing resources over the internet.

Examples:

```text
AWS
Azure
GCP
```

---

### IaaS

Infrastructure as a Service

Example:

```text
AWS EC2
```

---

### PaaS

Platform as a Service

Example:

```text
Heroku
```

---

### SaaS

Software as a Service

Example:

```text
Gmail
Salesforce
```

---

# 🚀 DevOps

### DevOps

Culture + Practices + Automation

Purpose:

```text
Develop Faster
Deploy Faster
Operate Better
```

---

### Benefits

```text
Automation
Collaboration
Reliability
Faster Delivery
```

---

# 🌳 Git

### Git

Distributed Version Control System

---

### Git Workflow

```text
Working Directory
      ↓
Staging Area
      ↓
Local Repository
      ↓
Remote Repository
```

---

### Most Important Commands

```bash
git clone
git add
git commit
git push
git pull
git branch
git checkout
git merge
git rebase
```

---

### Merge vs Rebase

Merge:

```text
Preserves History
```

Rebase:

```text
Linear History
```

---

# 🐙 GitHub

### GitHub

Cloud platform for hosting Git repositories.

---

### Webhook

Webhook:

```text
Event Notification
```

Example:

```text
Git Push
 ↓
Webhook
 ↓
Jenkins
 ↓
Pipeline Trigger
```

---

# ⚙️ CI/CD

### CI

Continuous Integration

```text
Code
 ↓
Build
 ↓
Test
```

---

### CD

Continuous Delivery / Deployment

```text
Build
 ↓
Deploy
```

---

# 🤖 Jenkins

### Jenkins

Automation Server

Used for:

```text
Build
Test
Deploy
```

---

### Jenkins Flow

```text
GitHub
 ↓
Webhook
 ↓
Jenkins
 ↓
Pipeline
 ↓
Deployment
```

---

# 🐳 Docker

### Docker

Containerization Platform

---

### Image

Blueprint

---

### Container

Running instance of image.

---

### Docker Flow

```text
Code
 ↓
Dockerfile
 ↓
Image
 ↓
Container
```

---

### Important Commands

```bash
docker build
docker run
docker ps
docker logs
docker exec
docker images
```

---

# ☸️ Kubernetes

### Kubernetes

Container Orchestration Platform

---

### Pod

Smallest Deployable Unit

---

### Deployment

Manages Pods

---

### Service

Exposes Pods

---

### Ingress

Routes external traffic.

---

### Kubernetes Flow

```text
Deployment
 ↓
Pods
 ↓
Service
 ↓
Ingress
```

---

### Debugging Commands

```bash
kubectl get pods

kubectl describe pod

kubectl logs

kubectl get events
```

---

# ☁️ AWS

### EC2

Virtual Machine

---

### S3

Object Storage

---

### IAM

Access Control

---

### VPC

Private Network

---

### Load Balancer

Traffic Distribution

---

### Route 53

DNS Service

---

# 🏗 Terraform

### Terraform

Infrastructure as Code

---

### Workflow

```text
terraform init
 ↓
terraform plan
 ↓
terraform apply
```

---

### Benefits

```text
Automation
Consistency
Version Control
```

---

# ⚙️ Ansible

### Ansible

Configuration Management Tool

---

### Terraform vs Ansible

Terraform:

```text
Creates Infrastructure
```

Ansible:

```text
Configures Infrastructure
```

---

# 🌐 Networking

### TCP vs UDP

TCP:

```text
Reliable
Connection Oriented
```

UDP:

```text
Fast
Connectionless
```

---

### Ports

```text
22   SSH
80   HTTP
443  HTTPS
3306 MySQL
5432 PostgreSQL
6379 Redis
```

---

### TCP Handshake

```text
SYN
 ↓
SYN-ACK
 ↓
ACK
```

---

# 🔐 Security

### Authentication

```text
Who Are You?
```

---

### Authorization

```text
What Can You Access?
```

---

### SSH

Secure Remote Access

---

### TLS

Encryption Layer

---

### Public Key

Used for encryption.

---

### Private Key

Used for decryption.

---

# 📦 Nginx

### Nginx

```text
Web Server
Reverse Proxy
Load Balancer
```

---

### Flow

```text
User
 ↓
Nginx
 ↓
Application
```

---

# 🗄 Databases

### SQL

Structured Data

Examples:

```text
MySQL
PostgreSQL
```

---

### NoSQL

Flexible Data

Examples:

```text
MongoDB
Redis
```

---

### Replication

Copy Data

---

### Sharding

Split Data

---

# 📊 Monitoring

### Monitoring

Collecting Metrics

---

### Prometheus

Metrics Collection

---

### Grafana

Visualization

---

### Alerting

Notify Engineers

---

# 🔭 Observability

### Three Pillars

```text
Metrics
Logs
Traces
```

---

### OpenTelemetry

Industry Standard Telemetry Framework

---

# 🚨 SRE

### SRE

Site Reliability Engineering

---

### SLI

Measurement

---

### SLO

Target

---

### SLA

Contract

---

### Error Budget

Allowed Failure

---

# 🏗 System Design

### Scalability

Handle Growth

---

### Availability

System Accessible

---

### Reliability

System Correct

---

### Load Balancer

Distributes Traffic

---

### Cache

Reduces Database Load

---

### Redis

In-Memory Cache

---

# 🔥 Production Troubleshooting

### Universal Debugging Flow

```text
Problem
 ↓
Observe
 ↓
Logs
 ↓
Metrics
 ↓
Root Cause
 ↓
Fix
 ↓
Validate
```

---

### First Question

```text
What Changed?
```

---

### Linux Commands

```bash
top
htop
free -h
df -h
ps aux
journalctl -xe
```

---

### Docker Commands

```bash
docker ps
docker logs
docker inspect
```

---

### Kubernetes Commands

```bash
kubectl get pods

kubectl describe pod

kubectl logs
```

---

# 🎯 Top Interview Questions

1. What is DevOps?
2. What is CI/CD?
3. What is Jenkins?
4. What is Docker?
5. Difference between Image and Container?
6. What is Kubernetes?
7. What is a Pod?
8. What is AWS EC2?
9. What is S3?
10. What is Terraform?
11. What is DNS?
12. What happens when you type google.com?
13. Difference between HTTP and HTTPS?
14. What is a Load Balancer?
15. What is Monitoring?
16. What is SRE?
17. What is a Webhook?
18. What is Git Rebase?
19. What is Nginx?
20. What is Ansible?

---

# 🧠 Ultimate Mental Model

```text
Developer
 ↓
Git
 ↓
GitHub
 ↓
Webhook
 ↓
CI/CD
 ↓
Docker
 ↓
Registry
 ↓
Kubernetes
 ↓
AWS
 ↓
Monitoring
 ↓
Alerts
 ↓
Engineer
```

---

# One-Line Summary

A successful DevOps engineer understands Linux, Networking, Security, Git, CI/CD, Docker, Kubernetes, AWS, Terraform, Monitoring, SRE, and Production Troubleshooting—and knows how they work together to build reliable systems.
