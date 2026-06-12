# ☸️ Kubernetes Cheat Sheet

> Quick Revision Guide for Kubernetes, DevOps, Cloud & Interview Preparation

---

# 🎯 What is Kubernetes?

Kubernetes (K8s) is a container orchestration platform used to:

```text
Deploy Containers

Scale Applications

Manage Containers

Recover Failed Containers

Automate Operations
```

---

# 🗺 Kubernetes Architecture

```text
User
  ↓
kubectl
  ↓
API Server
  ↓
Scheduler
  ↓
Worker Nodes
  ↓
Pods
  ↓
Containers
```

---

# 🧠 Core Components

| Component         | Purpose                  |
| ----------------- | ------------------------ |
| Pod               | Smallest Deployable Unit |
| Deployment        | Manages Pods             |
| ReplicaSet        | Maintains Pod Count      |
| Service           | Exposes Pods             |
| Ingress           | External Access          |
| ConfigMap         | Configuration            |
| Secret            | Sensitive Data           |
| Namespace         | Logical Isolation        |
| Persistent Volume | Storage                  |
| StatefulSet       | Stateful Apps            |
| DaemonSet         | One Pod Per Node         |
| Job               | One-Time Task            |
| CronJob           | Scheduled Task           |

---

# 📦 Pods

## List Pods

```bash
kubectl get pods
```

---

## Detailed Pod Information

```bash
kubectl describe pod POD_NAME
```

---

## Pod Logs

```bash
kubectl logs POD_NAME
```

---

## Follow Logs

```bash
kubectl logs -f POD_NAME
```

---

## Delete Pod

```bash
kubectl delete pod POD_NAME
```

---

# 🚀 Deployments

## List Deployments

```bash
kubectl get deployments
```

---

## Deployment Details

```bash
kubectl describe deployment DEPLOYMENT_NAME
```

---

## Create Deployment

```bash
kubectl create deployment nginx --image=nginx
```

---

## Scale Deployment

```bash
kubectl scale deployment nginx --replicas=5
```

---

## Restart Deployment

```bash
kubectl rollout restart deployment nginx
```

---

## Deployment Status

```bash
kubectl rollout status deployment nginx
```

---

# 📜 YAML Files

## Apply YAML

```bash
kubectl apply -f deployment.yaml
```

---

## Delete Resource

```bash
kubectl delete -f deployment.yaml
```

---

## View YAML

```bash
kubectl get deployment nginx -o yaml
```

---

# 🌐 Services

## List Services

```bash
kubectl get svc
```

---

## Service Details

```bash
kubectl describe svc SERVICE_NAME
```

---

## Service Types

```text
ClusterIP

NodePort

LoadBalancer

ExternalName
```

---

# 🌍 Ingress

## List Ingress

```bash
kubectl get ingress
```

---

## Describe Ingress

```bash
kubectl describe ingress
```

---

## Traffic Flow

```text
Internet
   ↓
Ingress
   ↓
Service
   ↓
Pod
```

---

# 📁 Namespaces

## List Namespaces

```bash
kubectl get namespaces
```

---

## Create Namespace

```bash
kubectl create namespace dev
```

---

## Use Namespace

```bash
kubectl get pods -n dev
```

---

## Delete Namespace

```bash
kubectl delete namespace dev
```

---

# 🔐 ConfigMaps

## List ConfigMaps

```bash
kubectl get configmaps
```

---

## Create ConfigMap

```bash
kubectl create configmap app-config \
--from-literal=ENV=prod
```

---

## View ConfigMap

```bash
kubectl describe configmap app-config
```

---

# 🔑 Secrets

## List Secrets

```bash
kubectl get secrets
```

---

## Create Secret

```bash
kubectl create secret generic db-secret \
--from-literal=password=admin123
```

---

## Describe Secret

```bash
kubectl describe secret db-secret
```

---

# 💾 Persistent Storage

## List Persistent Volumes

```bash
kubectl get pv
```

---

## List PVC

```bash
kubectl get pvc
```

---

## Storage Flow

```text
Application
     ↓
PVC
     ↓
PV
     ↓
Storage
```

---

# 🖥 Nodes

## List Nodes

```bash
kubectl get nodes
```

---

## Node Details

```bash
kubectl describe node NODE_NAME
```

---

## Drain Node

```bash
kubectl drain NODE_NAME
```

---

## Uncordon Node

```bash
kubectl uncordon NODE_NAME
```

---

# 🔄 Rollouts

## Deployment History

```bash
kubectl rollout history deployment nginx
```

---

## Rollback

```bash
kubectl rollout undo deployment nginx
```

---

## Rollback Specific Revision

```bash
kubectl rollout undo deployment nginx --to-revision=2
```

---

# 📊 Resource Usage

## Pod Usage

```bash
kubectl top pod
```

---

## Node Usage

```bash
kubectl top node
```

---

# 🧹 Cleanup Commands

## Delete Pod

```bash
kubectl delete pod POD_NAME
```

---

## Delete Deployment

```bash
kubectl delete deployment nginx
```

---

## Delete Service

```bash
kubectl delete svc nginx
```

---

## Delete Namespace

```bash
kubectl delete namespace dev
```

---

# 🔥 Most Used Commands

```bash
kubectl get pods

kubectl get deployments

kubectl get svc

kubectl get ingress

kubectl get nodes

kubectl describe pod

kubectl logs

kubectl exec

kubectl apply -f

kubectl delete -f
```

---

# 🖥 Execute Commands Inside Pod

## Open Shell

```bash
kubectl exec -it POD_NAME -- bash
```

---

For Alpine:

```bash
kubectl exec -it POD_NAME -- sh
```

---

# 🔍 Troubleshooting Commands

## Describe Pod

```bash
kubectl describe pod POD_NAME
```

---

## View Logs

```bash
kubectl logs POD_NAME
```

---

## Events

```bash
kubectl get events
```

---

## Resource Usage

```bash
kubectl top pod
```

---

# 🚨 Common Errors

## CrashLoopBackOff

Meaning:

```text
Container Starts
      ↓
Container Crashes
      ↓
Kubernetes Restarts It
```

Check:

```bash
kubectl logs POD_NAME
```

---

## ImagePullBackOff

Meaning:

```text
Image Cannot Be Downloaded
```

Check:

```text
Image Name

Registry Access

Image Exists
```

---

## Pending

Meaning:

```text
Pod Cannot Be Scheduled
```

Possible Causes:

```text
CPU

Memory

Storage

Node Selector
```

---

# ☸️ Important Kubernetes Objects

## Deployment

```text
Stateless Applications
```

Examples:

```text
Web Applications

APIs
```

---

## StatefulSet

```text
Stateful Applications
```

Examples:

```text
MySQL

MongoDB

PostgreSQL
```

---

## DaemonSet

```text
One Pod Per Node
```

Examples:

```text
Prometheus Exporter

Fluentd

Monitoring Agent
```

---

## Job

```text
Run Once
```

---

## CronJob

```text
Run On Schedule
```

---

# 🎯 Kubernetes Interview Questions

## What is Kubernetes?

Container orchestration platform.

---

## What is a Pod?

Smallest deployable unit.

Contains:

```text
One Or More Containers
```

---

## What is Deployment?

Manages Pods.

Provides:

```text
Scaling

Self-Healing

Rolling Updates
```

---

## What is Service?

Provides stable access to Pods.

---

## What is Ingress?

Manages external traffic routing.

---

## Deployment vs StatefulSet?

Deployment:

```text
Stateless
```

StatefulSet:

```text
Stateful
```

---

## ConfigMap vs Secret?

ConfigMap:

```text
Configuration Data
```

Secret:

```text
Sensitive Data
```

---

# 🚀 Kubernetes Workflow

```text
Application
      ↓
Docker Image
      ↓
Container Registry
      ↓
Deployment
      ↓
Pods
      ↓
Service
      ↓
Ingress
      ↓
Users
```

---

# 🔥 Production Troubleshooting Flow

```text
Application Down
        ↓
kubectl get pods
        ↓
kubectl describe pod
        ↓
kubectl logs
        ↓
kubectl get events
        ↓
Find Root Cause
```

---

# 🧠 Kubernetes Mental Model

```text
Deployment
     ↓
ReplicaSet
     ↓
Pods
     ↓
Containers
```

---

# 🎯 One-Line Revision

```text
Deployment → Pod → Service → Ingress → Users
```

---

# 🚀 Kubernetes Master Formula

```text
Docker Image
       ↓
Registry
       ↓
Kubernetes Deployment
       ↓
Pods
       ↓
Service
       ↓
Ingress
       ↓
Production
```
