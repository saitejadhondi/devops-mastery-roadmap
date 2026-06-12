# 🔥 13-DevOps-Interview-Questions-and-Answers-Part3.md

# DevOps Interview Questions & Answers (101-150)

## Scenario-Based, Troubleshooting, Production & Real-World Questions

---

# Production Troubleshooting

### 101. A website is suddenly slow. What would you check first?

I would start with:

```text
CPU Usage
Memory Usage
Disk Usage
Network Utilization
Application Logs
Database Performance
```

Tools:

```text
top
htop
free -m
df -h
Prometheus
Grafana
CloudWatch
```

---

### 102. A Jenkins pipeline suddenly fails. How would you troubleshoot?

Check:

```text
Jenkins Console Output
Build Logs
Agent Status
Network Connectivity
Credentials
Recent Code Changes
```

Then identify the stage where the failure occurred.

---

### 103. A Docker container keeps restarting. What would you do?

Commands:

```bash
docker ps
docker logs <container-id>
docker inspect <container-id>
```

Check:

```text
Application Errors
Missing Environment Variables
Port Conflicts
Memory Issues
```

---

### 104. A Kubernetes Pod is in CrashLoopBackOff. What does it mean?

The container starts, crashes, and Kubernetes repeatedly tries to restart it.

Check:

```bash
kubectl logs pod-name
kubectl describe pod pod-name
```

---

### 105. How do you investigate a pod that is not starting?

Commands:

```bash
kubectl describe pod pod-name
kubectl logs pod-name
kubectl get events
```

Check:

```text
Image Pull Errors
Resource Limits
Missing ConfigMaps
Missing Secrets
```

---

### 106. A service is down but pods are running. What would you check?

Check:

```text
Service Configuration
Endpoints
Ingress Rules
Network Policies
Application Health
```

Commands:

```bash
kubectl get svc
kubectl get endpoints
```

---

### 107. How do you troubleshoot high CPU usage?

Check:

```bash
top
htop
ps -ef
```

Identify:

```text
CPU-intensive Process
Application Loops
Traffic Spikes
```

---

### 108. How do you troubleshoot high memory usage?

Check:

```bash
free -m
top
ps aux --sort=-%mem
```

Look for:

```text
Memory Leaks
Large Processes
Cache Growth
```

---

### 109. What would you do if disk space becomes full?

Check:

```bash
df -h
du -sh *
```

Actions:

```text
Delete Old Logs
Clean Temporary Files
Increase Storage
```

---

### 110. How would you investigate a database performance issue?

Check:

```text
Slow Queries
Connection Counts
CPU Usage
Disk I/O
Indexes
```

---

# Kubernetes Scenarios

### 111. Why use Kubernetes instead of Docker alone?

Docker creates containers.

Kubernetes manages:

```text
Scaling
Networking
Self-Healing
Rolling Updates
```

for large numbers of containers.

---

### 112. What happens when a Pod crashes?

Kubernetes detects failure and creates a replacement Pod automatically.

---

### 113. What is self-healing?

The ability of Kubernetes to automatically recover failed workloads.

---

### 114. What is horizontal scaling?

Adding more application instances.

Example:

```text
3 Pods
 ↓
10 Pods
```

---

### 115. What is vertical scaling?

Increasing resources of existing instances.

Example:

```text
2 CPU
 ↓
8 CPU
```

---

### 116. What is a rolling update?

Gradually replacing old Pods with new Pods without downtime.

---

### 117. How does Kubernetes provide high availability?

Using:

```text
Multiple Nodes
ReplicaSets
Deployments
Services
```

---

### 118. Difference between Deployment and StatefulSet?

Deployment:

```text
Stateless Applications
```

StatefulSet:

```text
Databases
Persistent Identity
```

---

### 119. What is a readiness probe?

Determines whether a Pod is ready to receive traffic.

---

### 120. What is a liveness probe?

Determines whether a Pod is healthy and should continue running.

---

# AWS Scenarios

### 121. What happens if an EC2 instance fails?

Traffic is redirected to healthy instances through a Load Balancer and Auto Scaling Group launches a replacement.

---

### 122. Why use multiple Availability Zones?

To improve fault tolerance and availability.

---

### 123. What is High Availability?

Designing systems to remain operational despite failures.

---

### 124. What is Disaster Recovery?

The process of restoring services after major failures.

---

### 125. Difference between High Availability and Disaster Recovery?

High Availability:

```text
Prevent Downtime
```

Disaster Recovery:

```text
Recover From Downtime
```

---

### 126. How would you secure AWS resources?

Using:

```text
IAM
Security Groups
Encryption
MFA
Least Privilege Access
```

---

### 127. Why use IAM Roles instead of Access Keys?

Roles provide temporary credentials and are more secure.

---

### 128. What is the principle of least privilege?

Grant only the permissions necessary to perform a task.

---

### 129. What is an Auto Scaling Group?

A service that automatically adds or removes EC2 instances based on demand.

---

### 130. What is a Load Balancer?

A service that distributes traffic across multiple instances.

---

# Monitoring & Observability

### 131. Difference between Monitoring and Observability?

Monitoring detects known issues.

Observability helps investigate unknown issues.

---

### 132. What are the three pillars of observability?

```text
Metrics
Logs
Traces
```

---

### 133. What is Prometheus?

An open-source metrics collection system.

---

### 134. What is Grafana?

A dashboard and visualization platform.

---

### 135. What is AlertManager?

A tool that sends alerts when monitoring rules are triggered.

---

### 136. What is centralized logging?

Collecting logs from multiple systems into one location.

---

### 137. What is ELK Stack?

```text
Elasticsearch
Logstash
Kibana
```

Used for centralized logging.

---

### 138. Why are logs important?

Logs help identify application and infrastructure issues.

---

### 139. What are traces?

Records showing how requests move through distributed systems.

---

### 140. Why is observability important for microservices?

Because requests travel through multiple services and tracing helps identify bottlenecks.

---

# System Design & DevOps Thinking

### 141. Explain an end-to-end CI/CD pipeline.

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
Docker
 ↓
Registry
 ↓
Kubernetes
 ↓
Production
```

---

### 142. What is Infrastructure as Code?

Managing infrastructure using code instead of manual processes.

---

### 143. Why is Terraform important?

Provides:

```text
Automation
Version Control
Consistency
Repeatability
```

---

### 144. How would you deploy a highly available web application?

Use:

```text
Multiple AZs
Load Balancer
Auto Scaling
Kubernetes
Monitoring
```

---

### 145. What is Blue-Green Deployment?

Two environments:

```text
Blue = Current

Green = New Version
```

Traffic switches after validation.

---

### 146. What is Canary Deployment?

Releasing a new version to a small percentage of users first.

---

### 147. What is Rollback?

Reverting to a previous stable version when a deployment fails.

---

### 148. What are the most important DevOps principles?

```text
Automation
Collaboration
Continuous Improvement
Monitoring
Reliability
```

---

### 149. What would your ideal DevOps toolchain look like?

```text
GitHub
 ↓
Jenkins
 ↓
Docker
 ↓
Terraform
 ↓
AWS
 ↓
Kubernetes
 ↓
Prometheus
 ↓
Grafana
```

---

### 150. Explain DevOps in one minute.

DevOps is a culture and engineering practice that combines development, operations, automation, cloud infrastructure, CI/CD, monitoring, and collaboration to deliver software faster, more reliably, and with higher quality.

---

# Ultimate Interview Summary

```text
GitHub      → Code Storage

Webhook     → Notification

Jenkins     → Automation

Docker      → Containerization

Kubernetes  → Orchestration

Terraform   → Infrastructure as Code

AWS         → Cloud Infrastructure

EC2         → Virtual Machine

S3          → Object Storage

RDS         → Managed Database

Load Balancer → Traffic Distribution

Prometheus  → Metrics

Grafana     → Dashboards

ELK         → Logging

Monitoring  → Detect Problems

Observability → Understand Problems

DevOps      → Automate Software Delivery
```

---

# Golden Interview Answer

If an interviewer asks:

"Explain how modern applications are delivered."

Answer:

```text
A developer pushes code to GitHub. A webhook triggers Jenkins, which builds, tests, and packages the application into a Docker image. The image is stored in a registry and deployed to Kubernetes running on AWS infrastructure provisioned through Terraform. Monitoring tools such as Prometheus and Grafana observe the application and alert engineers when issues occur. This automated workflow enables reliable and scalable software delivery.
```
