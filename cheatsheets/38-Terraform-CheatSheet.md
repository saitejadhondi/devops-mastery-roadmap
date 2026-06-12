# 🏗 Terraform Cheat Sheet

> Quick Revision Guide for Terraform, Infrastructure as Code (IaC), Cloud & DevOps Interviews

---

# 🎯 What is Terraform?

Terraform is an **Infrastructure as Code (IaC)** tool developed by  [HashiCorp](https://www.hashicorp.com?utm_source=chatgpt.com).

It allows you to:

```text
Create Infrastructure

Modify Infrastructure

Delete Infrastructure

Version Infrastructure
```

Using code instead of manual cloud console operations.

---

# 🗺 Terraform Workflow

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

# 🧠 Core Concepts

| Component  | Purpose                     |
| ---------- | --------------------------- |
| Provider   | Connects Terraform to Cloud |
| Resource   | Infrastructure Object       |
| Variable   | Dynamic Input               |
| Output     | Return Value                |
| State File | Tracks Infrastructure       |
| Module     | Reusable Code               |
| Backend    | Stores State File           |

---

# ☁️ Provider

Provider tells Terraform where to create resources.

Example:

```hcl
provider "aws" {
  region = "ap-south-1"
}
```

---

# 🚀 Resource

Resource = Actual Infrastructure.

Example:

```hcl
resource "aws_instance" "web" {
  ami           = "ami-123456"
  instance_type = "t2.micro"
}
```

---

# 📦 Common Resource Types

```text
aws_instance

aws_s3_bucket

aws_vpc

aws_subnet

aws_security_group

aws_lb

aws_rds_instance
```

---

# ⚙️ Terraform Commands

## Initialize Project

```bash
terraform init
```

Downloads:

```text
Providers

Plugins

Dependencies
```

---

## Validate Code

```bash
terraform validate
```

Checks syntax errors.

---

## Format Code

```bash
terraform fmt
```

---

## View Execution Plan

```bash
terraform plan
```

Shows:

```text
What Will Be Created

What Will Change

What Will Be Deleted
```

---

## Apply Changes

```bash
terraform apply
```

---

## Auto Approve

```bash
terraform apply -auto-approve
```

---

## Destroy Infrastructure

```bash
terraform destroy
```

---

## Auto Destroy

```bash
terraform destroy -auto-approve
```

---

# 📋 Important Terraform Commands

```bash
terraform init

terraform validate

terraform fmt

terraform plan

terraform apply

terraform destroy

terraform output

terraform state list
```

---

# 📂 Variables

Variables make code reusable.

Example:

```hcl
variable "instance_type" {
  default = "t2.micro"
}
```

Usage:

```hcl
instance_type = var.instance_type
```

---

# 📤 Outputs

Used to display values.

Example:

```hcl
output "public_ip" {
  value = aws_instance.web.public_ip
}
```

View:

```bash
terraform output
```

---

# 🗄 Terraform State

Terraform stores infrastructure information in:

```text
terraform.tfstate
```

---

# Why State File?

Terraform needs to know:

```text
What Exists

What Changed

What Must Be Updated
```

---

# View Resources In State

```bash
terraform state list
```

---

# View Resource Details

```bash
terraform state show RESOURCE
```

Example:

```bash
terraform state show aws_instance.web
```

---

# 📁 Modules

Modules allow code reuse.

Example:

```text
Network Module

EC2 Module

Database Module
```

---

# Module Structure

```text
modules/
   ├── vpc/
   ├── ec2/
   └── rds/
```

---

# Calling Module

```hcl
module "ec2" {
  source = "./modules/ec2"
}
```

---

# 🌍 Remote State

Production environments store state remotely.

Common Backend:

```text
AWS S3
```

Example:

```hcl
terraform {
  backend "s3" {
    bucket = "terraform-state"
    key    = "prod.tfstate"
    region = "ap-south-1"
  }
}
```

---

# 🔒 State Locking

Problem:

```text
Two Engineers Run Terraform
At Same Time
```

Solution:

```text
State Locking
```

AWS:

```text
S3 + DynamoDB
```

---

# ☁️ AWS Resources Cheat Sheet

## EC2

```hcl
resource "aws_instance" "web" {
  ami           = "ami-123"
  instance_type = "t2.micro"
}
```

---

## S3 Bucket

```hcl
resource "aws_s3_bucket" "bucket" {
  bucket = "mybucket"
}
```

---

## Security Group

```hcl
resource "aws_security_group" "web" {
  name = "web-sg"
}
```

---

# 🔥 Most Used Workflow

```bash
terraform init

terraform fmt

terraform validate

terraform plan

terraform apply
```

---

# 📊 Terraform Lifecycle

```text
Code
 ↓
Init
 ↓
Plan
 ↓
Apply
 ↓
Infrastructure
 ↓
State File
```

---

# 🚨 Troubleshooting Commands

## Check State

```bash
terraform state list
```

---

## Refresh State

```bash
terraform refresh
```

---

## Show Outputs

```bash
terraform output
```

---

## Validate Configuration

```bash
terraform validate
```

---

# 🔄 Terraform vs CloudFormation

| Terraform    | CloudFormation |
| ------------ | -------------- |
| Multi Cloud  | AWS Only       |
| Open Source  | AWS Managed    |
| HCL Language | JSON/YAML      |
| More Popular | AWS Specific   |

---

# ⚔ Terraform vs Ansible

Terraform:

```text
Creates Infrastructure
```

Examples:

```text
EC2

VPC

S3

RDS
```

---

Ansible:

```text
Configures Infrastructure
```

Examples:

```text
Install Nginx

Update Packages

Configure Servers
```

---

# 🧠 Terraform Interview Questions

## What is Terraform?

Infrastructure as Code tool.

---

## What is Infrastructure as Code?

Managing infrastructure using code instead of manual actions.

---

## What is Terraform State?

File that tracks infrastructure.

```text
terraform.tfstate
```

---

## What is Provider?

Plugin used to communicate with cloud platforms.

Example:

```text
AWS

Azure

GCP
```

---

## What is Resource?

Actual infrastructure object.

Example:

```text
EC2

S3

VPC
```

---

## What is Module?

Reusable Terraform code.

---

## What is Backend?

Location where state file is stored.

---

## Why Remote State?

```text
Team Collaboration

Backup

State Locking
```

---

## Terraform Plan vs Apply?

Plan:

```text
Preview Changes
```

Apply:

```text
Execute Changes
```

---

# 🚀 Terraform + AWS Workflow

```text
Terraform Code
        ↓
terraform init
        ↓
terraform plan
        ↓
terraform apply
        ↓
AWS Resources
        ↓
EC2
S3
VPC
RDS
```

---

# 🏭 Real DevOps Workflow

```text
Developer
      ↓
GitHub
      ↓
Jenkins
      ↓
Terraform
      ↓
AWS Infrastructure
      ↓
Docker
      ↓
Kubernetes
      ↓
Production
```

---

# 🔥 Most Important Terraform Files

```text
main.tf

variables.tf

outputs.tf

providers.tf

terraform.tfvars

terraform.tfstate
```

---

# 🎯 One-Line Revision

```text
Provider → Resource → Init → Plan → Apply → State
```

---

# 🧠 Terraform Master Formula

```text
Infrastructure
      ↓
Convert To Code
      ↓
Terraform
      ↓
Plan
      ↓
Apply
      ↓
Cloud Resources
```
