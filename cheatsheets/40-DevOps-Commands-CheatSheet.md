# 🚀 DevOps Commands Cheat Sheet

> Ultimate Quick Revision Sheet for Linux, Git, Docker, Kubernetes, AWS, Terraform & DevOps Interviews

---

# 🎯 DevOps Daily Workflow

```text
Developer
    ↓
Git
    ↓
GitHub
    ↓
CI/CD
    ↓
Docker
    ↓
Kubernetes
    ↓
AWS
    ↓
Monitoring
    ↓
Production
```

---

# 🐧 Linux Commands

## Files & Directories

```bash
pwd
ls
ls -la

cd /path

mkdir test

touch file.txt

cp file1 file2

mv old new

rm file.txt

rm -rf folder
```

---

## Search

```bash
find . -name "*.log"

grep "error" app.log

grep -r "database" .
```

---

## Processes

```bash
ps aux

top

htop

kill PID

kill -9 PID
```

---

## Memory

```bash
free -h

vmstat
```

---

## Disk

```bash
df -h

du -sh *

du -ah | sort -rh
```

---

## Services

```bash
systemctl status nginx

systemctl start nginx

systemctl stop nginx

systemctl restart nginx
```

---

## Logs

```bash
journalctl -xe

journalctl -f

tail -f app.log
```

---

## Networking

```bash
ip addr

ping google.com

curl google.com

nslookup google.com

dig google.com

ss -tulnp
```

---

# 🌳 Git Commands

## Repository

```bash
git clone URL

git init

git status
```

---

## Commit Flow

```bash
git add .

git commit -m "message"

git push

git pull
```

---

## Branches

```bash
git branch

git checkout branch

git checkout -b feature

git merge feature
```

---

## Advanced

```bash
git rebase main

git stash

git stash pop

git cherry-pick COMMIT_ID

git revert COMMIT_ID

git reset --hard HEAD~1
```

---

## Logs

```bash
git log

git log --oneline

git reflog
```

---

# 🐳 Docker Commands

## Images

```bash
docker images

docker pull nginx

docker rmi IMAGE_ID
```

---

## Containers

```bash
docker run nginx

docker run -d nginx

docker run -p 80:80 nginx

docker ps

docker ps -a

docker stop CONTAINER

docker rm CONTAINER
```

---

## Logs

```bash
docker logs CONTAINER

docker logs -f CONTAINER
```

---

## Exec

```bash
docker exec -it CONTAINER bash
```

---

## Build

```bash
docker build -t app .

docker push image

docker pull image
```

---

## Cleanup

```bash
docker system prune -a
```

---

# ☸️ Kubernetes Commands

## Pods

```bash
kubectl get pods

kubectl describe pod POD

kubectl logs POD

kubectl delete pod POD
```

---

## Deployments

```bash
kubectl get deployments

kubectl scale deployment app --replicas=5

kubectl rollout restart deployment app
```

---

## Services

```bash
kubectl get svc

kubectl describe svc SERVICE
```

---

## Nodes

```bash
kubectl get nodes

kubectl describe node NODE
```

---

## YAML

```bash
kubectl apply -f deployment.yaml

kubectl delete -f deployment.yaml
```

---

## Exec

```bash
kubectl exec -it POD -- bash
```

---

## Troubleshooting

```bash
kubectl get events

kubectl top pod

kubectl top node
```

---

# ☁️ AWS CLI Commands

## Configure

```bash
aws configure
```

---

## S3

```bash
aws s3 ls

aws s3 cp file.txt s3://bucket

aws s3 sync . s3://bucket
```

---

## EC2

```bash
aws ec2 describe-instances
```

---

## IAM

```bash
aws iam list-users
```

---

## CloudWatch

```bash
aws logs describe-log-groups
```

---

# 🏗 Terraform Commands

## Initialize

```bash
terraform init
```

---

## Validate

```bash
terraform validate
```

---

## Format

```bash
terraform fmt
```

---

## Plan

```bash
terraform plan
```

---

## Apply

```bash
terraform apply
```

---

## Destroy

```bash
terraform destroy
```

---

## State

```bash
terraform state list

terraform output
```

---

# 🌐 Networking Commands

## Connectivity

```bash
ping google.com
```

---

## DNS

```bash
nslookup google.com

dig google.com
```

---

## Route

```bash
traceroute google.com
```

---

## Open Ports

```bash
ss -tulnp

netstat -tulnp
```

---

## Test Port

```bash
nc -zv google.com 443
```

---

# 🔐 SSH Commands

## Connect

```bash
ssh user@server-ip
```

---

## Generate Keys

```bash
ssh-keygen
```

---

## Copy File

```bash
scp file.txt user@server:/tmp
```

---

## Test SSH

```bash
ssh -v user@server
```

---

# 📦 Docker Compose Commands

## Start

```bash
docker compose up
```

---

## Background

```bash
docker compose up -d
```

---

## Stop

```bash
docker compose down
```

---

## Logs

```bash
docker compose logs
```

---

# 📊 Monitoring Commands

## CPU

```bash
top

htop
```

---

## Memory

```bash
free -h
```

---

## Disk

```bash
df -h
```

---

## Network

```bash
ss -tulnp
```

---

## Logs

```bash
journalctl -xe
```

---

# 🚨 Production Troubleshooting Commands

## Application Down

```bash
systemctl status app
```

---

## Check Logs

```bash
journalctl -xe

tail -f app.log
```

---

## Check Process

```bash
ps aux
```

---

## Check Port

```bash
ss -tulnp
```

---

## Check Kubernetes

```bash
kubectl get pods

kubectl logs POD
```

---

## Check Docker

```bash
docker ps

docker logs CONTAINER
```

---

# 🔥 Most Important Interview Commands

## Linux

```bash
top

free -h

df -h

ps aux
```

---

## Git

```bash
git status

git log

git rebase

git stash
```

---

## Docker

```bash
docker ps

docker logs

docker exec
```

---

## Kubernetes

```bash
kubectl get pods

kubectl logs

kubectl describe
```

---

## Terraform

```bash
terraform plan

terraform apply
```

---

## AWS

```bash
aws configure

aws s3 ls
```

---

# 🧠 DevOps Mental Model

```text
Linux
 ↓
Git
 ↓
Docker
 ↓
Kubernetes
 ↓
AWS
 ↓
Terraform
 ↓
Monitoring
 ↓
Production
```

---

# 🎯 30-Second Interview Revision

```text
Linux
 ├── ps
 ├── top
 ├── free
 └── df

Git
 ├── add
 ├── commit
 ├── push
 └── rebase

Docker
 ├── build
 ├── run
 ├── logs
 └── exec

Kubernetes
 ├── get
 ├── describe
 ├── logs
 └── apply

Terraform
 ├── init
 ├── plan
 ├── apply
 └── destroy

AWS
 ├── EC2
 ├── S3
 ├── IAM
 ├── VPC
 └── CloudWatch
```

---

# 🚀 DevOps Master Formula

```text
Code
 ↓
Git
 ↓
GitHub
 ↓
CI/CD
 ↓
Docker
 ↓
Registry
 ↓
Kubernetes
 ↓
AWS
 ↓
Monitoring
 ↓
Production
```
