# 🔭 25-Observability-Advanced.md

# Observability Advanced

## OpenTelemetry, Distributed Tracing, Jaeger, Zipkin, Datadog, Splunk, SLI, SLO & Error Budgets

> Monitoring tells you that something is wrong.
>
> Observability helps you understand why it is wrong.
>
> Modern distributed systems contain:
>
> * Microservices
> * Containers
> * Kubernetes
> * Cloud Services
> * Databases
>
> Traditional monitoring is no longer enough.
>
> Observability is how modern engineering teams troubleshoot production systems.

---

# 📚 Table of Contents

1. Monitoring vs Observability
2. The Three Pillars of Observability
3. Metrics
4. Logs
5. Traces
6. Distributed Systems Problem
7. Distributed Tracing
8. OpenTelemetry
9. Jaeger
10. Zipkin
11. Prometheus
12. Grafana
13. Datadog
14. Splunk
15. New Relic
16. SLI
17. SLO
18. SLA
19. Error Budgets
20. Alerting
21. PagerDuty
22. Production Architecture
23. Interview Questions

---

# Chapter 1: Monitoring vs Observability

## Monitoring

Answers:

```text
What Happened?
```

---

Example:

```text
CPU = 95%
```

---

## Observability

Answers:

```text
Why Did It Happen?
```

---

Example:

```text
Which Service?

Which Database Query?

Which API Request?
```

---

Easy Memory:

```text
Monitoring
    =
What Broke?

Observability
    =
Why Did It Break?
```

---

# Chapter 2: The Three Pillars Of Observability

Modern observability consists of:

```text
Metrics
Logs
Traces
```

---

Architecture:

```text
Application
     ↓
Metrics

Logs

Traces
```

---

Interview Favorite:

```text
Metrics + Logs + Traces
     =
Observability
```

---

# Chapter 3: Metrics

Metrics are numerical values.

---

Examples:

```text
CPU Usage
Memory Usage
Request Count
Latency
Error Rate
```

---

Example:

```text
CPU = 85%

Memory = 70%
```

---

Benefits:

```text
Fast
Aggregated
Easy To Alert On
```

---

# Chapter 4: Logs

Logs are event records.

---

Example:

```text
User Login Success

Database Connection Failed

Order Created
```

---

Application Log:

```text
2025-01-01
User Logged In
```

---

Purpose:

```text
Detailed Troubleshooting
```

---

# Chapter 5: Traces

Traces track requests.

---

Example:

```text
User Request
     ↓
API
     ↓
Service A
     ↓
Service B
     ↓
Database
```

---

Trace shows:

```text
Entire Request Journey
```

---

# Chapter 6: Distributed Systems Problem

Monolith:

```text
Application
```

---

Easy to troubleshoot.

---

Microservices:

```text
Frontend
 ↓
API
 ↓
Auth Service
 ↓
Payment Service
 ↓
Database
```

---

Problem:

```text
Where Did Request Fail?
```

---

# Chapter 7: Distributed Tracing

Distributed Tracing tracks requests across services.

---

Architecture:

```text
Request
 ↓
Service A
 ↓
Service B
 ↓
Service C
```

---

Shows:

```text
Latency
Errors
Dependencies
```

---

Benefits:

```text
Root Cause Analysis
```

---

# Chapter 8: OpenTelemetry

OpenTelemetry:

```text
Open Source Observability Standard
```

---

Purpose:

```text
Collect Metrics
Collect Logs
Collect Traces
```

---

Think:

```text
OpenTelemetry
      =
Observability SDK
```

---

Architecture:

```text
Application
 ↓
OpenTelemetry
 ↓
Observability Platform
```

---

Interview Favorite:

```text
OpenTelemetry
    =
Industry Standard
For Telemetry Data
```

---

# Chapter 9: Jaeger

Jaeger:

```text
Distributed Tracing Platform
```

---

Purpose:

```text
Visualize Traces
```

---

Architecture:

```text
Application
 ↓
OpenTelemetry
 ↓
Jaeger
```

---

Benefits:

```text
Trace Analysis
Performance Optimization
```

---

# Chapter 10: Zipkin

Zipkin:

```text
Distributed Tracing Tool
```

---

Similar To:

```text
Jaeger
```

---

Use Cases:

```text
Latency Analysis
Dependency Mapping
```

---

# Chapter 11: Prometheus

Prometheus:

```text
Metrics Collection System
```

---

Collects:

```text
CPU
Memory
Requests
Errors
```

---

Architecture:

```text
Application
 ↓
Prometheus
 ↓
Metrics Storage
```

---

Query Language:

```text
PromQL
```

---

Interview Favorite:

```text
Prometheus
     =
Metrics
```

---

# Chapter 12: Grafana

Grafana:

```text
Visualization Platform
```

---

Purpose:

```text
Dashboards
Charts
Alerts
```

---

Architecture:

```text
Prometheus
 ↓
Grafana
 ↓
Dashboard
```

---

Interview Favorite:

```text
Grafana
     =
Visualization
```

---

# Chapter 13: Datadog

Datadog:

```text
Commercial Observability Platform
```

---

Provides:

```text
Metrics
Logs
Traces
Security Monitoring
```

---

Benefits:

```text
Single Platform
Cloud Native
```

---

# Chapter 14: Splunk

Splunk:

```text
Log Analytics Platform
```

---

Purpose:

```text
Search Logs
Analyze Logs
Visualize Logs
```

---

Common Use Cases:

```text
Security
Operations
Compliance
```

---

# Chapter 15: New Relic

New Relic:

```text
Application Performance Monitoring
```

---

Focus:

```text
Performance
User Experience
Observability
```

---

Tracks:

```text
Applications
Databases
Infrastructure
```

---

# Chapter 16: SLI

SLI:

```text
Service Level Indicator
```

---

Measures:

```text
Availability
Latency
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
Measurement
```

---

# Chapter 17: SLO

SLO:

```text
Service Level Objective
```

---

Target Value.

---

Example:

```text
99.9% Availability
```

---

Think:

```text
SLO
    =
Goal
```

---

# Chapter 18: SLA

SLA:

```text
Service Level Agreement
```

---

Customer-facing commitment.

---

Example:

```text
99.9% Uptime Guaranteed
```

---

Think:

```text
SLA
    =
Contract
```

---

Easy Memory:

```text
SLI
   =
Measurement

SLO
   =
Target

SLA
   =
Promise
```

---

# Chapter 19: Error Budgets

Example:

```text
99.9% Availability
```

---

Allows:

```text
0.1% Failure
```

---

This acceptable failure amount is:

```text
Error Budget
```

---

Purpose:

```text
Balance Reliability
And Innovation
```

---

Interview Favorite:

```text
Error Budget
     =
Allowed Downtime
```

---

# Chapter 20: Alerting

Monitoring without alerts is useless.

---

Examples:

```text
CPU > 90%

Memory > 95%

Error Rate High
```

---

Alert Flow:

```text
Prometheus
 ↓
AlertManager
 ↓
PagerDuty
```

---

# Chapter 21: PagerDuty

PagerDuty:

```text
Incident Management Platform
```

---

Purpose:

```text
Notify Engineers
```

during incidents.

---

Flow:

```text
Monitoring
 ↓
Alert
 ↓
PagerDuty
 ↓
Engineer
```

---

Common Usage:

```text
24x7 On-Call Support
```

---

# Chapter 22: Production Architecture

Modern Observability Stack:

```text
Application
 ↓
OpenTelemetry
 ↓
Prometheus
 ↓
Grafana
```

---

Enterprise Stack:

```text
Application
 ↓
OpenTelemetry
 ↓
Datadog
```

---

Distributed Tracing:

```text
Application
 ↓
OpenTelemetry
 ↓
Jaeger
```

---

Cloud Native Stack:

```text
Kubernetes
 ↓
Prometheus
 ↓
Grafana
 ↓
AlertManager
 ↓
PagerDuty
```

---

# Chapter 23: Why Observability Matters

Modern systems are:

```text
Distributed
Containerized
Cloud Native
```

---

Observability helps:

```text
Detect Issues
Diagnose Issues
Resolve Issues
Prevent Issues
```

---

# 🔥 Interview Questions

### What Is Observability?

The ability to understand the internal state of a system using metrics, logs, and traces.

---

### Monitoring vs Observability?

Monitoring tells you what happened.

Observability helps explain why it happened.

---

### What Are The Three Pillars Of Observability?

```text
Metrics
Logs
Traces
```

---

### What Is Distributed Tracing?

Tracking a request across multiple services.

---

### What Is OpenTelemetry?

An open-source standard for collecting telemetry data.

---

### What Is Jaeger?

A distributed tracing platform.

---

### What Is Zipkin?

A distributed tracing tool used to analyze request flows.

---

### What Is Prometheus?

An open-source metrics collection and monitoring system.

---

### What Is Grafana?

A dashboard and visualization platform.

---

### What Is Datadog?

A commercial observability platform providing metrics, logs, traces, and monitoring.

---

### What Is Splunk?

A platform used for log analytics and operational intelligence.

---

### Difference Between SLI, SLO, And SLA?

```text
SLI = Measurement

SLO = Goal

SLA = Contract
```

---

### What Is An Error Budget?

The amount of acceptable failure within an SLO target.

---

### What Is PagerDuty?

An incident response and on-call alerting platform.

---

# Mental Model

```text
Application
 ↓
Metrics
Logs
Traces
 ↓
Observability Platform
 ↓
Alerts
 ↓
Engineers
```

---

# Modern Observability Stack

```text
OpenTelemetry
      ↓
Collect Data

Prometheus
      ↓
Store Metrics

Grafana
      ↓
Visualize

AlertManager
      ↓
Alert

PagerDuty
      ↓
Notify Engineers
```

---

# One-Line Summary

Observability is the practice of understanding and troubleshooting distributed systems using metrics, logs, traces, telemetry, alerting, and reliability engineering concepts such as SLI, SLO, SLA, and error budgets.
