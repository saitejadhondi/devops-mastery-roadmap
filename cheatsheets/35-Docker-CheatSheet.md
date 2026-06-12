# 🐳 Docker Cheat Sheet

> Quick Revision Guide for Docker, Containers, Kubernetes & DevOps Interviews

---

# 🎯 What is Docker?

Docker is a containerization platform that packages applications and their dependencies into portable containers.

---

# 🗺 Docker Architecture

```text
Developer
    ↓
Dockerfile
    ↓
Docker Build
    ↓
Docker Image
    ↓
Docker Run
    ↓
Docker Container
```

---

# 🧠 Core Concepts

| Component        | Description                 |
| ---------------- | --------------------------- |
| Docker Engine    | Runs containers             |
| Docker Image     | Blueprint                   |
| Docker Container | Running Image               |
| Dockerfile       | Instructions to build image |
| Docker Hub       | Image Registry              |
| Volume           | Persistent Storage          |
| Network          | Container Communication     |

---

# 📦 Images

## List Images

```bash
docker images
```

---

## Pull Image

```bash
docker pull nginx
```

---

## Pull Specific Version

```bash
docker pull nginx:1.25
```

---

## Remove Image

```bash
docker rmi nginx
```

---

## Remove Multiple Images

```bash
docker rmi IMAGE_ID
```

---

# 🚀 Containers

## Run Container

```bash
docker run nginx
```

---

## Run In Background

```bash
docker run -d nginx
```

---

## Run With Name

```bash
docker run --name my-nginx nginx
```

---

## Run With Port Mapping

```bash
docker run -d -p 80:80 nginx
```

Meaning:

```text
Host Port : Container Port
```

---

## Run Interactive Container

```bash
docker run -it ubuntu bash
```

---

## List Running Containers

```bash
docker ps
```

---

## List All Containers

```bash
docker ps -a
```

---

## Stop Container

```bash
docker stop CONTAINER_ID
```

---

## Start Container

```bash
docker start CONTAINER_ID
```

---

## Restart Container

```bash
docker restart CONTAINER_ID
```

---

## Remove Container

```bash
docker rm CONTAINER_ID
```

---

# 🔍 Container Inspection

## View Logs

```bash
docker logs CONTAINER_ID
```

---

## Follow Logs

```bash
docker logs -f CONTAINER_ID
```

---

## Inspect Container

```bash
docker inspect CONTAINER_ID
```

---

## View Running Processes

```bash
docker top CONTAINER_ID
```

---

# 🖥 Execute Commands Inside Container

## Open Shell

```bash
docker exec -it CONTAINER_ID bash
```

For Alpine:

```bash
docker exec -it CONTAINER_ID sh
```

---

## Check Files

```bash
docker exec -it nginx ls
```

---

# 📄 Dockerfile

## Sample Dockerfile

```dockerfile
FROM ubuntu

RUN apt update

RUN apt install -y nginx

CMD ["nginx", "-g", "daemon off;"]
```

---

# 🏗 Build Images

## Build Image

```bash
docker build -t myapp .
```

---

## Build Specific Dockerfile

```bash
docker build -f Dockerfile.dev -t myapp .
```

---

## Tag Image

```bash
docker tag myapp:v1 myrepo/myapp:v1
```

---

# 📤 Push Images

## Login

```bash
docker login
```

---

## Push

```bash
docker push myrepo/myapp:v1
```

---

# 📥 Pull Images

```bash
docker pull myrepo/myapp:v1
```

---

# 💾 Volumes

## Create Volume

```bash
docker volume create myvolume
```

---

## List Volumes

```bash
docker volume ls
```

---

## Inspect Volume

```bash
docker volume inspect myvolume
```

---

## Remove Volume

```bash
docker volume rm myvolume
```

---

## Mount Volume

```bash
docker run -v myvolume:/data nginx
```

---

# 🌐 Networking

## List Networks

```bash
docker network ls
```

---

## Create Network

```bash
docker network create dev-network
```

---

## Inspect Network

```bash
docker network inspect dev-network
```

---

## Connect Container To Network

```bash
docker network connect dev-network container1
```

---

# 📋 Docker Compose

## Start Services

```bash
docker compose up
```

---

## Background Mode

```bash
docker compose up -d
```

---

## Stop Services

```bash
docker compose down
```

---

## View Logs

```bash
docker compose logs
```

---

# Sample docker-compose.yml

```yaml
version: "3"

services:

  web:
    image: nginx
    ports:
      - "80:80"
```

---

# 🧹 Cleanup Commands

## Remove Stopped Containers

```bash
docker container prune
```

---

## Remove Unused Images

```bash
docker image prune
```

---

## Remove Unused Volumes

```bash
docker volume prune
```

---

## Full Cleanup

```bash
docker system prune -a
```

---

# 🔥 Most Used Commands

```bash
docker images

docker ps

docker ps -a

docker pull nginx

docker run nginx

docker run -d nginx

docker stop

docker restart

docker rm

docker logs

docker exec

docker build

docker push

docker compose up
```

---

# 🚨 Troubleshooting Commands

## Container Not Running

```bash
docker ps -a
```

---

## Check Logs

```bash
docker logs CONTAINER_ID
```

---

## Check Configuration

```bash
docker inspect CONTAINER_ID
```

---

## Enter Container

```bash
docker exec -it CONTAINER_ID bash
```

---

# 🎯 Docker Interview Questions

## What is Docker?

Containerization platform.

---

## What is a Container?

Running instance of an image.

---

## What is an Image?

Blueprint for creating containers.

---

## Difference Between VM and Container?

VM:

```text
Guest OS
More Resources
Slower Startup
```

Container:

```text
Shares Host Kernel
Lightweight
Fast Startup
```

---

## What is Dockerfile?

File containing instructions to build Docker images.

---

## What is Docker Compose?

Tool for managing multi-container applications.

---

## What is a Volume?

Persistent storage for containers.

---

## Why Docker?

```text
Portability

Consistency

Isolation

Fast Deployment
```

---

# 🗺 Docker Workflow

```text
Application Code
        ↓
Dockerfile
        ↓
docker build
        ↓
Docker Image
        ↓
docker push
        ↓
Registry
        ↓
docker pull
        ↓
docker run
        ↓
Container
```

---

# ☸️ Docker + Kubernetes

```text
Application
      ↓
Dockerfile
      ↓
Docker Image
      ↓
Container Registry
      ↓
Kubernetes
      ↓
Pods
      ↓
Production
```

---

# 🚀 Production Troubleshooting Flow

```text
Container Down
       ↓
docker ps -a
       ↓
docker logs
       ↓
docker inspect
       ↓
docker exec
       ↓
Find Root Cause
```

---

# 🎯 One-Line Revision

```text
Dockerfile → Build → Image → Push → Pull → Run → Container
```

---

# 🧠 Docker Master Formula

```text
Code
 ↓
Dockerfile
 ↓
Build
 ↓
Image
 ↓
Registry
 ↓
Container
 ↓
Kubernetes
 ↓
Production
```
