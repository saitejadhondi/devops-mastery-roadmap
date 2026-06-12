# 🌎 07-Terraform-Infrastructure-as-Code.md

# Terraform & Infrastructure as Code (IaC)

## Understanding How Modern Companies Build Cloud Infrastructure

> AWS gives us servers.
>
> AWS gives us databases.
>
> AWS gives us networks.
>
> AWS gives us Kubernetes clusters.
>
> But creating everything manually is a nightmare.
>
> Terraform was created to solve that problem.

---

# 📚 Table of Contents

1. The Problem Before Terraform
2. Why Terraform Exists
3. What Is Infrastructure?
4. What Is Infrastructure as Code?
5. What Is Terraform?
6. Terraform Architecture
7. Providers
8. Resources
9. State File
10. Terraform Workflow
11. HCL Language
12. Variables
13. Outputs
14. Modules
15. Remote State
16. Terraform & AWS
17. Terraform in CI/CD
18. Real Production Architecture
19. Interview Questions

---

# Chapter 1: Life Before Terraform

Imagine your company wants:

```text
1 VPC
3 Subnets
2 EC2 Servers
1 Database
1 Load Balancer
1 EKS Cluster
```

Without Terraform:

Engineer logs into AWS Console.

---

Clicks:

```text
Create VPC
Create Subnet
Create Security Group
Create EC2
Create Database
Create Load Balancer
Create EKS
```

Manually.

---

Problems:

```text
Slow
Error-Prone
Hard To Repeat
No Version Control
No Audit Trail
```

---

Question:

How do we know:

```text
Who created server?
When created?
Why created?
What changed?
```

Very difficult.

---

# Real Enterprise Problem

Suppose Production has:

```text
50 Servers
10 Databases
5 Load Balancers
```

Now company wants:

```text
Development Environment
Testing Environment
Staging Environment
```

Should engineers click everything again?

No.

Impossible at scale.

---

# Chapter 2: Why Terraform Exists

Software engineers asked:

```text
Why can code be version controlled
but infrastructure cannot?
```

---

Terraform introduced:

# Infrastructure as Code

(IaC)

Meaning:

```text
Infrastructure
Becomes
Code
```

---

Instead of:

```text
Click Buttons
```

we write:

```text
Configuration Files
```

---

Now infrastructure can be:

```text
Stored In Git
Reviewed
Version Controlled
Automated
Repeated
```

Exactly like software.

---

# Chapter 3: What Is Infrastructure?

Infrastructure means:

Everything required to run software.

---

Examples:

```text
Servers
Networks
Databases
Storage
Load Balancers
DNS
Kubernetes Clusters
```

---

Think:

```text
Application
      +
Infrastructure
      =
Working System
```

---

Example

Shopping App:

```text
Frontend
Backend
Database
Network
Load Balancer
Storage
```

All together:

```text
Infrastructure
```

---

# Chapter 4: What Is Infrastructure as Code?

Traditional Method:

```text
Human Creates Infrastructure
```

---

IaC Method:

```text
Code Creates Infrastructure
```

---

Example:

Instead of:

```text
AWS Console
Click Click Click
```

Write:

```hcl
resource "aws_instance" "web" {
  instance_type = "t2.micro"
}
```

---

Terraform creates infrastructure automatically.

---

Benefits:

```text
Consistency
Repeatability
Automation
Version Control
Auditability
```

---

# Chapter 5: What Is Terraform?

Terraform is:

# Infrastructure as Code Tool

Created by:

HashiCorp

---

Simple Definition:

```text
Terraform creates and manages infrastructure using code.
```

---

Think:

```text
Git
   =
Code Management

Terraform
   =
Infrastructure Management
```

---

Mental Model:

```text
Terraform
    =
Cloud Automation Engine
```

---

# Chapter 6: Terraform Architecture

High-Level Flow

```text
Terraform Code
       ↓
Terraform
       ↓
AWS API
       ↓
AWS Resources
```

---

Example

```text
main.tf
      ↓
terraform apply
      ↓
AWS Creates Resources
```

---

Terraform does NOT create servers directly.

Terraform talks to AWS APIs.

AWS creates resources.

---

# Chapter 7: Providers

Question:

How does Terraform talk to AWS?

---

Answer:

# Provider

---

Provider = Plugin

---

Examples:

```text
AWS Provider
Azure Provider
Google Cloud Provider
Kubernetes Provider
Docker Provider
```

---

Example:

```hcl
provider "aws" {
  region = "ap-south-1"
}
```

Meaning:

```text
Use AWS
Mumbai Region
```

---

# Chapter 8: Resources

Most important Terraform concept.

---

Resource = Infrastructure Object

---

Examples:

```text
EC2
VPC
Subnet
S3
Database
```

All are resources.

---

Example:

```hcl
resource "aws_instance" "web" {

  ami           = "ami-123"

  instance_type = "t2.micro"

}
```

---

Meaning:

```text
Create EC2 Instance
```

---

Terraform reads file.

AWS creates server.

---

# Chapter 9: State File

Most interview questions come from here.

---

Question:

How does Terraform know:

```text
What Already Exists?
```

---

Answer:

# State File

---

File:

```text
terraform.tfstate
```

---

Contains:

```text
Resources Created
Resource IDs
Mappings
Metadata
```

---

Think:

```text
Terraform Memory
```

---

Without state:

Terraform would not know:

```text
Existing Servers
Existing Databases
Existing Networks
```

---

# Chapter 10: Terraform Workflow

Every Terraform project follows:

```text
Write
Plan
Apply
Destroy
```

---

# Step 1

Write configuration.

```hcl
resource "aws_instance" "web" {
}
```

---

# Step 2

Initialize

```bash
terraform init
```

Downloads providers.

---

# Step 3

Plan

```bash
terraform plan
```

Shows:

```text
What Terraform Intends To Do
```

Example:

```text
+ Create EC2
+ Create VPC
+ Create Security Group
```

Nothing created yet.

---

# Step 4

Apply

```bash
terraform apply
```

Actually creates resources.

---

# Step 5

Destroy

```bash
terraform destroy
```

Removes resources.

---

# Complete Workflow

```text
Write Code
     ↓
terraform init
     ↓
terraform plan
     ↓
terraform apply
     ↓
Infrastructure Created
```

---

# Chapter 11: HCL

Terraform uses:

# HCL

HashiCorp Configuration Language

---

Example:

```hcl
resource "aws_s3_bucket" "logs" {

  bucket = "company-logs"

}
```

---

Purpose:

```text
Human Readable
Easy To Understand
Declarative
```

---

# Declarative vs Imperative

Imperative:

```text
Step 1
Step 2
Step 3
```

Tell system HOW.

---

Terraform:

```text
Desired State
```

Tell system WHAT.

---

Example:

```text
Need 3 Servers
```

Terraform figures out HOW.

---

# Chapter 12: Variables

Hardcoding:

```hcl
instance_type = "t2.micro"
```

Not flexible.

---

Use Variables.

```hcl
variable "instance_type" {
}
```

---

Benefits:

```text
Reusable
Configurable
Cleaner
```

---

# Chapter 13: Outputs

Need information after creation.

Example:

```text
Public IP
DNS Name
Load Balancer URL
```

---

Terraform provides:

# Outputs

---

Example:

```hcl
output "server_ip" {
}
```

---

Displays result.

---

# Chapter 14: Modules

Imagine:

```text
Create VPC
Create Subnets
Create Security Groups
```

Repeated in many projects.

---

Need reuse.

---

Solution:

# Modules

---

Think:

```text
Function In Programming
```

---

Benefits:

```text
Reusable
Maintainable
Standardized
```

---

# Chapter 15: Remote State

Problem:

State file stored locally.

---

Team members cannot share.

---

Solution:

Remote State.

---

Common Storage:

```text
S3
Terraform Cloud
```

---

Benefits:

```text
Team Collaboration
Backup
Consistency
```

---

# Chapter 16: Terraform & AWS

Real Example

Terraform Creates:

```text
VPC
Subnets
Security Groups
EC2
RDS
S3
EKS
```

Automatically.

---

Architecture:

```text
Terraform
      ↓
AWS
      ↓
VPC
EC2
RDS
EKS
```

---

# Chapter 17: Terraform In CI/CD

Terraform is often automated.

---

Pipeline:

```text
GitHub
    ↓
Webhook
    ↓
Jenkins
    ↓
Terraform Plan
    ↓
Approval
    ↓
Terraform Apply
```

---

Infrastructure becomes automated.

---

# Chapter 18: Complete Enterprise Architecture

```text
Developer
    ↓
Git Push
    ↓
GitHub
    ↓
Webhook
    ↓
Jenkins
    ↓
Terraform
    ↓
AWS Infrastructure
    ↓
EKS Cluster
    ↓
Applications
```

---

Now entire infrastructure can be created from code.

---

# Infrastructure Lifecycle

```text
Code
 ↓
Terraform
 ↓
AWS Resources
 ↓
Application Deployment
 ↓
Monitoring
```

---

# Mental Model

Think:

```text
AWS
   =
Infrastructure Provider

Terraform
   =
Infrastructure Automation

Provider
   =
Cloud Connector

Resource
   =
Infrastructure Object

State File
   =
Terraform Memory

Module
   =
Reusable Infrastructure Component
```

---

# 🔥 Interview Questions

### What Is Terraform?

Terraform is an Infrastructure as Code tool used to provision and manage infrastructure using configuration files.

---

### What Is Infrastructure as Code?

Managing infrastructure through code rather than manual processes.

---

### What Is A Provider?

A plugin that allows Terraform to communicate with a target platform like AWS.

---

### What Is A Resource?

An infrastructure object managed by Terraform.

---

### What Is Terraform State?

A file that tracks infrastructure managed by Terraform.

---

### Difference Between Terraform Plan And Apply?

Plan shows intended changes.

Apply performs those changes.

---

### Why Use Modules?

To reuse infrastructure code and reduce duplication.

---

### Why Use Remote State?

To share and safely manage Terraform state across teams.

---

### Why Terraform Instead Of AWS Console?

Terraform provides automation, version control, consistency, repeatability, and collaboration.

---

# One-Line Summary

Terraform transforms cloud infrastructure into version-controlled code, allowing entire AWS environments to be created, updated, and destroyed automatically and consistently.
