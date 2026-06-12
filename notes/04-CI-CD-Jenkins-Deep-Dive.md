# 🚀 04-CI-CD-Jenkins-Deep-Dive.md

# CI/CD & Jenkins Deep Dive

## Understanding What Happens After Git Push

> Git manages code.
>
> GitHub stores code.
>
> Webhooks notify Jenkins.
>
> Jenkins automates everything that happens next.

---

# 📚 Table of Contents

1. Why CI/CD Exists
2. The Problem Before CI/CD
3. What Is CI?
4. What Is CD?
5. CI vs CD
6. What Is Jenkins?
7. Jenkins Architecture
8. Controller vs Agent
9. What Happens After Webhook?
10. Pipeline Deep Dive
11. Pipeline Stages
12. Build Stage
13. Testing Stage
14. Static Analysis Stage
15. Artifact Creation
16. Artifact Repositories
17. Deployment Stage
18. Jenkinsfile Explained
19. Complete Industry Workflow
20. Interview Questions

---

# Chapter 1: Why CI/CD Exists

Imagine 100 developers.

Every day:

```text
Developer A → Pushes Code
Developer B → Pushes Code
Developer C → Pushes Code
```

Question:

Who will verify:

```text
Code Compiles?
Tests Pass?
Application Works?
```

Manual verification is impossible.

Need automation.

---

# Before CI/CD

Workflow:

```text
Developer Writes Code
        ↓
Developer Emails Team
        ↓
Build Engineer Builds
        ↓
Tester Tests
        ↓
Operations Deploys
```

Problems:

```text
Slow
Manual
Error-Prone
Expensive
```

---

# Goal Of CI/CD

```text
Automate Everything
```

---

# Chapter 2: What Is CI?

CI = Continuous Integration

---

## Definition

Continuous Integration means:

```text
Every Code Change
        ↓
Automatically Verified
```

---

Example:

Developer pushes:

```bash
git push
```

Immediately:

```text
Build Starts
Tests Run
Checks Execute
Reports Generated
```

Without human intervention.

---

# CI Pipeline

```text
Code Push
    ↓
Build
    ↓
Unit Tests
    ↓
Code Quality Checks
    ↓
Artifact Creation
```

Goal:

```text
Detect Problems Early
```

---

# Chapter 3: What Is CD?

CD = Continuous Delivery

or

CD = Continuous Deployment

Depending on company.

---

# Continuous Delivery

Pipeline:

```text
Build
 ↓
Test
 ↓
Artifact Ready
 ↓
Manual Approval
 ↓
Deploy
```

Human approves deployment.

---

# Continuous Deployment

Pipeline:

```text
Build
 ↓
Test
 ↓
Deploy Automatically
```

No human approval.

---

# Difference

## Continuous Integration

Answers:

```text
Is Code Good?
```

---

## Continuous Delivery

Answers:

```text
Can Software Be Released?
```

---

## Continuous Deployment

Answers:

```text
Release Immediately
```

---

# Chapter 4: What Is Jenkins?

Most people say:

```text
Jenkins is a CI/CD Tool
```

Technically correct.

But incomplete.

---

# Better Definition

Jenkins is:

```text
An Automation Server
```

Think:

```text
Robot Employee
```

Whenever an event occurs:

```text
New Commit
New Release
Scheduled Job
Manual Trigger
```

Jenkins performs tasks automatically.

---

# Real Example

Developer pushes code.

```text
GitHub
   ↓
Webhook
   ↓
Jenkins
```

Jenkins says:

```text
Let me verify everything.
```

---

# Chapter 5: Jenkins Architecture

Many beginners think:

```text
Jenkins
```

is one machine.

Large companies don't work like that.

---

Architecture:

```text
                Jenkins Controller
                       |
      ------------------------------------
      |                |                 |
      |                |                 |
      v                v                 v

 Linux Agent     Windows Agent     Test Agent
```

---

# Controller

Brain of Jenkins.

Responsibilities:

```text
Manage Jobs
Manage Users
Schedule Builds
Store Configurations
```

Controller rarely performs heavy work.

---

# Agent

Workers.

Responsibilities:

```text
Compile Code
Run Tests
Create Artifacts
Deploy Applications
```

---

# Real Example

Imagine:

```text
Android Build
Linux Build
Windows Build
```

Different agents execute different tasks.

---

# Chapter 6: What Happens After Webhook?

Let's follow the complete journey.

Developer:

```bash
git push
```

---

GitHub:

```text
Receives Commit
```

---

GitHub:

```text
Sends Webhook
```

---

Jenkins:

```text
Receives Webhook
```

---

Jenkins:

```text
Starts Pipeline
```

Pipeline begins.

---

# Visual Flow

```text
Developer
    ↓
git push
    ↓
GitHub
    ↓
Webhook
    ↓
Jenkins
    ↓
Pipeline
```

---

# Chapter 7: What Is A Pipeline?

Definition:

```text
Pipeline = Automated Workflow
```

---

Example:

```text
Build
 ↓
Test
 ↓
Scan
 ↓
Package
 ↓
Deploy
```

Each step is called:

```text
Stage
```

---

# Pipeline Visualization

```text
Stage 1 → Build
Stage 2 → Test
Stage 3 → Scan
Stage 4 → Package
Stage 5 → Deploy
```

---

# Chapter 8: Build Stage

Question:

Why build?

---

Source code:

```c
printf("Hello");
```

CPU cannot understand C.

Need translation.

---

Build Process:

```text
Source Code
     ↓
Compiler
     ↓
Machine Code
```

---

Examples

Java:

```text
.java
   ↓
.jar
```

---

C/C++:

```text
.c
 ↓
.exe
```

---

Embedded:

```text
.c
 ↓
.elf
```

---

If build fails:

```text
Pipeline Stops
```

---

# Chapter 9: Testing Stage

Code compiles.

Doesn't mean code works.

---

Example:

```python
def add(a,b):
    return a-b
```

Build:

```text
PASS
```

Logic:

```text
WRONG
```

---

Need tests.

---

Unit Test:

```python
assert add(2,3)==5
```

---

Results:

```text
Pass
Fail
```

---

If test fails:

```text
Pipeline Stops
```

---

# Chapter 10: Static Code Analysis

Question:

Can we detect problems without executing code?

Yes.

---

Tools:

* SonarQube
* Checkstyle
* PMD
* Cppcheck

---

Example:

```c
int *ptr = NULL;
*ptr = 10;
```

Possible crash.

Tool detects issue.

---

Benefits:

```text
Code Quality
Security
Maintainability
Reliability
```

---

# Chapter 11: Artifact Creation

After successful build:

Need output.

---

Artifact = Build Result

Examples:

```text
.jar
.war
.exe
.dll
.elf
Docker Image
```

---

Artifact is what gets deployed.

Not source code.

---

# Chapter 12: Artifact Repository

Question:

Where do artifacts live?

Need storage.

---

Popular Repositories:

* Nexus
* Artifactory
* Docker Registry

---

Flow:

```text
Build
 ↓
Artifact
 ↓
Repository
```

---

Benefits:

```text
Versioning
Storage
Distribution
Rollback
```

---

# Chapter 13: Deployment Stage

Software verified.

Now release it.

---

Deployment means:

```text
Move Application
To Target Environment
```

---

Environments:

```text
Development
Testing
Staging
Production
```

---

Typical Flow:

```text
Dev
 ↓
QA
 ↓
Staging
 ↓
Production
```

---

# Chapter 14: Jenkinsfile

Question:

How does Jenkins know what to do?

Answer:

```text
Jenkinsfile
```

---

Think:

```text
Instruction Manual
For Jenkins
```

---

Example:

```groovy
pipeline {

  agent any

  stages {

    stage('Build') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Deploy') {
      steps {
        sh './deploy.sh'
      }
    }

  }

}
```

---

Meaning:

```text
Build
 ↓
Test
 ↓
Deploy
```

---

# Chapter 15: Complete Industry Pipeline

```text
Developer
      ↓
git push
      ↓
GitHub
      ↓
Webhook
      ↓
Jenkins
      ↓
Checkout Code
      ↓
Build
      ↓
Unit Tests
      ↓
Static Analysis
      ↓
Artifact Creation
      ↓
Artifact Repository
      ↓
Deploy
      ↓
Environment
```

---

# Chapter 16: Real Enterprise Pipeline

```text
Developer
     ↓
GitHub
     ↓
Webhook
     ↓
Jenkins
     ↓
Maven Build
     ↓
JUnit Tests
     ↓
SonarQube Scan
     ↓
Docker Build
     ↓
Docker Registry
     ↓
Deploy To Kubernetes
     ↓
AWS
     ↓
Users
```

This is very close to how modern software companies operate.

---

# Mental Model

Think of Jenkins as:

```text
Factory Manager
```

Think of Pipeline as:

```text
Assembly Line
```

Think of Stages as:

```text
Factory Stations
```

Think of Artifacts as:

```text
Finished Products
```

---

# 🔥 Interview Questions

### What Is CI?

Continuous Integration automatically verifies code changes through build and testing.

---

### What Is CD?

Continuous Delivery or Deployment automates software release.

---

### What Is Jenkins?

An automation server used to build, test, package, and deploy software.

---

### Difference Between Controller And Agent?

Controller manages jobs and scheduling.

Agents execute actual tasks.

---

### What Is A Pipeline?

A sequence of automated stages executed by Jenkins.

---

### What Is A Jenkinsfile?

A file that defines pipeline stages and execution logic.

---

### What Is An Artifact?

The deployable output generated from a build process.

---

### Why Use Artifact Repositories?

To store, version, distribute, and rollback build outputs.
