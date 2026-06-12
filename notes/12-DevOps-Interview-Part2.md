# 🔥 12-DevOps-Interview-Questions-and-Answers-Part2.md

# DevOps Interview Questions & Answers (51-100)

---

# AWS & Cloud Computing

### 51. What is AWS?

AWS (Amazon Web Services) is a cloud platform that provides on-demand infrastructure and services such as compute, storage, networking, databases, and security.

---

### 52. Why do companies use AWS?

* No upfront hardware cost
* Global availability
* Scalability
* Pay-as-you-go pricing
* Managed services

---

### 53. What is EC2?

Elastic Compute Cloud (EC2) is a virtual machine service in AWS.

---

### 54. What is an AMI?

Amazon Machine Image (AMI) is a template used to launch EC2 instances.

---

### 55. What is the difference between EC2 and AMI?

AMI = Template

EC2 = Running Virtual Machine

---

### 56. What is S3?

Simple Storage Service (S3) is object storage used to store files, backups, logs, images, and videos.

---

### 57. What is a bucket in S3?

A bucket is a logical container used to store objects in S3.

---

### 58. Difference between S3 and EBS?

S3 = Object Storage

EBS = Block Storage attached to EC2

---

### 59. What is EBS?

Elastic Block Store is persistent disk storage for EC2 instances.

---

### 60. What is RDS?

Relational Database Service is a managed database service in AWS.

---

### 61. Which databases are supported by RDS?

* MySQL
* PostgreSQL
* MariaDB
* Oracle
* SQL Server

---

### 62. What is IAM?

Identity and Access Management is used to manage users, roles, permissions, and policies.

---

### 63. What is an IAM Role?

A role provides temporary permissions to AWS services or users.

---

### 64. What is a Security Group?

A virtual firewall controlling inbound and outbound traffic for AWS resources.

---

### 65. What is a VPC?

Virtual Private Cloud is a logically isolated network in AWS.

---

### 66. What is a subnet?

A subnet is a segment of a VPC network.

---

### 67. Difference between Public and Private Subnet?

Public Subnet:
Has internet access.

Private Subnet:
No direct internet access.

---

### 68. What is a Load Balancer?

A service that distributes incoming traffic across multiple servers.

---

### 69. What is Auto Scaling?

Automatically increasing or decreasing resources based on demand.

---

### 70. What is Route 53?

AWS DNS service used to map domain names to IP addresses.

---

# Terraform

### 71. What is Terraform?

Terraform is an Infrastructure as Code (IaC) tool used to provision and manage infrastructure.

---

### 72. What is Infrastructure as Code?

Managing infrastructure through code instead of manual processes.

---

### 73. Why use Terraform?

* Automation
* Repeatability
* Version Control
* Consistency

---

### 74. What is a Provider?

A plugin that allows Terraform to communicate with platforms such as AWS or Azure.

---

### 75. What is a Resource?

A component managed by Terraform such as EC2, VPC, or S3.

---

### 76. What is terraform init?

Initializes Terraform and downloads required providers.

---

### 77. What is terraform plan?

Shows what changes Terraform intends to make.

---

### 78. What is terraform apply?

Creates or modifies infrastructure.

---

### 79. What is terraform destroy?

Deletes infrastructure managed by Terraform.

---

### 80. What is Terraform State?

A file that tracks resources managed by Terraform.

---

# Linux

### 81. Why is Linux important in DevOps?

Most servers, containers, Kubernetes nodes, and cloud systems run Linux.

---

### 82. How do you view current directory?

```bash
pwd
```

---

### 83. How do you list files?

```bash
ls
```

---

### 84. How do you check disk usage?

```bash
df -h
```

---

### 85. How do you check memory usage?

```bash
free -m
```

---

### 86. How do you check running processes?

```bash
ps -ef
```

---

### 87. How do you kill a process?

```bash
kill -9 PID
```

---

### 88. How do you search text in files?

```bash
grep "text" file.txt
```

---

### 89. What is chmod?

Used to modify file permissions.

Example:

```bash
chmod 755 file.sh
```

---

### 90. What is sudo?

Allows a user to execute commands with elevated privileges.

---

# Networking

### 91. What is an IP Address?

A unique identifier assigned to devices on a network.

---

### 92. What is DNS?

Domain Name System converts domain names into IP addresses.

---

### 93. What happens when you type google.com?

Browser asks DNS for IP → Connects to server → Sends HTTP request → Receives response.

---

### 94. What is HTTP?

HyperText Transfer Protocol used for communication between clients and servers.

---

### 95. What is HTTPS?

HTTP secured using SSL/TLS encryption.

---

### 96. Difference between HTTP and HTTPS?

HTTP = Unencrypted

HTTPS = Encrypted

---

### 97. What is TCP?

Transmission Control Protocol provides reliable communication.

---

### 98. What is a Port?

A logical endpoint used by applications for communication.

Examples:

```text
80   HTTP
443  HTTPS
22   SSH
3306 MySQL
5432 PostgreSQL
```

---

### 99. What is SSH?

Secure Shell is used to securely connect to remote servers.

Example:

```bash
ssh user@server-ip
```

---

### 100. What is a Load Balancer in networking?

A component that distributes traffic across multiple backend servers to improve availability and performance.

---

# Quick Revision

```text
EC2           → Virtual Machine

S3            → Object Storage

EBS           → Disk Storage

RDS           → Managed Database

IAM           → Access Control

VPC           → Private Network

Route53       → DNS

Terraform     → Infrastructure as Code

Provider      → Cloud Connector

State File    → Terraform Memory

Linux         → Server Operating System

DNS           → Domain → IP

HTTP          → Web Protocol

HTTPS         → Secure Web Protocol

TCP           → Reliable Communication

SSH           → Remote Login
```

---

# ⭐ Most Asked DevOps Interview Questions (With Answers)

These are some of the most frequently asked questions in entry-level DevOps, Cloud, SRE, and Platform Engineering interviews.

---

## 1. What is CI/CD?

CI/CD stands for:

```text
Continuous Integration
Continuous Delivery/Deployment
```

### Continuous Integration (CI)

CI is the practice of automatically building and testing code whenever developers push changes.

Example:

```text
Developer
    ↓
Git Push
    ↓
Jenkins
    ↓
Build
    ↓
Test
```

Goal:

```text
Find Problems Early
```

---

### Continuous Delivery (CD)

Ensures software is always ready for deployment.

Example:

```text
Build
 ↓
Test
 ↓
Approval
 ↓
Deploy
```

---

### Continuous Deployment

Deploys software automatically without manual approval.

Example:

```text
Build
 ↓
Test
 ↓
Deploy Automatically
```

---

### Interview Answer

CI/CD is a software delivery practice that automates code integration, testing, and deployment to improve release speed and reliability.

---

## 2. Difference Between Git and GitHub?

### Git

Git is a version control tool.

Used for:

```text
Tracking Code Changes
Version Control
Branching
Merging
```

Example:

```bash
git commit
git push
```

---

### GitHub

GitHub is a cloud platform that hosts Git repositories.

Provides:

```text
Repository Hosting
Pull Requests
Code Reviews
CI/CD Integrations
```

---

### Interview Answer

Git is a distributed version control system, whereas GitHub is a cloud platform used to host and collaborate on Git repositories.

---

## 3. What is Jenkins?

Jenkins is an open-source automation server used to automate software development tasks.

Examples:

```text
Build
Test
Package
Deploy
```

---

### Workflow

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

### Interview Answer

Jenkins is a CI/CD automation server used to build, test, and deploy applications automatically.

---

## 4. What is Docker?

Docker is a containerization platform.

It packages:

```text
Application
Libraries
Dependencies
Configuration
```

into a container.

---

### Problem Docker Solves

```text
Works On My Machine
```

Problem.

---

### Interview Answer

Docker is a platform that packages applications and dependencies into portable containers so they run consistently across environments.

---

## 5. Difference Between Image and Container?

### Docker Image

A blueprint or template.

Example:

```text
shopping-app:v1
```

Not running.

---

### Container

A running instance of an image.

Example:

```bash
docker run shopping-app:v1
```

creates a container.

---

### Easy Analogy

```text
Class      → Image

Object     → Container
```

---

### Interview Answer

An image is a read-only template used to create containers, while a container is a running instance of that image.

---

## 6. What is Kubernetes?

Kubernetes is a container orchestration platform.

It manages:

```text
Containers
Networking
Scaling
Deployments
Recovery
```

---

### Problem It Solves

Managing thousands of containers manually.

---

### Interview Answer

Kubernetes automates deployment, scaling, networking, and management of containerized applications.

---

## 7. What is a Pod?

A Pod is the smallest deployable unit in Kubernetes.

---

Example:

```text
Pod
 └── Container
```

---

Kubernetes deploys Pods, not containers directly.

---

### Interview Answer

A Pod is the smallest deployable object in Kubernetes and contains one or more containers that share networking and storage.

---

## 8. What is AWS EC2?

EC2 stands for:

```text
Elastic Compute Cloud
```

---

It is a virtual machine running in AWS.

---

Example:

```text
AWS
 ↓
EC2
 ↓
Linux
 ↓
Application
```

---

### Interview Answer

Amazon EC2 is a cloud-based virtual machine service that provides scalable compute capacity on demand.

---

## 9. What is S3?

S3 stands for:

```text
Simple Storage Service
```

---

Used to store:

```text
Images
Videos
Documents
Logs
Backups
```

---

Think:

```text
Infinite Cloud Storage
```

---

### Interview Answer

Amazon S3 is an object storage service used for storing and retrieving files at virtually unlimited scale.

---

## 10. What is Terraform?

Terraform is an Infrastructure as Code (IaC) tool.

---

Instead of:

```text
Creating Infrastructure Manually
```

you write:

```hcl
resource "aws_instance" "web" {}
```

---

Terraform creates infrastructure automatically.

---

### Interview Answer

Terraform is an Infrastructure as Code tool used to provision and manage cloud resources through configuration files.

---

## 11. What is DNS?

DNS stands for:

```text
Domain Name System
```

---

Converts:

```text
google.com
```

into:

```text
142.250.183.46
```

(IP Address)

---

### Easy Analogy

```text
DNS
 =
Internet Phonebook
```

---

### Interview Answer

DNS translates domain names into IP addresses so computers can locate servers on the internet.

---

## 12. What Happens When You Type google.com?

### Step 1

Browser checks DNS.

```text
google.com
     ↓
DNS
```

---

### Step 2

DNS returns IP Address.

```text
142.x.x.x
```

---

### Step 3

Browser connects to Google server.

---

### Step 4

HTTP/HTTPS request sent.

---

### Step 5

Google server processes request.

---

### Step 6

Response returned.

---

### Complete Flow

```text
Browser
 ↓
DNS
 ↓
IP Address
 ↓
Google Server
 ↓
Response
 ↓
Browser
```

---

### Interview Answer

When google.com is entered, DNS resolves the domain name to an IP address, the browser establishes a connection to the server, sends an HTTPS request, receives a response, and renders the webpage.

---

## 13. Difference Between HTTP and HTTPS?

### HTTP

```text
HyperText Transfer Protocol
```

Data transferred in plain text.

---

### HTTPS

```text
HTTP + SSL/TLS Encryption
```

Data encrypted.

---

### Comparison

| HTTP          | HTTPS       |
| ------------- | ----------- |
| Not Encrypted | Encrypted   |
| Port 80       | Port 443    |
| Less Secure   | More Secure |

---

### Interview Answer

HTTPS is the secure version of HTTP that uses SSL/TLS encryption to protect communication between clients and servers.

---

## 14. What is a Load Balancer?

A Load Balancer distributes traffic across multiple servers.

---

Example:

```text
Users
   ↓
Load Balancer
   ↓
Server A
Server B
Server C
```

---

Benefits:

```text
High Availability
Scalability
Fault Tolerance
```

---

### Interview Answer

A Load Balancer distributes incoming requests across multiple backend servers to improve performance and availability.

---

## 15. What is Monitoring?

Monitoring is the process of continuously observing systems and applications.

---

Monitored Metrics:

```text
CPU
Memory
Disk
Network
Error Rate
Response Time
```

---

Example Tools:

```text
Prometheus
Grafana
CloudWatch
Datadog
```

---

### Interview Answer

Monitoring is the continuous collection and analysis of metrics, logs, and system health information to detect and troubleshoot issues proactively.

---

# 30-Second DevOps Interview Summary

```text
Git         → Version Control

GitHub      → Code Hosting

CI/CD       → Automation Pipeline

Jenkins     → CI/CD Tool

Docker      → Containerization

Image       → Blueprint

Container   → Running Application

Kubernetes  → Container Orchestration

Pod         → Smallest Kubernetes Unit

EC2         → Virtual Machine

S3          → Object Storage

Terraform   → Infrastructure as Code

DNS         → Domain → IP

HTTPS       → Secure Communication

Load Balancer → Traffic Distribution

Monitoring  → System Health Tracking
```
