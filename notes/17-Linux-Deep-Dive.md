# 🐧 17-Linux-Deep-Dive.md

# Linux Deep Dive

## Processes, Threads, Memory, System Calls, Systemd, Boot Process & Production Linux

> Linux is the foundation of modern infrastructure.
>
> Most cloud servers, Docker containers, Kubernetes nodes, CI/CD servers, and production systems run Linux.
>
> To become a DevOps Engineer, Cloud Engineer, Platform Engineer, or SRE, Linux is non-negotiable.

---

# 📚 Table of Contents

1. What is Linux?
2. Why Linux Dominates DevOps
3. Linux Architecture
4. User Space vs Kernel Space
5. Kernel
6. System Calls
7. Processes
8. Threads
9. Process States
10. Zombie & Orphan Processes
11. Daemons
12. Signals
13. Memory Management
14. Linux File System
15. Users & Permissions
16. Boot Process
17. Systemd
18. Cron Jobs
19. Logs & Journalctl
20. Essential Commands
21. Production Troubleshooting
22. Interview Questions

---

# Chapter 1: What is Linux?

Linux is:

```text
Open Source
Unix-Like
Operating System Kernel
```

---

When people say:

```text
Ubuntu
RedHat
CentOS
Debian
Amazon Linux
```

they are talking about:

```text
Linux Distributions
```

---

Linux Kernel:

```text
CPU Management
Memory Management
Process Scheduling
Device Drivers
File Systems
Networking
```

---

# Chapter 2: Why Linux Dominates DevOps

Almost everything runs Linux:

```text
AWS EC2
Docker
Kubernetes
Jenkins
Nginx
Terraform Runners
GitHub Actions Runners
```

---

Why?

```text
Stable
Secure
Scalable
Open Source
Efficient
```

---

# Chapter 3: Linux Architecture

Architecture:

```text
Applications
      ↓
System Calls
      ↓
Kernel
      ↓
Hardware
```

---

Think:

```text
Applications
cannot directly talk to hardware.

Kernel acts as the manager.
```

---

# Chapter 4: User Space vs Kernel Space

Linux separates execution into:

```text
User Space
Kernel Space
```

---

User Space:

```text
Chrome
Python
Java
Nginx
Docker CLI
```

---

Kernel Space:

```text
Memory
CPU
Disk
Network
Drivers
```

---

Architecture:

```text
User Space
     ↓
System Calls
     ↓
Kernel Space
```

---

# Chapter 5: Kernel

Kernel is the heart of Linux.

Responsibilities:

```text
Process Scheduling
Memory Management
Device Management
Networking
Security
```

---

Think:

```text
Kernel
     =
Operating System Manager
```

---

# Chapter 6: System Calls

Applications cannot access hardware directly.

They request services from the kernel.

Called:

```text
System Calls
```

---

Examples:

```text
open()
read()
write()
fork()
exec()
```

---

Flow:

```text
Application
      ↓
System Call
      ↓
Kernel
      ↓
Hardware
```

---

# Chapter 7: Processes

A process is:

```text
A Running Program
```

---

Example:

```text
Chrome
VS Code
Nginx
Docker
```

---

Commands:

```bash
ps -ef
top
htop
```

---

View Processes:

```bash
ps aux
```

---

# Chapter 8: Threads

A thread is:

```text
Smallest Unit Of Execution
```

inside a process.

---

Example:

```text
Chrome Process
     ↓
Thread 1
Thread 2
Thread 3
```

---

Difference:

| Process         | Thread        |
| --------------- | ------------- |
| Independent     | Shares Memory |
| Heavyweight     | Lightweight   |
| Separate Memory | Shared Memory |

---

Interview Favorite:

```text
Process = Separate House

Thread = Room Inside House
```

---

# Chapter 9: Process States

Common States:

```text
Running
Ready
Waiting
Stopped
Zombie
```

---

Example:

```text
Running
   ↓
Waiting
   ↓
Running
```

---

# Chapter 10: Zombie & Orphan Processes

## Zombie Process

Finished execution.

Parent hasn't collected exit status.

---

State:

```text
Defunct Process
```

---

View:

```bash
ps aux | grep Z
```

---

## Orphan Process

Parent process dies.

Child survives.

---

Linux assigns:

```text
PID 1
```

(Systemd)

as new parent.

---

Interview Favorite:

```text
Zombie = Dead Child Waiting

Orphan = Alive Child Without Parent
```

---

# Chapter 11: Daemons

Daemon:

```text
Background Service
```

---

Examples:

```text
sshd
nginx
docker
cron
```

---

View:

```bash
systemctl list-units
```

---

Think:

```text
Daemon
    =
Windows Service
```

---

# Chapter 12: Signals

Signals allow processes to communicate.

---

Common Signals:

```text
SIGTERM
SIGKILL
SIGINT
SIGHUP
```

---

Terminate Process:

```bash
kill -15 PID
```

---

Force Kill:

```bash
kill -9 PID
```

---

Interview:

```text
SIGTERM = Graceful Shutdown

SIGKILL = Immediate Termination
```

---

# Chapter 13: Memory Management

Linux manages:

```text
RAM
Swap
Virtual Memory
```

---

Check Memory:

```bash
free -m
```

---

Output:

```text
Total
Used
Free
Available
```

---

Virtual Memory:

```text
Application Thinks
It Has Large Memory
```

even when physical RAM is limited.

---

# Chapter 14: Linux File System

Everything in Linux is a file.

---

Important Directories:

```text
/       Root
/home   Users
/etc    Configurations
/var    Logs
/tmp    Temporary Files
/bin    Commands
```

---

Example:

```bash
ls /
```

---

# Chapter 15: Users & Permissions

Linux Security:

```text
User
Group
Others
```

---

Permissions:

```text
r = Read
w = Write
x = Execute
```

---

Example:

```bash
-rwxr-xr-x
```

Meaning:

```text
Owner = rwx

Group = r-x

Others = r-x
```

---

Change Permission:

```bash
chmod 755 file.sh
```

---

Change Owner:

```bash
chown user file.sh
```

---

# Chapter 16: Linux Boot Process

System Startup:

```text
BIOS/UEFI
      ↓
Bootloader
      ↓
Kernel
      ↓
Systemd
      ↓
Services
      ↓
Login
```

---

Interview Favorite:

```text
Who starts Linux?

Bootloader
```

---

# Chapter 17: Systemd

Systemd is:

```text
Init System
Service Manager
```

---

PID:

```text
1
```

---

Commands:

Start Service:

```bash
systemctl start nginx
```

---

Stop Service:

```bash
systemctl stop nginx
```

---

Restart:

```bash
systemctl restart nginx
```

---

Status:

```bash
systemctl status nginx
```

---

# Chapter 18: Cron Jobs

Cron schedules tasks.

---

Example:

```bash
0 2 * * * backup.sh
```

Meaning:

```text
Run Daily
At 2 AM
```

---

Edit:

```bash
crontab -e
```

---

View:

```bash
crontab -l
```

---

# Chapter 19: Logs & Journalctl

Logs are critical for troubleshooting.

---

Common Location:

```text
/var/log
```

---

System Logs:

```bash
journalctl
```

---

View Latest Logs:

```bash
journalctl -xe
```

---

Nginx Logs:

```text
/var/log/nginx/
```

---

# Chapter 20: Essential Commands

Disk Usage:

```bash
df -h
```

---

Directory Size:

```bash
du -sh *
```

---

Memory:

```bash
free -m
```

---

Processes:

```bash
ps -ef
```

---

Real-Time Monitoring:

```bash
top
htop
```

---

Network:

```bash
netstat -tulpn
```

or

```bash
ss -tulpn
```

---

# Chapter 21: Production Troubleshooting

## High CPU

Check:

```bash
top
```

---

## High Memory

Check:

```bash
free -m
```

---

## Disk Full

Check:

```bash
df -h
```

---

## Service Down

Check:

```bash
systemctl status nginx
```

---

## Logs

Check:

```bash
journalctl -xe
```

---

# Chapter 22: Why Linux Matters In DevOps

Everything ultimately runs on Linux:

```text
Docker
Kubernetes
AWS EC2
Jenkins
Nginx
Terraform
Ansible
```

Understanding Linux helps you troubleshoot production systems effectively.

---

# 🔥 Interview Questions

### What Is Linux?

Linux is an open-source Unix-like operating system kernel used in servers, cloud environments, and embedded systems.

---

### What Is A Process?

A running instance of a program.

---

### What Is A Thread?

The smallest unit of execution within a process.

---

### Process vs Thread?

Processes have separate memory.

Threads share memory.

---

### What Is A Zombie Process?

A completed process whose parent has not collected its exit status.

---

### What Is An Orphan Process?

A running process whose parent has terminated.

---

### What Is A Daemon?

A background service that runs continuously.

---

### What Is A System Call?

A mechanism that allows user-space applications to request services from the Linux kernel.

---

### What Is Systemd?

The modern Linux init system and service manager.

---

### What Happens During Linux Boot?

```text
BIOS/UEFI
   ↓
Bootloader
   ↓
Kernel
   ↓
Systemd
   ↓
Services
```

---

# Mental Model

```text
Application
      ↓
Process
      ↓
Thread
      ↓
System Call
      ↓
Kernel
      ↓
CPU / Memory / Disk
```

---

# One-Line Summary

Linux is the operating system foundation of modern cloud and DevOps infrastructure, providing process management, memory management, networking, security, and service orchestration through the Linux kernel.
