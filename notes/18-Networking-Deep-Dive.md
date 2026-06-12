# 🌐 18-Networking-Deep-Dive.md

# Networking Deep Dive

## OSI Model, TCP/IP, DNS, HTTP, HTTPS, CIDR, NAT, Load Balancers, Firewalls & Production Networking

> Networking is the language of distributed systems.
>
> Every request in a cloud application travels through networks.
>
> Understanding networking helps explain:
>
> * How websites work
> * How Kubernetes networking works
> * How AWS networking works
> * How Load Balancers work
> * How DNS works
> * How the Internet works

---

# 📚 Table of Contents

1. What Is Networking?
2. Why Networking Matters in DevOps
3. OSI Model
4. TCP/IP Model
5. IP Address
6. Public vs Private IP
7. Ports
8. TCP
9. TCP 3-Way Handshake
10. UDP
11. DNS
12. What Happens When You Open Google.com
13. HTTP
14. HTTPS
15. SSL/TLS
16. CIDR
17. Subnetting
18. NAT
19. Firewalls
20. Proxy & Reverse Proxy
21. Load Balancers
22. VPN
23. Essential Linux Networking Commands
24. Production Troubleshooting
25. Interview Questions

---

# Chapter 1: What Is Networking?

Networking is:

```text
Communication Between Devices
```

---

Examples:

```text
Laptop ↔ Server

Browser ↔ Website

Pod ↔ Pod

Microservice ↔ Database
```

---

Without networking:

```text
No Internet
No Cloud
No Kubernetes
No AWS
```

---

# Chapter 2: Why Networking Matters In DevOps

Almost every DevOps tool relies on networking.

Examples:

```text
GitHub
Jenkins
Docker
Kubernetes
AWS
Terraform
Nginx
```

---

Flow:

```text
Developer
    ↓
GitHub
    ↓
Jenkins
    ↓
Docker Registry
    ↓
Kubernetes
```

Everything communicates through networks.

---

# Chapter 3: OSI Model

OSI Model:

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

Easy Memory Trick:

```text
Please
Do
Not
Throw
Sausage
Pizza
Away
```

---

Most Important Layers:

```text
Application
Transport
Network
```

---

# Chapter 4: TCP/IP Model

Real-world networking uses:

```text
Application
Transport
Internet
Network Access
```

---

Mapping:

```text
OSI → TCP/IP

Application → Application
Transport → Transport
Network → Internet
Data Link → Network Access
```

---

# Chapter 5: IP Address

IP Address:

```text
Unique Network Address
```

---

Example:

```text
192.168.1.10
```

---

Think:

```text
Home Address
For Computers
```

---

# Chapter 6: Public vs Private IP

## Public IP

Accessible from internet.

Example:

```text
54.201.10.5
```

---

## Private IP

Internal network only.

Examples:

```text
10.0.0.0/8

172.16.0.0/12

192.168.0.0/16
```

---

AWS Example:

```text
Internet
   ↓
Public IP
   ↓
Private IP
```

---

# Chapter 7: Ports

One server can run multiple applications.

Ports identify applications.

---

Examples:

```text
22     SSH
80     HTTP
443    HTTPS
3306   MySQL
5432   PostgreSQL
6379   Redis
```

---

Think:

```text
IP Address
   =
Building

Port
   =
Apartment Number
```

---

# Chapter 8: TCP

TCP:

```text
Transmission Control Protocol
```

---

Features:

```text
Reliable
Ordered
Error Checked
```

---

Used By:

```text
HTTP
HTTPS
SSH
Database Connections
```

---

# Chapter 9: TCP 3-Way Handshake

Before communication:

```text
Client
  ↓ SYN
Server

Client
  ↓ SYN-ACK
Server

Client
  ↓ ACK
Server
```

---

Flow:

```text
1 SYN

2 SYN ACK

3 ACK
```

---

Purpose:

```text
Connection Establishment
```

---

Interview Favorite.

---

# Chapter 10: UDP

UDP:

```text
User Datagram Protocol
```

---

Features:

```text
Fast
Connectionless
No Delivery Guarantee
```

---

Used By:

```text
Video Streaming
Gaming
DNS
VoIP
```

---

Difference:

| TCP        | UDP            |
| ---------- | -------------- |
| Reliable   | Fast           |
| Connection | Connectionless |
| Ordered    | Unordered      |

---

# Chapter 11: DNS

DNS:

```text
Domain Name System
```

---

Converts:

```text
google.com
```

to:

```text
142.x.x.x
```

---

Think:

```text
Internet Phonebook
```

---

# Chapter 12: What Happens When You Open Google.com

Step 1

```text
Browser
 ↓
DNS Lookup
```

---

Step 2

```text
Get IP Address
```

---

Step 3

```text
TCP Handshake
```

---

Step 4

```text
HTTPS Request
```

---

Step 5

```text
Server Response
```

---

Complete Flow:

```text
Browser
 ↓
DNS
 ↓
IP Address
 ↓
TCP
 ↓
HTTPS
 ↓
Google Server
```

---

# Chapter 13: HTTP

HTTP:

```text
HyperText Transfer Protocol
```

---

Methods:

```text
GET
POST
PUT
DELETE
PATCH
```

---

Example:

```http
GET /users
```

---

# Chapter 14: HTTPS

HTTPS:

```text
HTTP + Encryption
```

---

Uses:

```text
TLS
Certificates
Encryption
```

---

Benefits:

```text
Security
Privacy
Integrity
```

---

# Chapter 15: SSL/TLS

TLS secures communication.

---

Flow:

```text
Browser
   ↓
Certificate
   ↓
Encryption
   ↓
Secure Communication
```

---

Most modern systems use:

```text
TLS
```

instead of SSL.

---

# Chapter 16: CIDR

CIDR:

```text
Classless Inter-Domain Routing
```

---

Example:

```text
192.168.1.0/24
```

---

Meaning:

```text
24 Bits
Network Portion
```

---

Common Examples:

```text
/24 → 256 IPs

/16 → 65536 IPs

/8  → 16 Million IPs
```

---

Used heavily in:

```text
AWS VPC
Kubernetes
Networking
```

---

# Chapter 17: Subnetting

Subnetting:

```text
Divide Large Network
Into Smaller Networks
```

---

Example:

```text
10.0.0.0/16

↓

10.0.1.0/24
10.0.2.0/24
10.0.3.0/24
```

---

Benefits:

```text
Security
Isolation
Scalability
```

---

# Chapter 18: NAT

NAT:

```text
Network Address Translation
```

---

Purpose:

```text
Private IP
     ↓
Public IP
```

---

Example:

```text
Private Server
     ↓
NAT Gateway
     ↓
Internet
```

---

Used extensively in AWS.

---

# Chapter 19: Firewalls

Firewall:

```text
Traffic Filter
```

---

Controls:

```text
Allow
Deny
```

traffic.

---

AWS Example:

```text
Security Groups
```

act as firewalls.

---

Example:

```text
Allow 22
Allow 443
Block Others
```

---

# Chapter 20: Proxy & Reverse Proxy

## Forward Proxy

```text
User
 ↓
Proxy
 ↓
Internet
```

---

Protects clients.

---

## Reverse Proxy

```text
User
 ↓
Nginx
 ↓
Application
```

---

Protects servers.

---

# Chapter 21: Load Balancers

Purpose:

```text
Distribute Traffic
```

---

Architecture:

```text
Users
   ↓
Load Balancer
   ↓
Server A

Server B

Server C
```

---

Benefits:

```text
Scalability
High Availability
Fault Tolerance
```

---

AWS Example:

```text
ALB
NLB
```

---

# Chapter 22: VPN

VPN:

```text
Virtual Private Network
```

---

Purpose:

```text
Secure Communication
```

over public internet.

---

Example:

```text
Laptop
   ↓
VPN Tunnel
   ↓
Company Network
```

---

# Chapter 23: Essential Linux Networking Commands

Check IP:

```bash
ip addr
```

---

Routing:

```bash
ip route
```

---

DNS:

```bash
nslookup google.com
```

---

Ping:

```bash
ping google.com
```

---

Open Ports:

```bash
ss -tulpn
```

---

Trace Route:

```bash
traceroute google.com
```

---

HTTP Request:

```bash
curl https://google.com
```

---

# Chapter 24: Production Troubleshooting

## Cannot Access Website

Check:

```bash
ping website.com
```

---

## DNS Issue

Check:

```bash
nslookup website.com
```

---

## Port Not Open

Check:

```bash
ss -tulpn
```

---

## HTTPS Failure

Check:

```text
TLS Certificate
```

---

## Server Not Reachable

Check:

```text
Firewall
Security Groups
Network ACLs
```

---

# Chapter 25: Why Networking Matters In Cloud & DevOps

Everything depends on networking:

```text
Docker
Kubernetes
AWS
Terraform
Nginx
GitHub
Jenkins
```

Understanding networking makes troubleshooting significantly easier.

---

# 🔥 Interview Questions

### What Is An IP Address?

A unique address assigned to devices on a network.

---

### Difference Between Public And Private IP?

Public IP is internet accessible.

Private IP is internal only.

---

### What Is A Port?

A logical endpoint used by applications for communication.

---

### What Is TCP?

A reliable transport protocol that guarantees delivery.

---

### Explain TCP 3-Way Handshake.

```text
SYN
 ↓
SYN ACK
 ↓
ACK
```

Used to establish a TCP connection.

---

### Difference Between TCP And UDP?

TCP is reliable.

UDP is faster but does not guarantee delivery.

---

### What Is DNS?

DNS converts domain names into IP addresses.

---

### What Is NAT?

Network Address Translation converts private addresses into public addresses.

---

### What Is A Firewall?

A security mechanism that controls network traffic.

---

### What Is A Load Balancer?

A service that distributes incoming traffic across multiple servers.

---

### What Is CIDR?

A notation used to define IP address ranges.

---

# Mental Model

```text
User
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
Nginx
 ↓
Application
 ↓
Database
```

---

# One-Line Summary

Networking is the foundation of cloud, DevOps, Kubernetes, and distributed systems, enabling secure and reliable communication between users, applications, services, and infrastructure.
