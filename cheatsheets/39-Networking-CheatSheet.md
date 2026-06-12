# 🌐 Networking Cheat Sheet

> Quick Revision Guide for Networking, Linux, Cloud, DevOps & Interviews

---

# 🎯 What is Networking?

Networking enables communication between devices over a network.

Example:

```text
Laptop
   ↓
Router
   ↓
Internet
   ↓
Server
```

---

# 🗺 What Happens When You Type google.com?

```text
Browser
   ↓
DNS Lookup
   ↓
Get IP Address
   ↓
TCP Handshake
   ↓
HTTPS Connection
   ↓
Request Sent
   ↓
Google Server
   ↓
Response Returned
```

---

# 🌍 OSI Model

```text
7 Application
6 Presentation
5 Session
4 Transport
3 Network
2 Data Link
1 Physical
```

---

## Easy Memory Trick

```text
All
People
Seem
To
Need
Data
Processing
```

---

# 🌐 TCP/IP Model

```text
Application
Transport
Internet
Network Access
```

---

# ⚡ TCP vs UDP

| TCP                 | UDP              |
| ------------------- | ---------------- |
| Reliable            | Fast             |
| Connection-Oriented | Connectionless   |
| Error Checking      | Minimal Checking |
| Slower              | Faster           |

---

## TCP Examples

```text
HTTPS

SSH

FTP

Database Connections
```

---

## UDP Examples

```text
DNS

Video Streaming

Gaming

VoIP
```

---

# 🤝 TCP 3-Way Handshake

```text
Client                Server

SYN  ---------------->

      <-------------- SYN-ACK

ACK  ---------------->
```

Connection established.

---

# 🔚 TCP Connection Close

```text
FIN
ACK
FIN
ACK
```

---

# 🌍 IP Address

Unique identifier for a device.

Example:

```text
192.168.1.10
```

---

# Private IP Ranges

```text
10.0.0.0/8

172.16.0.0/12

192.168.0.0/16
```

---

# Public IP

Accessible over internet.

Example:

```text
8.8.8.8
```

---

# 📌 CIDR Notation

Example:

```text
192.168.1.0/24
```

Meaning:

```text
24 Bits Network

8 Bits Host
```

---

# Common CIDR

| CIDR | Hosts |
| ---- | ----- |
| /24  | 254   |
| /25  | 126   |
| /26  | 62    |
| /27  | 30    |
| /28  | 14    |

---

# 🌐 DNS

DNS converts:

```text
google.com
      ↓
142.250.x.x
```

---

# Common DNS Records

| Record | Purpose       |
| ------ | ------------- |
| A      | Domain → IPv4 |
| AAAA   | Domain → IPv6 |
| CNAME  | Alias         |
| MX     | Mail          |
| TXT    | Verification  |
| NS     | Name Server   |

---

# DNS Flow

```text
Browser
    ↓
DNS Resolver
    ↓
DNS Server
    ↓
IP Address
```

---

# 🔌 Common Ports

| Port  | Protocol    |
| ----- | ----------- |
| 20/21 | FTP         |
| 22    | SSH         |
| 23    | Telnet      |
| 25    | SMTP        |
| 53    | DNS         |
| 80    | HTTP        |
| 110   | POP3        |
| 143   | IMAP        |
| 443   | HTTPS       |
| 3306  | MySQL       |
| 5432  | PostgreSQL  |
| 6379  | Redis       |
| 9092  | Kafka       |
| 8080  | Application |

---

# 🔐 HTTP vs HTTPS

## HTTP

```text
Plain Text

Not Encrypted

Port 80
```

---

## HTTPS

```text
Encrypted

SSL/TLS

Port 443
```

---

# 🔒 SSL/TLS

Purpose:

```text
Encryption

Authentication

Secure Communication
```

---

Flow:

```text
Client
   ↓
TLS Handshake
   ↓
Encrypted Connection
```

---

# 🚪 NAT (Network Address Translation)

Converts:

```text
Private IP
     ↓
Public IP
```

Example:

```text
192.168.1.10
     ↓
52.x.x.x
```

---

# 🔥 Firewall

Controls network traffic.

Example:

```text
Allow
 22 SSH
 80 HTTP
443 HTTPS

Block Everything Else
```

---

# ⚖️ Load Balancer

Distributes traffic.

```text
Users
   ↓
Load Balancer
   ↓
Server1
Server2
Server3
```

---

# Types of Load Balancer

```text
Layer 4

Layer 7
```

---

# 🔁 Proxy vs Reverse Proxy

## Proxy

```text
Client
   ↓
Proxy
   ↓
Internet
```

---

## Reverse Proxy

```text
Client
   ↓
Nginx
   ↓
Application Server
```

---

# 🌍 VPN

Virtual Private Network.

Creates encrypted tunnel.

```text
Laptop
   ↓
VPN Tunnel
   ↓
Company Network
```

---

# 🛡 Subnet

Logical division of network.

Example:

```text
VPC
 │
 ├── Public Subnet
 │
 └── Private Subnet
```

---

# ☁️ AWS Networking

```text
VPC
 ↓
Subnet
 ↓
Route Table
 ↓
Internet Gateway
 ↓
Security Group
```

---

# 🔍 Networking Commands

## Show IP

```bash
ip addr

hostname -I
```

---

## Ping

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

## Route Path

```bash
traceroute google.com
```

---

## Test Port

```bash
telnet google.com 80

nc -zv google.com 80
```

---

## Open Ports

```bash
ss -tulnp

netstat -tulnp
```

---

## Download Test

```bash
curl https://google.com
```

---

# 🔥 Most Used Commands

```bash
ping

curl

dig

nslookup

traceroute

netstat

ss

telnet

nc
```

---

# 🚨 Troubleshooting Workflow

## Website Not Opening

```text
Check DNS
      ↓
Check Ping
      ↓
Check Port
      ↓
Check Firewall
      ↓
Check Server
```

---

## Server Not Reachable

```text
Ping
 ↓
Traceroute
 ↓
Firewall
 ↓
Security Group
 ↓
Application
```

---

# 🧠 Networking Interview Questions

## What is DNS?

Domain Name System.

Converts:

```text
Domain
 ↓
IP Address
```

---

## What is TCP?

Reliable communication protocol.

---

## What is UDP?

Fast connectionless protocol.

---

## What is CIDR?

Classless Inter-Domain Routing.

Used for subnet sizing.

---

## What is NAT?

Converts private IPs to public IPs.

---

## What is Load Balancer?

Distributes traffic across servers.

---

## What is Firewall?

Filters network traffic.

---

## What is VPC?

Private virtual network in cloud.

---

## Difference Between HTTP and HTTPS?

HTTP:

```text
Not Secure
Port 80
```

HTTPS:

```text
Encrypted
Port 443
```

---

## Difference Between Proxy and Reverse Proxy?

Proxy:

```text
Represents Client
```

Reverse Proxy:

```text
Represents Server
```

---

# 🏗 Real Production Flow

```text
User
  ↓
DNS
  ↓
Load Balancer
  ↓
Nginx
  ↓
Application
  ↓
Database
```

---

# 🎯 One-Line Revision

```text
DNS → TCP → HTTPS → Load Balancer → Server → Response
```

---

# 🚀 Networking Master Formula

```text
Domain
   ↓
DNS
   ↓
IP Address
   ↓
TCP Connection
   ↓
HTTPS
   ↓
Load Balancer
   ↓
Application
   ↓
Database
```
