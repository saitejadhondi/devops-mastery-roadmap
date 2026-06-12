# ⚡ DevOps Quick Revision

> 15-Minute DevOps Revision Guide for Interviews

---

# 🚀 Complete DevOps Flow

```text
Developer
    ↓
Git
    ↓
GitHub
    ↓
Webhook
    ↓
Jenkins / GitHub Actions
    ↓
Build
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
Production
```

---

# 🌍 Internet

## What happens when you type google.com?

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
HTTPS Request
 ↓
Google Server
 ↓
Response
```

---

# ☁️ Cloud Computing

Cloud = Renting infrastructure instead of buying hardware.

### Service Models

```text
IaaS → EC2

PaaS → Heroku

SaaS → Gmail
```

---

# ⚙️ DevOps

DevOps = Culture + Automation.

Goal:

```text
Faster Delivery

Better Reliability

Automation

Collaboration
```

---

# 🌳 Git

### Most Important Commands

```bash
git clone

git add .

git commit -m ""

git push

git pull

git branch

git checkout

git merge

git rebase

git stash
```

---

## Git vs GitHub

```text
Git
=
Version Control Tool

GitHub
=
Cloud Hosting Platform
```

---

# 🔄 CI/CD

## CI

```text
Code
 ↓
Build
 ↓
Test
```

---

## CD

```text
Build
 ↓
Deploy
```

---

## Jenkins Pipeline

```text
GitHub
 ↓
Webhook
 ↓
Jenkins
 ↓
Build
 ↓
Test
 ↓
Deploy
```

---

# 🐳 Docker

Docker packages applications into containers.

---

## Docker Flow

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

## Important Commands

```bash
docker build

docker run

docker ps

docker logs

docker exec
```

---

## Image vs Container

```text
Image
=
Blueprint

Container
=
Running Image
```

---

# ☸️ Kubernetes

Container Orchestration Platform.

---

## Architecture

```text
Deployment
 ↓
ReplicaSet
 ↓
Pod
 ↓
Container
```

---

## Request Flow

```text
User
 ↓
Ingress
 ↓
Service
 ↓
Pod
```

---

## Important Commands

```bash
kubectl get pods

kubectl logs

kubectl describe

kubectl apply -f
```

---

# ☁️ AWS

Most Important Services:

```text
EC2
S3
IAM
VPC
RDS
ELB
CloudWatch
Route53
Lambda
```

---

## EC2

Virtual Machine.

---

## S3

Object Storage.

---

## IAM

Access Control.

---

## VPC

Private Network.

---

## Route53

DNS Service.

---

# 🏗 Terraform

Infrastructure as Code.

---

## Workflow

```text
Code
 ↓
terraform init
 ↓
terraform plan
 ↓
terraform apply
 ↓
Infrastructure
```

---

## Important Files

```text
main.tf

variables.tf

outputs.tf

terraform.tfstate
```

---

# 🤖 Ansible

Configuration Management Tool.

---

## Terraform vs Ansible

```text
Terraform
=
Creates Infrastructure

Ansible
=
Configures Infrastructure
```

---

# 🌐 Networking

## OSI Model

```text
Application
Presentation
Session
Transport
Network
Data Link
Physical
```

---

## TCP Handshake

```text
SYN

SYN-ACK

ACK
```

---

## DNS

```text
Domain
 ↓
IP Address
```

---

## Common Ports

```text
22 SSH

80 HTTP

443 HTTPS

53 DNS

3306 MySQL
```

---

# 🔐 Security

## Encryption

```text
Plain Text
 ↓
Encrypted Data
```

---

## Hashing

```text
Input
 ↓
Hash
```

Examples:

```text
SHA256

MD5
```

---

## SSH

```text
Public Key

Private Key
```

---

## SSL/TLS

Used for HTTPS.

---

# 🔥 Nginx

Most Popular Reverse Proxy.

---

## Architecture

```text
Users
 ↓
Nginx
 ↓
Application
```

---

## Uses

```text
Load Balancing

Reverse Proxy

SSL Termination

Static Files
```

---

# 📊 Monitoring

## Monitoring Stack

```text
Application
 ↓
Prometheus
 ↓
Grafana
```

---

## Logging Stack

```text
Application
 ↓
ELK
```

ELK:

```text
Elasticsearch

Logstash

Kibana
```

---

# 📈 Observability

Three Pillars:

```text
Metrics

Logs

Traces
```

---

# 🎯 SRE

Site Reliability Engineering.

Focus:

```text
Availability

Reliability

Automation

Monitoring
```

---

## SLI

Measurement.

Example:

```text
99.9% Availability
```

---

## SLO

Target.

---

## SLA

Business Agreement.

---

# 🏗 System Design

## Load Balancer

```text
Users
 ↓
Load Balancer
 ↓
Servers
```

---

## Cache

```text
User
 ↓
Redis
 ↓
Database
```

---

## Message Queue

```text
Producer
 ↓
Kafka
 ↓
Consumer
```

---

# 🚀 Deployment Strategies

## Blue Green

```text
Blue
 ↓
Green
```

Traffic switches instantly.

---

## Canary

```text
90% Old

10% New
```

Gradually increase.

---

# 🔥 Production Troubleshooting

## Website Not Working

```text
DNS
 ↓
Load Balancer
 ↓
Server
 ↓
Application
 ↓
Database
```

---

## Kubernetes Troubleshooting

```bash
kubectl get pods

kubectl describe pod

kubectl logs
```

---

## Docker Troubleshooting

```bash
docker ps

docker logs

docker exec
```

---

# 🎯 Most Asked Interview Questions

### What is DevOps?

Culture that combines Development and Operations.

---

### What is CI/CD?

Automated build, test and deployment process.

---

### What is Docker?

Containerization platform.

---

### What is Kubernetes?

Container orchestration platform.

---

### What is Terraform?

Infrastructure as Code tool.

---

### What is Ansible?

Configuration management tool.

---

### What is EC2?

Virtual machine in AWS.

---

### What is S3?

Object storage service.

---

### What is DNS?

Maps domain names to IP addresses.

---

### What is Load Balancer?

Distributes traffic across servers.

---

### What is Nginx?

Web server and reverse proxy.

---

### What is Monitoring?

Tracking application and infrastructure health.

---

# 🧠 Ultimate DevOps Mental Model

```text
Internet
 ↓
Cloud
 ↓
Linux
 ↓
Networking
 ↓
Security
 ↓
Git
 ↓
CI/CD
 ↓
Docker
 ↓
Kubernetes
 ↓
AWS
 ↓
Terraform
 ↓
Ansible
 ↓
Monitoring
 ↓
SRE
 ↓
Production
```

---

# 🚀 One-Line Interview Revision

```text
Git → Jenkins → Docker → Kubernetes → AWS → Terraform → Monitoring → Production
```
