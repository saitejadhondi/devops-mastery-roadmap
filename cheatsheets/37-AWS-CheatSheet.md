# ☁️ AWS Cheat Sheet

> Quick Revision Guide for AWS, Cloud Computing, DevOps & Interview Preparation

---

# 🎯 What is AWS?

AWS (Amazon Web Services) is a cloud platform that provides:

```text
Compute
Storage
Networking
Databases
Security
Monitoring
Serverless Services
```

Pay only for what you use.

---

# 🗺 AWS Global Infrastructure

```text
AWS Global Infrastructure
          │
          ▼
      Regions
          │
          ▼
 Availability Zones (AZs)
          │
          ▼
    Data Centers
```

Example:

```text
ap-south-1
     ↓
Mumbai Region
     ↓
AZ-A
AZ-B
AZ-C
```

---

# 🚀 Core AWS Services

| Service      | Purpose                      |
| ------------ | ---------------------------- |
| EC2          | Virtual Servers              |
| S3           | Object Storage               |
| IAM          | Identity & Access Management |
| VPC          | Virtual Network              |
| RDS          | Managed Database             |
| EBS          | Block Storage                |
| ELB          | Load Balancer                |
| Route53      | DNS                          |
| CloudWatch   | Monitoring                   |
| Auto Scaling | Automatic Scaling            |

---

# 🖥 EC2 (Elastic Compute Cloud)

## Purpose

Virtual Machine in AWS.

---

## EC2 Flow

```text
Application
     ↓
EC2 Instance
     ↓
Linux Server
```

---

## Common EC2 Concepts

```text
AMI
Instance Type
Security Group
Key Pair
Elastic IP
EBS Volume
```

---

## Popular Instance Types

```text
t2.micro

t3.micro

t3.medium

m5.large

c5.large
```

---

# 💾 S3 (Simple Storage Service)

## Purpose

Object Storage.

Stores:

```text
Images
Videos
Backups
Logs
Static Websites
```

---

## S3 Characteristics

```text
Highly Durable

Highly Available

Scalable

Low Cost
```

---

## Storage Classes

```text
S3 Standard

S3 IA

S3 Glacier

S3 Deep Archive
```

---

# 🔐 IAM (Identity & Access Management)

## Purpose

Controls access to AWS resources.

---

## IAM Components

```text
Users

Groups

Roles

Policies
```

---

## Principle

```text
Least Privilege Access
```

---

# 🌐 VPC (Virtual Private Cloud)

## Purpose

Private network inside AWS.

---

## Components

```text
VPC
Subnet
Route Table
Internet Gateway
NAT Gateway
Security Group
NACL
```

---

## VPC Architecture

```text
Internet
    ↓
Internet Gateway
    ↓
Public Subnet
    ↓
Private Subnet
```

---

# 🔒 Security Groups

## Purpose

Virtual Firewall.

Controls:

```text
Inbound Traffic

Outbound Traffic
```

---

Example:

```text
Port 22 → SSH

Port 80 → HTTP

Port 443 → HTTPS
```

---

# 💽 EBS (Elastic Block Store)

## Purpose

Persistent Storage for EC2.

---

## Characteristics

```text
Block Storage

Persistent

Attached To EC2
```

---

# ⚖️ Elastic Load Balancer (ELB)

## Purpose

Distributes traffic across servers.

---

## Architecture

```text
Users
   ↓
Load Balancer
   ↓
EC2
EC2
EC2
```

---

## Types

```text
ALB

NLB

CLB
```

---

# 📈 Auto Scaling

## Purpose

Automatically increase or decrease servers.

---

## Example

```text
High Traffic
      ↓
Launch More EC2

Low Traffic
      ↓
Terminate EC2
```

---

# 🌍 Route 53

## Purpose

DNS Service.

---

Example:

```text
google.com
     ↓
IP Address
```

---

# 🗄 RDS (Relational Database Service)

## Supported Databases

```text
MySQL

PostgreSQL

MariaDB

Oracle

SQL Server
```

---

## Benefits

```text
Automated Backups

Replication

Patching

High Availability
```

---

# 📊 CloudWatch

## Purpose

Monitoring Service.

---

Monitors:

```text
CPU

Memory

Disk

Network

Logs
```

---

## Example

```text
CPU > 80%
       ↓
CloudWatch Alarm
       ↓
Notification
```

---

# 🔔 SNS (Simple Notification Service)

## Purpose

Notification Service.

---

Examples

```text
Email

SMS

Lambda

HTTP Endpoint
```

---

# 📩 SQS (Simple Queue Service)

## Purpose

Message Queue.

---

Architecture

```text
Producer
     ↓
Queue
     ↓
Consumer
```

---

# ⚡ Lambda

## Purpose

Serverless Compute.

Run code without managing servers.

---

Architecture

```text
Event
   ↓
Lambda Function
   ↓
Response
```

---

# 🌍 CloudFront

## Purpose

Content Delivery Network (CDN).

---

Flow

```text
User
   ↓
Nearest Edge Location
   ↓
CloudFront
   ↓
S3 / EC2
```

---

# 🔑 Secrets Manager

## Purpose

Store:

```text
Passwords

API Keys

Database Credentials
```

Securely.

---

# 📝 CloudTrail

## Purpose

Auditing Service.

Tracks:

```text
Who

Did What

When
```

---

# 🔥 Most Used AWS Services

```text
EC2

S3

IAM

VPC

RDS

ELB

Auto Scaling

Route53

CloudWatch

Lambda
```

---

# 🎯 AWS CLI Commands

## Configure AWS

```bash
aws configure
```

---

## List S3 Buckets

```bash
aws s3 ls
```

---

## Copy File To S3

```bash
aws s3 cp file.txt s3://mybucket
```

---

## List EC2 Instances

```bash
aws ec2 describe-instances
```

---

## View IAM Users

```bash
aws iam list-users
```

---

# 🚨 Troubleshooting Commands

## Check EC2 Status

```text
EC2
 ↓
Monitoring
 ↓
System Checks
```

---

## Check Security Group

```text
Port Open?

22

80

443
```

---

## Check Route53

```text
DNS Correct?
```

---

## Check Load Balancer

```text
Target Healthy?
```

---

# 🧠 AWS Interview Questions

## What is AWS?

Cloud computing platform.

---

## What is EC2?

Virtual Machine service.

---

## What is S3?

Object storage service.

---

## What is IAM?

Access management service.

---

## What is VPC?

Private virtual network.

---

## What is Route53?

Managed DNS service.

---

## What is Auto Scaling?

Automatically adjusts resources.

---

## What is Load Balancer?

Distributes traffic across servers.

---

## What is CloudWatch?

Monitoring service.

---

## What is Lambda?

Serverless compute service.

---

# 🏗 AWS Production Architecture

```text
Users
   ↓
Route53
   ↓
CloudFront
   ↓
Load Balancer
   ↓
EC2 Auto Scaling Group
   ↓
Application
   ↓
RDS
```

---

# 🚀 AWS + DevOps Workflow

```text
Developer
     ↓
GitHub
     ↓
Jenkins
     ↓
Docker
     ↓
ECR
     ↓
EKS / EC2
     ↓
Production
```

---

# 🔥 AWS Service Categories

```text
Compute
 ├── EC2
 ├── Lambda

Storage
 ├── S3
 ├── EBS

Networking
 ├── VPC
 ├── Route53
 ├── ELB

Database
 ├── RDS
 ├── DynamoDB

Monitoring
 ├── CloudWatch
 ├── CloudTrail

Security
 ├── IAM
 ├── Secrets Manager
```

---

# 🎯 One-Line Revision

```text
EC2 → Compute

S3 → Storage

IAM → Security

VPC → Networking

RDS → Database

CloudWatch → Monitoring

Lambda → Serverless
```

---

# 🚀 AWS Master Formula

```text
Users
   ↓
Route53
   ↓
Load Balancer
   ↓
EC2 / EKS
   ↓
Application
   ↓
RDS
   ↓
Monitoring
```
