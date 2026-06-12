# ☸️ 22-Kubernetes-Advanced.md

# Kubernetes Advanced

## Helm, RBAC, Namespaces, StatefulSets, PV/PVC, Ingress, Network Policies & Service Mesh

> Running containers is easy.
>
> Running containers reliably at production scale is hard.
>
> This is where advanced Kubernetes concepts become essential.
>
> Most real-world Kubernetes interviews focus heavily on:
>
> * Helm
> * RBAC
> * StatefulSets
> * PV/PVC
> * Ingress
> * Network Policies
> * Service Mesh
>
> rather than basic Pods and Deployments.

---

# 📚 Table of Contents

1. Why Advanced Kubernetes?
2. Namespaces
3. Resource Quotas
4. RBAC
5. Service Accounts
6. Persistent Volumes (PV)
7. Persistent Volume Claims (PVC)
8. Storage Classes
9. StatefulSets
10. DaemonSets
11. Jobs
12. CronJobs
13. Ingress
14. Ingress Controller
15. Helm
16. ConfigMaps
17. Secrets
18. Network Policies
19. Service Mesh
20. Istio
21. Production Architecture
22. Interview Questions

---

# Chapter 1: Why Advanced Kubernetes?

Basic Kubernetes teaches:

```text
Pod
Deployment
Service
ReplicaSet
```

---

Production Kubernetes requires:

```text
Security
Storage
Networking
Traffic Management
Observability
```

---

Architecture:

```text
Users
 ↓
Ingress
 ↓
Services
 ↓
Pods
 ↓
Persistent Storage
```

---

# Chapter 2: Namespaces

Namespaces provide:

```text
Logical Isolation
```

inside a cluster.

---

Example:

```text
production

staging

development
```

---

Architecture:

```text
Cluster
 │
 ├── production
 │
 ├── staging
 │
 └── development
```

---

Benefits:

```text
Isolation
Organization
Security
```

---

Command:

```bash
kubectl get namespaces
```

---

# Chapter 3: Resource Quotas

Prevent resource abuse.

---

Example:

```text
Namespace
    ↓
CPU Limit
Memory Limit
Pod Limit
```

---

Benefits:

```text
Fair Resource Usage
Cluster Stability
```

---

# Chapter 4: RBAC

RBAC:

```text
Role Based Access Control
```

---

Purpose:

```text
Control Access
```

inside Kubernetes.

---

Example:

```text
Developer
     ↓
Can View Pods

Admin
     ↓
Can Delete Pods
```

---

Architecture:

```text
User
 ↓
Role
 ↓
Permissions
```

---

Interview Favorite:

```text
RBAC controls who can do what.
```

---

# Chapter 5: Service Accounts

Applications inside Kubernetes need identities.

---

Example:

```text
Pod
 ↓
Service Account
 ↓
Access Kubernetes API
```

---

Used for:

```text
Authentication
Authorization
```

---

# Chapter 6: Persistent Volumes (PV)

Problem:

```text
Container Deleted
      ↓
Data Lost
```

---

Solution:

```text
Persistent Volume
```

---

Definition:

```text
Storage Resource
Managed By Kubernetes
```

---

Architecture:

```text
Storage
   ↓
PV
```

---

# Chapter 7: Persistent Volume Claims (PVC)

Applications request storage.

---

Example:

```text
Pod
 ↓
PVC
 ↓
PV
```

---

Think:

```text
PV
   =
Actual Storage

PVC
   =
Storage Request
```

---

Interview Favorite:

```text
PV vs PVC
```

---

# Chapter 8: Storage Classes

Automatically create storage.

---

Example:

```text
PVC
 ↓
Storage Class
 ↓
AWS EBS
```

---

Benefits:

```text
Dynamic Provisioning
```

---

# Chapter 9: StatefulSets

Deployments work well for:

```text
Stateless Applications
```

---

Examples:

```text
Frontend
API
```

---

Stateful Applications:

```text
Databases
Kafka
Redis
```

---

Need:

```text
Stable Identity
Persistent Storage
```

---

Solution:

```text
StatefulSet
```

---

Interview Favorite:

```text
Deployment
     =
Stateless

StatefulSet
     =
Stateful
```

---

# Chapter 10: DaemonSets

Run one pod per node.

---

Example:

```text
Node 1
 ↓
Pod

Node 2
 ↓
Pod

Node 3
 ↓
Pod
```

---

Common Use Cases:

```text
Monitoring Agents
Log Collectors
Security Agents
```

---

Examples:

```text
Prometheus Node Exporter
Fluentd
```

---

# Chapter 11: Jobs

Run tasks once.

---

Examples:

```text
Database Migration
Data Processing
Batch Work
```

---

Flow:

```text
Job
 ↓
Run
 ↓
Complete
```

---

# Chapter 12: CronJobs

Scheduled Jobs.

---

Example:

```text
Every Night
At 2 AM
```

---

Use Cases:

```text
Backups
Reports
Maintenance
```

---

Linux Equivalent:

```text
Cron
```

---

# Chapter 13: Ingress

Problem:

```text
Many Services
One External Entry Point Needed
```

---

Solution:

```text
Ingress
```

---

Architecture:

```text
Users
 ↓
Ingress
 ↓
Service A

Service B

Service C
```

---

Think:

```text
Ingress
     =
Traffic Router
```

---

# Chapter 14: Ingress Controller

Ingress only defines rules.

Need:

```text
Actual Traffic Handler
```

---

Examples:

```text
Nginx Ingress
Traefik
HAProxy
```

---

Architecture:

```text
User
 ↓
Nginx Ingress Controller
 ↓
Services
```

---

# Chapter 15: Helm

Helm:

```text
Package Manager
For Kubernetes
```

---

Think:

```text
apt
     =
Linux Packages

helm
     =
Kubernetes Packages
```

---

Benefits:

```text
Reusable
Versioned
Configurable
```

---

Install:

```bash
helm install myapp chart/
```

---

Interview Favorite:

```text
Helm = Kubernetes Package Manager
```

---

# Chapter 16: ConfigMaps

Store:

```text
Application Configuration
```

---

Examples:

```text
URLs
Feature Flags
Settings
```

---

Architecture:

```text
ConfigMap
 ↓
Pod
```

---

# Chapter 17: Secrets

Store:

```text
Passwords
Tokens
Certificates
```

---

Never hardcode secrets.

---

Architecture:

```text
Secret
 ↓
Pod
```

---

Used with:

```text
Vault
AWS Secrets Manager
```

---

# Chapter 18: Network Policies

Control communication between pods.

---

Without Policy:

```text
Pod A
 ↔
Pod B
```

---

With Policy:

```text
Pod A
 ✖
Pod B
```

unless explicitly allowed.

---

Purpose:

```text
Microsegmentation
Security
```

---

# Chapter 19: Service Mesh

Large microservice environments become complex.

---

Need:

```text
Traffic Control
Observability
Security
```

---

Solution:

```text
Service Mesh
```

---

Architecture:

```text
Service A
 ↔
Service Mesh
 ↔
Service B
```

---

# Chapter 20: Istio

Most popular Service Mesh.

---

Provides:

```text
Traffic Routing
mTLS
Observability
Policy Enforcement
```

---

Architecture:

```text
Application
 ↓
Envoy Proxy
 ↓
Application
```

---

Benefits:

```text
Security
Visibility
Traffic Control
```

---

# Chapter 21: Real Production Architecture

Modern Kubernetes:

```text
Users
 ↓
Load Balancer
 ↓
Ingress Controller
 ↓
Services
 ↓
Pods
 ↓
PVC
 ↓
Database
```

---

Enterprise Architecture:

```text
Users
 ↓
CloudFront
 ↓
ALB
 ↓
Ingress
 ↓
Microservices
 ↓
Databases
```

---

# Chapter 22: Why Advanced Kubernetes Matters

Production clusters require:

```text
Storage
Security
Networking
Observability
Scalability
```

These concepts make Kubernetes production-ready.

---

# 🔥 Interview Questions

### What Is A Namespace?

A logical isolation boundary within a Kubernetes cluster.

---

### What Is RBAC?

Role-Based Access Control used to manage permissions in Kubernetes.

---

### What Is A Service Account?

An identity used by applications running inside Kubernetes.

---

### Difference Between PV And PVC?

PV:

```text
Actual Storage
```

PVC:

```text
Request For Storage
```

---

### Deployment vs StatefulSet?

Deployment:

```text
Stateless Applications
```

StatefulSet:

```text
Stateful Applications
```

---

### What Is A DaemonSet?

Runs exactly one pod on every node.

---

### What Is A Job?

Runs a task once and completes.

---

### What Is A CronJob?

Runs tasks on a schedule.

---

### What Is Ingress?

A Kubernetes resource that routes external traffic to services.

---

### What Is An Ingress Controller?

Software that implements Ingress rules.

---

### What Is Helm?

A package manager for Kubernetes.

---

### What Is A ConfigMap?

Stores non-sensitive application configuration.

---

### What Is A Secret?

Stores sensitive information securely.

---

### What Is A Network Policy?

Controls network communication between pods.

---

### What Is A Service Mesh?

Infrastructure layer that manages service-to-service communication.

---

### What Is Istio?

A popular Kubernetes service mesh providing traffic management, security, and observability.

---

# Mental Model

```text
Users
 ↓
Load Balancer
 ↓
Ingress
 ↓
Services
 ↓
Pods
 ↓
Persistent Storage
```

---

# Kubernetes Production Stack

```text
Helm
 ↓
Deploy Applications

RBAC
 ↓
Control Access

Ingress
 ↓
Route Traffic

PV/PVC
 ↓
Store Data

Network Policies
 ↓
Secure Traffic

Istio
 ↓
Manage Services
```

---

# One-Line Summary

Advanced Kubernetes introduces production-grade concepts such as Helm, RBAC, StatefulSets, Persistent Storage, Ingress, Network Policies, and Service Meshes that enable secure, scalable, and reliable cloud-native applications.
