# 🤖 16-Ansible-Deep-Dive.md

# Ansible Deep Dive

## Configuration Management, Automation & Infrastructure Operations

> Terraform creates infrastructure.
>
> Ansible configures infrastructure.
>
> Kubernetes runs applications on infrastructure.
>
> Together, they form a major part of modern DevOps automation.

---

# 📚 Table of Contents

1. What Is Ansible?
2. Why Ansible Exists
3. Configuration Management
4. Infrastructure Automation
5. How Ansible Works
6. Agent vs Agentless
7. Inventory
8. Playbooks
9. Tasks
10. Modules
11. Variables
12. Templates
13. Handlers
14. Roles
15. Ansible Vault
16. Ansible Architecture
17. Terraform vs Ansible
18. Real Production Workflow
19. Common Commands
20. Interview Questions

---

# Chapter 1: What Is Ansible?

Ansible is:

```text
Open Source
Automation Tool
Configuration Management Tool
Orchestration Tool
```

used to automate:

```text
Server Setup
Software Installation
Configuration Updates
Deployments
Patch Management
```

---

Simple Definition:

```text
Ansible automates repetitive system administration tasks.
```

---

Without Ansible:

```text
Server 1
 ↓
Install Nginx

Server 2
 ↓
Install Nginx

Server 3
 ↓
Install Nginx
```

Manual work.

---

With Ansible:

```text
One Command
      ↓
100 Servers Updated
```

---

# Chapter 2: Why Ansible Exists

Imagine:

```text
100 Linux Servers
```

Need:

```text
Install Docker
Install Nginx
Create Users
Update Configurations
```

---

Doing manually:

```text
SSH
SSH
SSH
SSH
SSH
...
```

Very slow.

---

Ansible automates everything.

---

# Chapter 3: Configuration Management

Configuration Management means:

```text
Keeping Servers
Configured Consistently
```

---

Example:

All servers should have:

```text
Docker
Nginx
Git
Python
```

installed.

---

Ansible ensures:

```text
Every Server
Same Configuration
```

---

# Chapter 4: Infrastructure Automation

Manual:

```text
Login
Install
Configure
Restart
```

---

Automated:

```text
Run Playbook
      ↓
Everything Happens Automatically
```

---

Benefits:

```text
Speed
Consistency
Reliability
Repeatability
```

---

# Chapter 5: How Ansible Works

Architecture:

```text
Control Node
      ↓ SSH
Managed Node 1

Managed Node 2

Managed Node 3
```

---

Control Node:

```text
Runs Ansible
```

---

Managed Nodes:

```text
Target Servers
```

---

# Chapter 6: Agent vs Agentless

Many tools require agents.

Example:

```text
Puppet Agent
Chef Agent
```

installed everywhere.

---

Ansible:

```text
Agentless
```

---

Uses:

```text
SSH
```

to communicate.

---

Major Advantage:

```text
No Software Installation
On Target Servers
```

---

# Chapter 7: Inventory

Inventory defines:

```text
Which Servers
Ansible Should Manage
```

---

Example:

```ini
[web]
server1
server2

[db]
server3
```

---

Meaning:

```text
Web Servers
Database Servers
```

---

# Chapter 8: Playbooks

Playbooks are the heart of Ansible.

---

Playbooks use:

```text
YAML
```

---

Example:

```yaml
- hosts: web

  tasks:

    - name: Install Nginx
      apt:
        name: nginx
        state: present
```

---

Think:

```text
Playbook
     =
Automation Script
```

---

# Chapter 9: Tasks

Tasks are individual actions.

---

Example:

```yaml
tasks:

  - name: Install Nginx

  - name: Start Nginx

  - name: Enable Nginx
```

---

Execution:

```text
Task 1
 ↓
Task 2
 ↓
Task 3
```

---

# Chapter 10: Modules

Modules perform actual work.

---

Examples:

```text
apt
yum
copy
service
file
user
git
docker_container
```

---

Example:

```yaml
- name: Install Git

  apt:
    name: git
    state: present
```

---

Ansible contains hundreds of modules.

---

# Chapter 11: Variables

Variables make playbooks reusable.

---

Example:

```yaml
app_name: nginx
```

---

Use:

```yaml
name: "{{ app_name }}"
```

---

Benefits:

```text
Reusable
Flexible
Maintainable
```

---

# Chapter 12: Templates

Templates allow dynamic configuration.

---

Example:

```jinja
server_name {{ domain_name }};
```

---

Ansible replaces:

```text
{{ domain_name }}
```

with actual values.

---

Used heavily for:

```text
Nginx
Apache
Application Configs
```

---

# Chapter 13: Handlers

Handlers run only when needed.

---

Example:

```yaml
notify:
  - restart nginx
```

---

Handler:

```yaml
handlers:

  - name: restart nginx
    service:
      name: nginx
      state: restarted
```

---

Benefit:

```text
Avoid Unnecessary Restarts
```

---

# Chapter 14: Roles

Large playbooks become difficult.

---

Solution:

```text
Roles
```

---

Structure:

```text
nginx-role

├── tasks
├── handlers
├── templates
├── vars
└── defaults
```

---

Think:

```text
Role
   =
Reusable Automation Package
```

---

# Chapter 15: Ansible Vault

Problem:

```text
Passwords
API Keys
Secrets
```

stored in plain text.

---

Solution:

```text
Ansible Vault
```

---

Encrypt:

```bash
ansible-vault encrypt secrets.yml
```

---

Benefits:

```text
Security
Compliance
Secret Management
```

---

# Chapter 16: Ansible Architecture

Complete Flow:

```text
Engineer
    ↓
Playbook
    ↓
Control Node
    ↓ SSH
Servers
```

---

Example:

```text
Install Docker
Create User
Deploy Application
```

all automatically.

---

# Chapter 17: Terraform vs Ansible

Most asked interview question.

---

Terraform:

```text
Creates Infrastructure
```

Example:

```text
EC2
VPC
Subnets
Load Balancers
```

---

Ansible:

```text
Configures Infrastructure
```

Example:

```text
Install Docker
Configure Nginx
Deploy App
```

---

Easy Memory:

```text
Terraform
    =
Build House

Ansible
    =
Furnish House
```

---

# Chapter 18: Real Production Workflow

Modern Workflow:

```text
Terraform
    ↓
Create EC2

Ansible
    ↓
Install Docker

Ansible
    ↓
Configure Nginx

Ansible
    ↓
Deploy Application
```

---

Production Flow:

```text
GitHub
    ↓
Jenkins
    ↓
Terraform
    ↓
AWS
    ↓
Ansible
    ↓
Application Deployment
```

---

# Chapter 19: Common Commands

Check Version:

```bash
ansible --version
```

---

Ping Servers:

```bash
ansible all -m ping
```

---

Run Playbook:

```bash
ansible-playbook site.yml
```

---

Inventory:

```bash
ansible-inventory --list
```

---

Encrypt Secret:

```bash
ansible-vault encrypt secrets.yml
```

---

# Chapter 20: Why DevOps Engineers Use Ansible

Ansible helps automate:

```text
Server Provisioning
Software Installation
Configuration Management
Application Deployment
Patch Management
```

Benefits:

```text
Fast
Reliable
Repeatable
Scalable
```

---

# 🔥 Interview Questions

### What Is Ansible?

Ansible is an open-source automation and configuration management tool used to automate server administration and deployments.

---

### Why Is Ansible Popular?

Because it is:

```text
Simple
Agentless
YAML Based
Easy To Learn
```

---

### What Is A Playbook?

A YAML file containing automation instructions.

---

### What Is Inventory?

A file that contains the list of servers managed by Ansible.

---

### What Is A Module?

A reusable component that performs a specific action such as installing software or managing files.

---

### What Is A Role?

A structured and reusable collection of Ansible tasks, handlers, templates, and variables.

---

### What Is Ansible Vault?

A feature used to encrypt sensitive information such as passwords and API keys.

---

### Difference Between Terraform And Ansible?

Terraform provisions infrastructure.

Ansible configures infrastructure.

---

### Why Is Ansible Called Agentless?

Because it uses SSH and does not require software agents on target machines.

---

# Mental Model

```text
Terraform
    =
Create Servers

Ansible
    =
Configure Servers

Docker
    =
Package Application

Kubernetes
    =
Run Application

Monitoring
    =
Observe Application
```

---

# One-Line Summary

Ansible is an agentless automation and configuration management tool that uses YAML playbooks to automate server configuration, application deployment, and operational tasks at scale.
