# 🔥 28-Production-Troubleshooting-Handbook.md

# Production Troubleshooting Handbook

## Linux, Networking, Docker, Kubernetes, AWS, Databases, CI/CD & Real Production Issues

> A good engineer knows tools.
>
> A great engineer can debug problems.
>
> In production, nobody asks:
>
> ```text
> What Is Docker?
> ```
>
> They ask:
>
> ```text
> Why Is Production Down?
> ```
>
> Troubleshooting is one of the most valuable skills in DevOps, SRE, Cloud, and Platform Engineering.

---

# 📚 Table of Contents

1. Troubleshooting Mindset
2. Golden Troubleshooting Rule
3. Incident Workflow
4. Linux Issues
5. CPU Problems
6. Memory Problems
7. Disk Problems
8. Network Issues
9. DNS Issues
10. HTTP/HTTPS Issues
11. Nginx Issues
12. Docker Issues
13. Kubernetes Issues
14. Database Issues
15. AWS Issues
16. CI/CD Issues
17. Monitoring Issues
18. Logs Investigation
19. Root Cause Analysis
20. Production Checklist
21. Interview Questions

---

# Chapter 1: Troubleshooting Mindset

Never start with:

```text
Random Commands
Random Restarts
Random Fixes
```

---

Start with:

```text
Observe
Investigate
Verify
Fix
Validate
```

---

Golden Rule:

```text
Understand Before Fixing
```

---

# Chapter 2: Golden Troubleshooting Rule

Always ask:

```text
What Changed?
```

---

Most production failures occur after:

```text
Deployment
Configuration Change
Infrastructure Change
Database Change
```

---

Interview Favorite:

```text
What Changed?
=
First Question
```

---

# Chapter 3: Incident Workflow

Standard Workflow:

```text
Alert
 ↓
Identify Problem
 ↓
Collect Evidence
 ↓
Find Root Cause
 ↓
Fix
 ↓
Validate
 ↓
Postmortem
```

---

Never Skip:

```text
Evidence Collection
```

---

# Chapter 4: Linux Issues

Server Slow?

Check:

```bash
top
```

---

Processes:

```bash
ps aux
```

---

Memory:

```bash
free -h
```

---

Disk:

```bash
df -h
```

---

System Logs:

```bash
journalctl -xe
```

---

Mental Model:

```text
CPU
Memory
Disk
Network
```

---

# Chapter 5: CPU Problems

Symptoms:

```text
Slow Application
High Latency
Timeouts
```

---

Check:

```bash
top
```

---

or:

```bash
htop
```

---

Look For:

```text
100% CPU Usage
```

---

Find Process:

```bash
ps aux --sort=-%cpu
```

---

# Chapter 6: Memory Problems

Symptoms:

```text
Application Crashes
OOMKilled
Slow Performance
```

---

Check:

```bash
free -h
```

---

Top Memory Consumers:

```bash
ps aux --sort=-%mem
```

---

Kubernetes Example:

```bash
kubectl describe pod <pod>
```

---

Look For:

```text
OOMKilled
```

---

Interview Favorite:

```text
OOM
=
Out Of Memory
```

---

# Chapter 7: Disk Problems

Symptoms:

```text
Application Fails
Database Stops
Logs Not Written
```

---

Check:

```bash
df -h
```

---

Large Files:

```bash
du -sh *
```

---

Find Biggest:

```bash
du -ah / | sort -rh | head
```

---

Common Cause:

```text
Log Files
```

---

# Chapter 8: Network Issues

Cannot Reach Server?

---

Check:

```bash
ping server-ip
```

---

Routing:

```bash
ip route
```

---

Open Ports:

```bash
ss -tulpn
```

---

Connectivity:

```bash
telnet host port
```

or

```bash
nc -zv host port
```

---

# Chapter 9: DNS Issues

Symptoms:

```text
Website Not Reachable
API Failure
```

---

Check:

```bash
nslookup google.com
```

---

or:

```bash
dig google.com
```

---

Mental Model:

```text
DNS
 ↓
IP Address
 ↓
Connection
```

---

# Chapter 10: HTTP/HTTPS Issues

Check:

```bash
curl https://api.example.com
```

---

Common Errors:

```text
404
Not Found

500
Internal Error

502
Bad Gateway

503
Service Unavailable
```

---

Interview Favorite:

```text
502
Often Reverse Proxy Problem
```

---

# Chapter 11: Nginx Issues

Check Status:

```bash
systemctl status nginx
```

---

Configuration:

```bash
nginx -t
```

---

Logs:

```bash
tail -f /var/log/nginx/error.log
```

---

Architecture:

```text
User
 ↓
Nginx
 ↓
Application
```

---

Common Issue:

```text
Backend Down
```

causing:

```text
502 Bad Gateway
```

---

# Chapter 12: Docker Issues

Container Not Running?

---

Check:

```bash
docker ps -a
```

---

Logs:

```bash
docker logs container-id
```

---

Inspect:

```bash
docker inspect container-id
```

---

Resource Usage:

```bash
docker stats
```

---

Most Common Problems:

```text
Port Conflict
Environment Variables
Missing Volumes
```

---

# Chapter 13: Kubernetes Issues

Check Pods:

```bash
kubectl get pods
```

---

Describe:

```bash
kubectl describe pod pod-name
```

---

Logs:

```bash
kubectl logs pod-name
```

---

Events:

```bash
kubectl get events
```

---

Common States:

```text
CrashLoopBackOff

ImagePullBackOff

Pending

OOMKilled
```

---

Interview Favorite:

```text
First Command
=
kubectl describe pod
```

---

# Chapter 14: Database Issues

Cannot Connect?

---

Check:

```bash
telnet db-host 5432
```

---

Connections:

```sql
SELECT * FROM pg_stat_activity;
```

---

Replication:

```text
Replication Lag
```

---

Common Problems:

```text
Connection Limit
Slow Queries
Storage Full
```

---

# Chapter 15: AWS Issues

EC2 Not Reachable?

---

Check:

```text
Security Groups

NACLs

Route Tables

Instance Status
```

---

S3 Access Problem?

---

Check:

```text
IAM Permissions
Bucket Policy
```

---

EKS Issue?

---

Check:

```bash
kubectl get nodes
```

---

Mental Model:

```text
IAM
Networking
Resources
```

---

# Chapter 16: CI/CD Issues

Pipeline Failed?

---

Check:

```text
Build Logs
```

---

Common Causes:

```text
Wrong Environment Variables

Failed Tests

Authentication Problems

Docker Build Failure
```

---

GitHub Actions:

```text
Actions Tab
```

---

Jenkins:

```text
Build Console Output
```

---

# Chapter 17: Monitoring Issues

Alert Triggered?

---

Check:

```text
Metric

Threshold

Historical Trend
```

---

Questions:

```text
Real Issue?

False Alert?
```

---

Tools:

```text
Prometheus
Grafana
Datadog
```

---

# Chapter 18: Logs Investigation

Logs Tell Stories.

---

Application Logs:

```bash
tail -f app.log
```

---

System Logs:

```bash
journalctl -xe
```

---

Docker Logs:

```bash
docker logs container
```

---

Kubernetes Logs:

```bash
kubectl logs pod
```

---

Golden Rule:

```text
Logs First
Guessing Later
```

---

# Chapter 19: Root Cause Analysis

Don't stop at:

```text
Server Restarted
```

---

Ask:

```text
Why Did It Need Restart?
```

---

Example:

```text
Server Down
 ↓
Memory Full
 ↓
Memory Leak
 ↓
Application Bug
```

---

Root Cause:

```text
Application Bug
```

---

# Chapter 20: Production Checklist

When Production Is Down:

---

Step 1

```text
Check Monitoring
```

---

Step 2

```text
Check Logs
```

---

Step 3

```text
Check Infrastructure
```

---

Step 4

```text
Check Recent Deployments
```

---

Step 5

```text
Check Dependencies
```

---

Dependencies:

```text
Database
Cache
Message Queue
DNS
```

---

Step 6

```text
Implement Fix
```

---

Step 7

```text
Validate Recovery
```

---

# Chapter 21: Real Production Troubleshooting Flow

Website Down.

---

Flow:

```text
Website Down
 ↓
DNS?
 ↓
Load Balancer?
 ↓
Nginx?
 ↓
Application?
 ↓
Database?
```

---

API Slow.

---

Flow:

```text
API Slow
 ↓
CPU?
 ↓
Memory?
 ↓
Database?
 ↓
Network?
```

---

Pod Crash.

---

Flow:

```text
Pod Crash
 ↓
Describe Pod
 ↓
Logs
 ↓
Events
 ↓
Fix
```

---

Database Slow.

---

Flow:

```text
Slow Query?
 ↓
CPU?
 ↓
Storage?
 ↓
Replication?
```

---

# 🔥 Interview Questions

### First Thing To Do During Production Failure?

Gather evidence and understand the scope of the problem.

---

### First Question During Troubleshooting?

```text
What Changed?
```

---

### How To Investigate A Kubernetes Pod Failure?

```bash
kubectl describe pod
kubectl logs pod
kubectl get events
```

---

### How To Check Disk Usage?

```bash
df -h
```

---

### How To Check Memory Usage?

```bash
free -h
```

---

### How To Check CPU Usage?

```bash
top
```

---

### How To Investigate DNS Issues?

```bash
nslookup
dig
```

---

### How To Investigate Docker Container Issues?

```bash
docker logs
docker inspect
```

---

### What Is Root Cause Analysis?

Identifying the fundamental reason behind a failure.

---

### Why Are Logs Important?

Logs provide evidence and context about system behavior.

---

# Mental Model

```text
Problem
 ↓
Observe
 ↓
Collect Data
 ↓
Analyze
 ↓
Root Cause
 ↓
Fix
 ↓
Validate
```

---

# Universal Troubleshooting Framework

```text
Linux
 ↓
Networking
 ↓
Application
 ↓
Database
 ↓
Infrastructure
 ↓
Monitoring
```

---

# One-Line Summary

Production troubleshooting is the systematic process of identifying, analyzing, and resolving issues across Linux, networking, containers, Kubernetes, databases, cloud infrastructure, and applications using evidence-driven investigation and root cause analysis.
