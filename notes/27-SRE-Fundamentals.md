# 🚨 27-SRE-Fundamentals.md

# Site Reliability Engineering (SRE) Fundamentals

## Reliability, Availability, Incidents, On-Call, Runbooks, Postmortems & Production Operations

> DevOps focuses on delivering software faster.
>
> SRE focuses on keeping software reliable.
>
> Modern companies such as Google, Netflix, Amazon, Meta, and Microsoft use SRE practices to ensure:
>
> * High Availability
> * Reliability
> * Scalability
> * Fast Incident Response
>
> SRE combines:
>
> ```text
> Software Engineering
> +
> Operations
> +
> Reliability
> ```

---

# 📚 Table of Contents

1. What Is SRE?
2. DevOps vs SRE
3. Reliability
4. Availability
5. Service Level Indicators (SLI)
6. Service Level Objectives (SLO)
7. Service Level Agreements (SLA)
8. Error Budgets
9. Incident Management
10. Incident Severity Levels
11. On-Call Engineering
12. Alert Fatigue
13. Runbooks
14. Playbooks
15. Postmortems
16. Blameless Culture
17. Capacity Planning
18. Disaster Recovery
19. Chaos Engineering
20. Production Operations
21. Real Production Architecture
22. Interview Questions

---

# Chapter 1: What Is SRE?

SRE stands for:

```text
Site Reliability Engineering
```

---

Created by:

Google

---

Definition:

```text
Applying Software Engineering
To Operations Problems
```

---

Goal:

```text
Keep Systems Reliable
```

---

# Chapter 2: DevOps vs SRE

## DevOps

Focus:

```text
Speed
Automation
Delivery
```

---

## SRE

Focus:

```text
Reliability
Availability
Operations
```

---

Comparison:

| DevOps          | SRE                     |
| --------------- | ----------------------- |
| Faster Delivery | Reliable Delivery       |
| Automation      | Reliability Engineering |
| CI/CD           | SLI/SLO/SLA             |
| Deployment      | Operations              |

---

Easy Memory:

```text
DevOps
    =
Move Faster

SRE
    =
Stay Reliable
```

---

# Chapter 3: Reliability

Reliability means:

```text
System Works Correctly
Over Time
```

---

Example:

```text
Payment Service
Processes Payments
Correctly
```

---

Not just availability.

---

Reliable System:

```text
Correct Results
Consistent Behavior
```

---

# Chapter 4: Availability

Availability means:

```text
System Is Accessible
```

---

Example:

```text
99.99% Uptime
```

---

Common Targets:

| Availability | Downtime Per Year |
| ------------ | ----------------- |
| 99%          | ~3.65 Days        |
| 99.9%        | ~8.7 Hours        |
| 99.99%       | ~52 Minutes       |
| 99.999%      | ~5 Minutes        |

---

Interview Favorite:

```text
Five Nines
=
99.999%
```

---

# Chapter 5: Service Level Indicator (SLI)

SLI:

```text
Measurement
```

---

Examples:

```text
Latency
Availability
Error Rate
```

---

Example:

```text
99.95% Availability
```

---

Think:

```text
SLI
=
Metric
```

---

# Chapter 6: Service Level Objective (SLO)

SLO:

```text
Target
```

---

Example:

```text
99.9% Availability
```

---

Think:

```text
SLI
=
Actual Value

SLO
=
Target Value
```

---

# Chapter 7: Service Level Agreement (SLA)

SLA:

```text
Business Commitment
```

---

Example:

```text
99.9% Uptime Guarantee
```

---

If violated:

```text
Compensation
Refund
Penalty
```

---

Easy Memory:

```text
SLI
=
Measurement

SLO
=
Goal

SLA
=
Contract
```

---

# Chapter 8: Error Budgets

Example:

```text
SLO = 99.9%
```

---

Allowed Failure:

```text
0.1%
```

---

This is:

```text
Error Budget
```

---

Purpose:

```text
Balance Innovation
And Reliability
```

---

# Chapter 9: Incident Management

Incident:

```text
Production Problem
```

---

Examples:

```text
Website Down
Database Failure
Payment Failure
```

---

Incident Flow:

```text
Monitoring
 ↓
Alert
 ↓
Investigation
 ↓
Resolution
```

---

# Chapter 10: Incident Severity Levels

Common Classification:

---

## SEV-1

```text
Entire System Down
```

---

## SEV-2

```text
Major Functionality Impacted
```

---

## SEV-3

```text
Minor Issue
```

---

## SEV-4

```text
Cosmetic Issue
```

---

# Chapter 11: On-Call Engineering

Engineers available for incidents.

---

Example:

```text
2 AM
Production Failure
 ↓
On-Call Engineer
```

---

Responsibilities:

```text
Investigate
Mitigate
Restore Service
```

---

# Chapter 12: Alert Fatigue

Problem:

```text
Too Many Alerts
```

---

Example:

```text
100 Alerts
Only 2 Important
```

---

Result:

```text
Engineers Ignore Alerts
```

---

Solution:

```text
Meaningful Alerts
```

---

# Chapter 13: Runbooks

Runbook:

```text
Step-By-Step Guide
```

for resolving issues.

---

Example:

```text
Database Down
 ↓
Restart Service
 ↓
Verify Connection
 ↓
Check Logs
```

---

Benefits:

```text
Faster Recovery
```

---

# Chapter 14: Playbooks

Playbook:

```text
Decision Framework
```

---

Runbook:

```text
How To Fix
```

---

Playbook:

```text
How To Respond
```

---

# Chapter 15: Postmortems

After incident:

```text
Analyze Failure
```

---

Questions:

```text
What Happened?

Why?

How To Prevent?
```

---

Output:

```text
Action Items
```

---

# Chapter 16: Blameless Culture

Never ask:

```text
Who Broke It?
```

---

Ask:

```text
Why Did System Allow It?
```

---

Focus:

```text
Process Improvement
```

---

This is:

```text
Blameless Postmortem
```

---

# Chapter 17: Capacity Planning

Purpose:

```text
Prepare For Growth
```

---

Example:

```text
100K Users Today

1M Users Next Year
```

---

Need:

```text
More Servers
More Storage
More Databases
```

---

# Chapter 18: Disaster Recovery

Disaster:

```text
Region Failure
Cloud Outage
Data Loss
```

---

Need:

```text
Recovery Plan
```

---

Important Metrics:

## RPO

```text
Maximum Data Loss
```

---

## RTO

```text
Maximum Recovery Time
```

---

# Chapter 19: Chaos Engineering

Idea:

```text
Break Things
On Purpose
```

---

Goal:

```text
Discover Weaknesses
```

---

Example:

```text
Shutdown Server
Observe System
```

---

Popular Example:

Netflix

created Chaos Monkey.

---

# Chapter 20: Production Operations

Daily SRE Activities:

```text
Monitoring
Alerting
Capacity Planning
Incident Response
Automation
Performance Tuning
```

---

Tools:

```text
Prometheus
Grafana
PagerDuty
Kubernetes
AWS
```

---

# Chapter 21: Real Production Architecture

Modern SRE Stack:

```text
Users
 ↓
CloudFront
 ↓
Load Balancer
 ↓
Kubernetes
 ↓
Microservices
 ↓
Databases
```

---

Observability Layer:

```text
Prometheus
 ↓
Grafana
 ↓
PagerDuty
```

---

Reliability Layer:

```text
SLIs
SLOs
Error Budgets
```

---

# Chapter 22: Why SRE Matters

Without SRE:

```text
Frequent Outages
Poor Reliability
Slow Recovery
```

---

With SRE:

```text
Reliable Systems
Fast Recovery
Better User Experience
```

---

# 🔥 Interview Questions

### What Is SRE?

Site Reliability Engineering is the practice of applying software engineering principles to operations and reliability problems.

---

### DevOps vs SRE?

DevOps focuses on delivery and automation.

SRE focuses on reliability and operations.

---

### What Is Reliability?

The ability of a system to perform correctly over time.

---

### What Is Availability?

The percentage of time a system is accessible.

---

### What Is SLI?

A metric that measures service performance.

---

### What Is SLO?

A target value for an SLI.

---

### What Is SLA?

A contractual commitment to customers.

---

### What Is An Error Budget?

The acceptable amount of failure within an SLO target.

---

### What Is A Runbook?

A documented procedure for resolving operational issues.

---

### What Is A Postmortem?

An analysis conducted after an incident to identify root causes and improvements.

---

### What Is RPO?

Maximum acceptable data loss.

---

### What Is RTO?

Maximum acceptable recovery time.

---

### What Is Chaos Engineering?

Testing system resilience by intentionally introducing failures.

---

### What Is Alert Fatigue?

A condition where excessive alerts reduce the effectiveness of incident response.

---

# Mental Model

```text
Build System
 ↓
Monitor
 ↓
Alert
 ↓
Respond
 ↓
Recover
 ↓
Improve
```

---

# SRE Lifecycle

```text
SLI
 ↓
SLO
 ↓
Monitoring
 ↓
Alerting
 ↓
Incident
 ↓
Runbook
 ↓
Resolution
 ↓
Postmortem
 ↓
Improvement
```

---

# One-Line Summary

Site Reliability Engineering (SRE) is the discipline of ensuring that systems remain reliable, available, scalable, and recoverable through monitoring, automation, incident management, error budgets, and continuous operational improvement.
