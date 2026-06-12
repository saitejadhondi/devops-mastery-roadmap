# ☁️ 06-AWS-Cloud-Deep-Dive.md

# AWS & Cloud Computing Deep Dive

## Understanding Where Modern Applications Actually Run

> Git stores code.
>
> Jenkins builds code.
>
> Docker packages code.
>
> Kubernetes manages containers.
>
> But where do the servers come from?
>
> Where do the networks come from?
>
> Where do the databases come from?
>
> That is where AWS enters the story.

---

# 📚 Table of Contents

1. Why Cloud Exists
2. Life Before Cloud
3. What Cloud Computing Actually Is
4. What Is AWS?
5. AWS Global Infrastructure
6. Regions
7. Availability Zones
8. VPC
9. EC2
10. Security Groups
11. Load Balancers
12. Auto Scaling
13. S3
14. EBS
15. RDS
16. IAM
17. Route 53
18. CloudWatch
19. EKS
20. Complete Production Architecture
21. Interview Questions

---

# Chapter 1: Life Before Cloud

Imagine you create a company.

Need to launch a website.

Before cloud:

You must buy:

```text
Servers
Storage
Networking Equipment
Power Backup
Cooling Systems
Fire Protection
Physical Security
```

---

Then:

```text
Install Hardware
Install Linux
Configure Network
Configure Security
Configure Storage
```

---

Cost:

```text
Thousands To Millions Of Dollars
```

before first customer arrives.

---

Big problems:

```text
Expensive
Slow
Complex
Difficult To Scale
```

---

# Example

Suppose:

```text
Need 5 Servers
```

Buy:

```text
5 Physical Machines
```

---

Traffic increases.

Need:

```text
50 Servers
```

Buy more hardware.

---

Traffic drops.

Now:

```text
45 Servers Idle
```

Still paying.

Huge waste.

---

# Chapter 2: Why Cloud Exists

Cloud providers asked:

```text
Why should every company
build their own data center?
```

---

Instead:

```text
AWS Builds Data Centers
```

Companies rent resources.

---

Think:

```text
Buying A House
        vs
Renting A House
```

Cloud = Renting.

---

Benefits:

```text
No Hardware Purchase
Pay As You Go
Fast Deployment
Easy Scaling
Global Reach
```

---

# Chapter 3: What Is Cloud Computing?

Simple Definition:

```text
Cloud Computing = Renting IT Resources Over The Internet
```

---

Resources include:

```text
Servers
Storage
Databases
Networking
Security
Monitoring
AI Services
```

---

Instead of:

```text
Buy Infrastructure
```

You:

```text
Rent Infrastructure
```

---

# Chapter 4: What Is AWS?

AWS = Amazon Web Services

---

Think:

```text
AWS = Giant Data Center Company
```

---

AWS provides:

```text
Computers
Storage
Networking
Databases
Security
Monitoring
AI Services
```

through APIs.

---

Mental Model:

```text
AWS = Operating System
For The Internet
```

---

# Chapter 5: AWS Global Infrastructure

AWS is not one building.

AWS consists of:

```text
Regions
Availability Zones
Data Centers
```

---

Architecture:

```text
AWS
 |
 +-- Region
 |      |
 |      +-- AZ1
 |      +-- AZ2
 |      +-- AZ3
 |
 +-- Region
        |
        +-- AZ1
        +-- AZ2
```

---

# Chapter 6: Region

Region = Geographic Location

Examples:

* US East
* US West
* Europe
* Asia Pacific

---

Example:

```text
Mumbai Region
```

India users receive lower latency.

---

Think:

```text
Region = City
```

---

# Chapter 7: Availability Zone (AZ)

Each region contains multiple AZs.

---

AZ = Independent Data Center

---

Example:

```text
Mumbai
   |
   +-- AZ-A
   +-- AZ-B
   +-- AZ-C
```

---

Why?

Suppose:

```text
AZ-A Power Failure
```

Application survives in:

```text
AZ-B
AZ-C
```

---

High Availability.

---

Think:

```text
Region = City

AZ = Building
```

---

# Chapter 8: VPC

One of the most important AWS concepts.

---

Question:

Where do servers live?

Need network.

---

AWS provides:

# VPC

Virtual Private Cloud

---

Think:

```text
Private Data Center Inside AWS
```

---

VPC contains:

```text
Servers
Databases
Load Balancers
Subnets
```

---

Architecture:

```text
AWS
  |
  +-- VPC
         |
         +-- EC2
         +-- RDS
         +-- Load Balancer
```

---

# Why VPC?

Provides:

```text
Isolation
Security
Network Control
```

---

# Chapter 9: EC2

Most important AWS service.

---

Question:

Where does application run?

Answer:

# EC2

Elastic Compute Cloud

---

Simple Definition:

```text
Virtual Machine In AWS
```

---

Think:

```text
Laptop In Cloud
```

---

Examples:

```text
Ubuntu Server
Windows Server
Amazon Linux
```

---

Application runs here.

---

Architecture:

```text
AWS
  |
  +-- VPC
         |
         +-- EC2
                 |
                 +-- Docker
                 +-- Application
```

---

# Chapter 10: Security Groups

Question:

Can anyone access server?

No.

Need firewall.

---

AWS provides:

# Security Groups

---

Controls:

```text
Who Can Enter
Who Can Leave
```

---

Example:

```text
Allow:
Port 80
Port 443

Block:
Everything Else
```

---

Think:

```text
Security Guard For Server
```

---

# Chapter 11: Load Balancer

Suppose:

```text
1 Server
```

receives:

```text
1 Million Requests
```

Not enough.

---

Need multiple servers.

```text
Server A
Server B
Server C
```

---

Question:

How do users choose?

---

Answer:

# Load Balancer

---

Architecture:

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

Load balancer distributes traffic.

---

Think:

```text
Traffic Police
```

---

# Chapter 12: Auto Scaling

Traffic changes constantly.

---

Morning:

```text
100 Users
```

Night:

```text
100,000 Users
```

---

Need automatic scaling.

---

AWS Auto Scaling:

```text
Traffic Increases
      ↓
Create Servers
```

---

Traffic decreases:

```text
Remove Servers
```

---

Benefits:

```text
Cost Savings
Performance
Automation
```

---

# Chapter 13: S3

One of AWS's most used services.

---

Question:

Where do files go?

Need storage.

---

AWS provides:

# S3

Simple Storage Service

---

Stores:

```text
Images
Videos
Documents
Backups
Logs
```

---

Think:

```text
Infinite Hard Drive
```

---

Architecture:

```text
Application
      ↓
S3 Bucket
      ↓
Stored Files
```

---

# Example

Instagram photos.

---

Photos stored in:

```text
S3
```

not EC2.

---

# Chapter 14: EBS

Question:

Where does EC2 store data?

Need disk.

---

AWS provides:

# EBS

Elastic Block Store

---

Think:

```text
Hard Disk For EC2
```

---

Architecture:

```text
EC2
  ↓
EBS
```

---

# Chapter 15: RDS

Question:

Where is database?

Need managed database.

---

AWS provides:

# RDS

Relational Database Service

---

Supports:

```text
MySQL
PostgreSQL
MariaDB
Oracle
```

---

Without RDS:

```text
Install Database
Patch Database
Backup Database
```

Manual work.

---

RDS automates everything.

---

Think:

```text
Database As A Service
```

---

# Chapter 16: IAM

Most important security service.

---

Question:

Who can access AWS?

Need permissions.

---

AWS provides:

# IAM

Identity And Access Management

---

Controls:

```text
Users
Roles
Permissions
Policies
```

---

Example:

```text
Developer
Can View EC2

Cannot Delete EC2
```

---

Think:

```text
Security Manager
```

---

# Chapter 17: Route 53

Question:

How does:

```text
amazon.com
```

find server?

Need DNS.

---

AWS provides:

# Route 53

---

Converts:

```text
amazon.com
```

to:

```text
IP Address
```

---

Think:

```text
Internet Phonebook
```

---

# Chapter 18: CloudWatch

Question:

How do we know server health?

Need monitoring.

---

AWS provides:

# CloudWatch

---

Monitors:

```text
CPU
Memory
Network
Logs
Errors
```

---

Alerts engineers when problems occur.

---

Think:

```text
Hospital Monitor
```

for infrastructure.

---

# Chapter 19: EKS

Remember Kubernetes?

---

Installing Kubernetes manually is difficult.

---

AWS provides:

# EKS

Elastic Kubernetes Service

---

AWS manages:

```text
Control Plane
Updates
Availability
```

---

Engineers manage:

```text
Applications
Pods
Deployments
```

---

# Chapter 20: Complete Production Architecture

Imagine Amazon Shopping Application.

---

Architecture:

```text
Users
   ↓
Route 53
   ↓
Load Balancer
   ↓
EKS Cluster
   ↓
Pods
   ↓
Services
   ↓
RDS Database
```

---

Images:

```text
Stored In S3
```

---

Monitoring:

```text
CloudWatch
```

---

Security:

```text
IAM
Security Groups
```

---

# Complete DevOps Flow

```text
Developer
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
    ↓
Docker Build
    ↓
Registry
    ↓
EKS
    ↓
Pods
    ↓
Users
```

Everything now fits together.

---

# Mental Model

Think:

```text
AWS = Cloud Provider

VPC = Private Network

EC2 = Virtual Machine

S3 = Storage

EBS = Hard Disk

RDS = Database

IAM = Security Manager

Load Balancer = Traffic Controller

CloudWatch = Monitoring

EKS = Managed Kubernetes
```

---

# 🔥 Interview Questions

### What Is AWS?

AWS is a cloud computing platform providing on-demand infrastructure and services.

---

### What Is EC2?

A virtual machine running in AWS.

---

### What Is S3?

Object storage service used to store files and data.

---

### Difference Between EBS And S3?

EBS is block storage attached to EC2.

S3 is object storage accessed via APIs.

---

### What Is VPC?

A logically isolated virtual network inside AWS.

---

### What Is IAM?

AWS service for managing users, permissions, and access control.

---

### Why Use Load Balancers?

To distribute traffic across multiple servers.

---

### What Is EKS?

AWS managed Kubernetes service.

---

# One-Line Summary

AWS provides the cloud infrastructure—servers, storage, networking, databases, security, and managed Kubernetes—that modern applications need to run reliably at global scale.
