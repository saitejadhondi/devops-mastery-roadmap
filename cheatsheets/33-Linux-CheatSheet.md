# 🐧 Linux Cheat Sheet

> Quick Revision Guide for DevOps, Cloud, SRE, Platform Engineering & Interviews

---

# 📂 File & Directory Commands

| Command          | Purpose                      |
| ---------------- | ---------------------------- |
| `pwd`            | Show current directory       |
| `ls`             | List files                   |
| `ls -l`          | Detailed list                |
| `ls -la`         | Show hidden files            |
| `cd dir`         | Change directory             |
| `cd ..`          | Go back one directory        |
| `mkdir test`     | Create directory             |
| `rmdir test`     | Remove empty directory       |
| `touch file.txt` | Create file                  |
| `cp file1 file2` | Copy file                    |
| `mv file1 file2` | Rename/Move file             |
| `rm file.txt`    | Delete file                  |
| `rm -rf dir`     | Delete directory recursively |

---

# 🔍 Search Commands

## Find Files

```bash
find / -name file.txt

find . -name "*.log"
```

## Search Text

```bash
grep "error" app.log

grep -r "database" .
```

## Locate File

```bash
locate nginx.conf
```

---

# 📄 View File Content

## Display File

```bash
cat file.txt
```

## First Lines

```bash
head file.txt

head -20 file.txt
```

## Last Lines

```bash
tail file.txt

tail -20 file.txt
```

## Live Log Monitoring

```bash
tail -f app.log
```

---

# 👤 User Management

## Current User

```bash
whoami
```

## User Information

```bash
id username
```

## Add User

```bash
sudo useradd user1
```

## Set Password

```bash
sudo passwd user1
```

## Delete User

```bash
sudo userdel user1
```

---

# 👥 Group Management

## Create Group

```bash
sudo groupadd devops
```

## Add User To Group

```bash
sudo usermod -aG devops user1
```

## View Groups

```bash
groups
```

---

# 🔐 File Permissions

## Permission Format

```text
-rwxr-xr-x
```

Meaning:

```text
Owner  Group  Others
```

---

## Change Permissions

```bash
chmod 755 script.sh

chmod +x script.sh
```

---

## Change Ownership

```bash
chown user file.txt

chown user:group file.txt
```

---

# ⚙️ Process Management

## View Processes

```bash
ps aux
```

## Interactive Process View

```bash
top

htop
```

## Find Process

```bash
ps aux | grep nginx
```

## Kill Process

```bash
kill PID
```

Force Kill:

```bash
kill -9 PID
```

---

# 🧠 Memory Commands

## Memory Usage

```bash
free -h
```

Example:

```text
Total
Used
Free
Available
```

---

## Virtual Memory Stats

```bash
vmstat
```

---

# 💾 Disk Commands

## Disk Usage

```bash
df -h
```

---

## Directory Size

```bash
du -sh *
```

---

## Find Large Files

```bash
du -ah / | sort -rh | head
```

---

# 🌐 Networking Commands

## Check IP Address

```bash
ip addr

hostname -I
```

---

## Ping Host

```bash
ping google.com
```

---

## DNS Lookup

```bash
nslookup google.com

dig google.com
```

---

## Test Connectivity

```bash
telnet host 80

nc -zv host 80
```

---

## Display Open Ports

```bash
ss -tulnp

netstat -tulnp
```

---

# 🔑 SSH Commands

## Connect To Server

```bash
ssh user@server-ip
```

---

## Copy File To Server

```bash
scp file.txt user@server:/tmp
```

---

## Generate SSH Key

```bash
ssh-keygen
```

---

## Test SSH

```bash
ssh -v user@server
```

---

# 📜 Logs

## System Logs

```bash
journalctl
```

---

## Recent Logs

```bash
journalctl -n 50
```

---

## Follow Logs

```bash
journalctl -f
```

---

## View Syslog

```bash
tail -f /var/log/syslog
```

---

# 🚀 Service Management (systemd)

## Service Status

```bash
systemctl status nginx
```

---

## Start Service

```bash
systemctl start nginx
```

---

## Stop Service

```bash
systemctl stop nginx
```

---

## Restart Service

```bash
systemctl restart nginx
```

---

## Enable At Boot

```bash
systemctl enable nginx
```

---

## Disable At Boot

```bash
systemctl disable nginx
```

---

# ⏰ Cron Jobs

## Edit Cron

```bash
crontab -e
```

---

## View Cron Jobs

```bash
crontab -l
```

---

## Example

Run every day at midnight:

```bash
0 0 * * * /home/user/backup.sh
```

---

# 📦 Package Management

## Ubuntu/Debian

Update:

```bash
sudo apt update
```

Install:

```bash
sudo apt install nginx
```

Remove:

```bash
sudo apt remove nginx
```

---

## RHEL/CentOS

Install:

```bash
sudo yum install nginx
```

or

```bash
sudo dnf install nginx
```

---

# 🔥 Most Important Interview Commands

## CPU Usage

```bash
top

htop
```

---

## Memory Usage

```bash
free -h
```

---

## Disk Usage

```bash
df -h
```

---

## Running Processes

```bash
ps aux
```

---

## Open Ports

```bash
ss -tulnp
```

---

## Logs

```bash
journalctl -xe
```

---

## Service Status

```bash
systemctl status service-name
```

---

# 🚨 Production Troubleshooting Flow

```text
Application Down
        ↓
Check Process
        ↓
Check Service
        ↓
Check Logs
        ↓
Check CPU
        ↓
Check Memory
        ↓
Check Disk
        ↓
Check Network
        ↓
Find Root Cause
```

---

# 🎯 Top Linux Interview Questions

### What is Linux?

Open-source operating system used in servers, cloud, containers, and DevOps environments.

---

### Difference Between Process and Thread?

Process:

```text
Independent Program
Own Memory
```

Thread:

```text
Execution Unit
Shared Memory
```

---

### What is a Zombie Process?

A process that has finished execution but still exists in the process table because the parent process hasn't collected its exit status.

---

### What is systemd?

Linux service manager responsible for:

```text
Starting Services
Managing Services
Boot Process
Logging
```

---

### What is SSH?

Secure Shell used for secure remote access to Linux servers.

---

# 🧠 One-Line Revision

```text
Files → Permissions → Processes → Memory → Disk → Networking → SSH → Logs → Services → Troubleshooting
```

---

# 🚀 Linux Master Formula

```text
Know Linux
      ↓
Understand Servers
      ↓
Understand Cloud
      ↓
Understand Containers
      ↓
Become Better At DevOps
```
