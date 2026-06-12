# 🔥 32-DevOps-Scenario-Based-Interviews.md

# DevOps Scenario-Based Interviews

## Real Production Problems, Debugging & Troubleshooting

> Most interviewers don't ask:
>
> ```text
> What is Docker?
> ```
>
> They ask:
>
> ```text
> Production is down.
>
> What will you do?
> ```
>
> This chapter focuses on real-world troubleshooting scenarios commonly asked in DevOps, Cloud, SRE, Platform Engineering, and Infrastructure interviews.

---

# 📚 Table of Contents

1. Troubleshooting Framework
2. Linux Scenarios
3. Networking Scenarios
4. DNS Scenarios
5. Git & CI/CD Scenarios
6. Docker Scenarios
7. Kubernetes Scenarios
8. AWS Scenarios
9. Database Scenarios
10. Monitoring Scenarios
11. SRE Scenarios
12. System Design Scenarios

---

# 🧠 Universal Troubleshooting Framework

Before any answer:

```text
Observe
 ↓
Collect Evidence
 ↓
Identify Scope
 ↓
Check Logs
 ↓
Find Root Cause
 ↓
Fix
 ↓
Validate
```

---

Golden Rule:

```text
Never Guess

Always Verify
```

---

# 🐧 Linux Scenarios

## Scenario 1

### Interview Question

A Linux server suddenly becomes very slow.

How would you troubleshoot?

### Answer

Step 1:

Check CPU:

```bash
top
```

or

```bash
htop
```

---

Step 2:

Check Memory:

```bash
free -h
```

---

Step 3:

Check Disk:

```bash
df -h
```

---

Step 4:

Check Processes:

```bash
ps aux --sort=-%cpu
```

---

Step 5:

Check Logs:

```bash
journalctl -xe
```

---

Expected Answer:

```text
CPU
Memory
Disk
Logs
Processes
```

Check all before restarting.

---

## Scenario 2

### Interview Question

Disk is 100% full.

What will you do?

### Answer

Check usage:

```bash
df -h
```

---

Find large files:

```bash
du -ah / | sort -rh | head
```

---

Common causes:

```text
Log Files

Backups

Temporary Files
```

---

Remove unnecessary data.

---

# 🌐 Networking Scenarios

## Scenario 3

### Interview Question

Users cannot access the application.

How would you troubleshoot?

### Answer

Check:

```text
DNS
 ↓
Load Balancer
 ↓
Nginx
 ↓
Application
 ↓
Database
```

---

Commands:

```bash
ping

curl

telnet

nc
```

---

Never assume application is the problem.

---

## Scenario 4

### Interview Question

Application is reachable internally but not externally.

### Answer

Check:

```text
Firewall

Security Group

NACL

Load Balancer

Ingress
```

---

Most likely:

```text
Network Configuration Issue
```

---

# 🌍 DNS Scenarios

## Scenario 5

### Interview Question

Website is down but server is healthy.

### Answer

Check DNS.

Commands:

```bash
nslookup example.com

dig example.com
```

---

Verify:

```text
Correct IP

DNS Propagation

Route53 Records
```

---

# 🌳 Git & CI/CD Scenarios

## Scenario 6

### Interview Question

Developer says Jenkins pipeline stopped triggering.

### Answer

Check:

```text
GitHub Webhook
 ↓
Jenkins Connectivity
 ↓
Pipeline Configuration
```

---

Verify:

```text
Webhook Deliveries
```

inside GitHub.

---

Common cause:

```text
Webhook Failure
```

---

## Scenario 7

### Interview Question

Pipeline suddenly started failing.

### Answer

Check:

```text
Recent Changes
```

---

Review:

```text
Build Logs

Environment Variables

Credentials

Dependencies
```

---

Golden Question:

```text
What Changed?
```

---

# 🐳 Docker Scenarios

## Scenario 8

### Interview Question

Container exits immediately after starting.

### Answer

Check:

```bash
docker logs container-id
```

---

Common causes:

```text
Wrong Command

Application Crash

Missing Environment Variables
```

---

## Scenario 9

### Interview Question

Container works locally but fails in production.

### Answer

Compare:

```text
Environment Variables

Volumes

Ports

Network Configuration
```

---

Verify image version.

---

# ☸️ Kubernetes Scenarios

## Scenario 10

### Interview Question

Pod is in CrashLoopBackOff.

### Answer

Check:

```bash
kubectl describe pod pod-name

kubectl logs pod-name

kubectl get events
```

---

Common causes:

```text
Application Crash

Wrong ConfigMap

Secret Missing

Database Connection Failure
```

---

## Scenario 11

### Interview Question

Pod remains in Pending state.

### Answer

Check:

```bash
kubectl describe pod
```

---

Possible reasons:

```text
Insufficient CPU

Insufficient Memory

Node Selector Issue

Storage Issue
```

---

## Scenario 12

### Interview Question

Service is not reachable.

### Answer

Check:

```text
Pod Running?

Service Exists?

Endpoints?

Ingress?
```

---

Commands:

```bash
kubectl get svc

kubectl get endpoints
```

---

# ☁️ AWS Scenarios

## Scenario 13

### Interview Question

EC2 instance is not reachable.

### Answer

Check:

```text
Instance Running?

Security Group?

NACL?

Route Table?

Public IP?
```

---

Most common issue:

```text
Security Group
```

---

## Scenario 14

### Interview Question

Application cannot access S3.

### Answer

Check:

```text
IAM Role

Bucket Policy

Access Keys

Region
```

---

Most common cause:

```text
Permission Issue
```

---

## Scenario 15

### Interview Question

Load Balancer returns 503 errors.

### Answer

Check:

```text
Target Group

Health Checks

Application Status
```

---

Usually:

```text
Targets Unhealthy
```

---

# 🗄 Database Scenarios

## Scenario 16

### Interview Question

Database suddenly becomes slow.

### Answer

Check:

```text
CPU

Memory

Connections

Slow Queries

Disk I/O
```

---

PostgreSQL:

```sql
SELECT * FROM pg_stat_activity;
```

---

Most common cause:

```text
Slow Queries
```

---

## Scenario 17

### Interview Question

Application cannot connect to database.

### Answer

Verify:

```text
Database Running?

Port Open?

Credentials Correct?

Firewall?
```

---

Test:

```bash
telnet db-host 5432
```

---

# 📊 Monitoring Scenarios

## Scenario 18

### Interview Question

CPU alert fired.

What do you do?

### Answer

Check:

```text
Real Spike?

False Alert?

Recent Deployment?
```

---

Commands:

```bash
top

htop
```

---

Review dashboards.

---

## Scenario 19

### Interview Question

Memory usage keeps increasing.

### Answer

Investigate:

```text
Memory Leak

Caching Problem

Large Workloads
```

---

Check:

```bash
free -h
```

---

# 🚨 SRE Scenarios

## Scenario 20

### Interview Question

Production outage occurs at 2 AM.

What is your approach?

### Answer

Step 1:

Assess impact.

---

Step 2:

Gather logs.

---

Step 3:

Check monitoring.

---

Step 4:

Mitigate.

---

Step 5:

Restore service.

---

Step 6:

Perform postmortem.

---

Never panic.

---

## Scenario 21

### Interview Question

An alert keeps firing every few minutes.

### Answer

Investigate:

```text
False Alert?

Threshold Too Low?

Real Issue?
```

---

Avoid:

```text
Alert Fatigue
```

---

# 🏗 System Design Scenarios

## Scenario 22

### Interview Question

Website traffic increases from 10,000 users to 1 million users.

How would you scale?

### Answer

Use:

```text
Load Balancer
 ↓
Multiple Servers
 ↓
Redis Cache
 ↓
Database Replicas
```

---

Horizontal scaling preferred.

---

## Scenario 23

### Interview Question

Database becomes bottleneck.

What are your options?

### Answer

Options:

```text
Caching

Read Replicas

Sharding

Query Optimization
```

---

## Scenario 24

### Interview Question

How would you design a highly available application?

### Answer

Architecture:

```text
Users
 ↓
Load Balancer
 ↓
Multiple Application Servers
 ↓
Redis
 ↓
Database Replicas
```

---

Eliminate:

```text
Single Point Of Failure
```

---

# 🔥 Most Important Interview Questions

1. Production is down. What do you do?
2. Pod is CrashLoopBackOff. How do you debug?
3. EC2 is unreachable. What do you check?
4. Jenkins pipeline failed. What next?
5. Website is slow. How do you investigate?
6. Database is slow. How do you troubleshoot?
7. Users cannot access application. What do you verify?
8. Load balancer returns 503. What do you check?
9. High CPU alert fired. What steps do you take?
10. How would you scale a system to 1 million users?

---

# 🧠 Interview Mental Model

Always answer using:

```text
Problem
 ↓
Evidence
 ↓
Logs
 ↓
Metrics
 ↓
Root Cause
 ↓
Fix
 ↓
Validation
```

---

# Golden Interview Rule

When asked:

```text
What Would You Do?
```

Never answer:

```text
Restart Server
```

First answer:

```text
Investigate

Collect Logs

Review Metrics

Identify Root Cause

Then Fix
```

---

# One-Line Summary

Strong DevOps engineers are not judged by how many tools they know—they are judged by how effectively they diagnose, troubleshoot, and resolve production issues using a structured and evidence-driven approach.
