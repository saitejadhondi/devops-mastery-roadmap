# 🔥 11-DevOps-Interview-Questions-and-Answers-Part1.md

# DevOps Interview Questions & Answers (1-50)

---

# DevOps Fundamentals

### 1. What is DevOps?

DevOps is a culture, set of practices, and automation approach that combines Development and Operations teams to deliver software faster and more reliably.

---

### 2. Why was DevOps introduced?

To solve problems caused by siloed Development and Operations teams such as slow releases, manual deployments, and poor collaboration.

---

### 3. What are the main goals of DevOps?

* Faster delivery
* Automation
* Reliability
* Scalability
* Continuous improvement

---

### 4. What is the Software Development Lifecycle (SDLC)?

The process of planning, developing, testing, deploying, and maintaining software.

---

### 5. What is CI/CD?

CI/CD stands for Continuous Integration and Continuous Delivery/Deployment.

---

### 6. What is Continuous Integration?

Automatically building and testing code whenever developers commit changes.

---

### 7. What is Continuous Delivery?

Ensuring software is always deployable but requiring manual approval before production deployment.

---

### 8. What is Continuous Deployment?

Automatically deploying software to production without manual approval.

---

### 9. Difference between Continuous Delivery and Continuous Deployment?

Delivery requires approval.

Deployment is fully automated.

---

### 10. What are the benefits of DevOps?

* Faster releases
* Better collaboration
* Reduced failures
* Increased automation
* Improved monitoring

---

# Git & GitHub

### 11. What is Git?

A distributed version control system used to track source code changes.

---

### 12. What is the difference between Git and GitHub?

Git is a tool.

GitHub is a platform that hosts Git repositories.

---

### 13. What is a repository?

A storage location containing source code and Git history.

---

### 14. What is a commit?

A snapshot of code changes stored in Git history.

---

### 15. What is a branch?

An independent line of development.

---

### 16. Why are branches used?

To isolate feature development and avoid impacting the main codebase.

---

### 17. What is merging?

Combining changes from one branch into another.

---

### 18. What is a merge conflict?

When Git cannot automatically determine which changes should be kept.

---

### 19. What is a Pull Request?

A request to review and merge code changes.

---

### 20. What is a webhook?

An HTTP callback that notifies another system when an event occurs.

---

# Jenkins & CI/CD

### 21. What is Jenkins?

An open-source automation server used for CI/CD pipelines.

---

### 22. Why is Jenkins used?

To automate build, test, and deployment activities.

---

### 23. What is a Jenkins Pipeline?

A series of automated stages executed by Jenkins.

---

### 24. What is a Jenkinsfile?

A file containing pipeline definitions written in Groovy.

---

### 25. What are Jenkins stages?

Logical sections of a pipeline such as Build, Test, and Deploy.

---

### 26. What is the difference between Jenkins Controller and Agent?

Controller manages jobs.

Agents execute jobs.

---

### 27. What triggers Jenkins jobs?

* Webhooks
* Scheduled jobs
* Manual triggers
* API calls

---

### 28. What is an artifact?

The deployable output generated from a build.

---

### 29. What is artifact versioning?

Maintaining uniquely identifiable versions of build outputs.

---

### 30. What are common artifact repositories?

* Nexus
* Artifactory
* Docker Registry

---

# Docker

### 31. What is Docker?

A containerization platform used to package applications and dependencies.

---

### 32. Why is Docker used?

To eliminate environment-related issues and ensure consistency.

---

### 33. What is a container?

A running instance of a Docker image.

---

### 34. What is a Docker image?

A template used to create containers.

---

### 35. Difference between Image and Container?

Image = Blueprint

Container = Running instance

---

### 36. What is a Dockerfile?

A file containing instructions for building Docker images.

---

### 37. What is Docker Hub?

A public registry for Docker images.

---

### 38. What is a Docker Registry?

A repository for storing and distributing Docker images.

---

### 39. What are Docker Volumes?

Persistent storage used by containers.

---

### 40. Difference between VM and Container?

VM contains a full guest OS.

Containers share the host OS kernel.

---

# Kubernetes

### 41. What is Kubernetes?

A container orchestration platform.

---

### 42. Why is Kubernetes needed?

To automate deployment, scaling, and management of containers.

---

### 43. What is a Pod?

The smallest deployable unit in Kubernetes.

---

### 44. What is a Deployment?

A Kubernetes object used to manage Pods and updates.

---

### 45. What is a ReplicaSet?

A controller that maintains the desired number of Pods.

---

### 46. What is a Service?

A stable network endpoint used to access Pods.

---

### 47. What is Ingress?

A mechanism for exposing HTTP/HTTPS services externally.

---

### 48. What is ConfigMap?

A Kubernetes object used to store configuration data.

---

### 49. What is a Secret?

A Kubernetes object used to store sensitive information.

---

### 50. What is self-healing in Kubernetes?

The ability to automatically replace failed Pods and maintain desired state.

---

# Quick Revision

```text
Git          → Version Control

GitHub       → Code Hosting

Webhook      → Notification

Jenkins      → Automation

Artifact     → Build Output

Docker       → Containerization

Image        → Blueprint

Container    → Running Application

Kubernetes   → Container Orchestration

Pod          → Smallest Deployable Unit

Service      → Stable Endpoint

Ingress      → External Access
```
