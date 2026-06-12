# 🔐 19-Security-Fundamentals.md

# Security Fundamentals

## Encryption, Hashing, SSH, SSL/TLS, Public Keys, Certificates, JWT, OAuth & Secrets Management

> Modern DevOps is not just about automation.
>
> It is about secure automation.
>
> Every cloud platform, CI/CD pipeline, Kubernetes cluster, Linux server, and production application relies on security fundamentals.

---

# 📚 Table of Contents

1. What is Security?
2. CIA Triad
3. Authentication vs Authorization
4. Encryption
5. Symmetric Encryption
6. Asymmetric Encryption
7. Public Key & Private Key
8. Hashing
9. Digital Signatures
10. SSL & TLS
11. HTTPS
12. Certificates
13. SSH
14. JWT
15. OAuth
16. Multi-Factor Authentication
17. Secrets Management
18. HashiCorp Vault
19. Security in DevOps
20. Production Security Best Practices
21. Interview Questions

---

# Chapter 1: What is Security?

Security means:

```text
Protecting
Systems
Applications
Networks
Data
```

from:

```text
Unauthorized Access
Attacks
Data Theft
Modification
```

---

Goal:

```text
Confidentiality
Integrity
Availability
```

---

# Chapter 2: CIA Triad

Foundation of cybersecurity.

---

## Confidentiality

Only authorized users can access data.

Example:

```text
Bank Account Password
```

---

## Integrity

Data should not be modified without authorization.

Example:

```text
Financial Records
```

---

## Availability

Systems should remain accessible.

Example:

```text
Google Available 24/7
```

---

Easy Memory:

```text
CIA

C → Confidentiality

I → Integrity

A → Availability
```

---

# Chapter 3: Authentication vs Authorization

## Authentication

Verifies:

```text
Who Are You?
```

Example:

```text
Username + Password
```

---

## Authorization

Determines:

```text
What Can You Access?
```

---

Example:

```text
Admin
Can Delete Users

Normal User
Cannot
```

---

Easy Memory:

```text
Authentication
      =
Identity

Authorization
      =
Permissions
```

---

# Chapter 4: Encryption

Encryption converts:

```text
Readable Data
```

into:

```text
Unreadable Data
```

---

Example:

```text
Hello
```

becomes:

```text
XJ82H3Q
```

---

Purpose:

```text
Protect Data
```

during storage and transmission.

---

# Chapter 5: Symmetric Encryption

Uses:

```text
One Key
```

for:

```text
Encryption
Decryption
```

---

Example:

```text
Key
 ↓
Encrypt

Same Key
 ↓
Decrypt
```

---

Advantages:

```text
Fast
Efficient
```

---

Examples:

```text
AES
DES
```

---

# Chapter 6: Asymmetric Encryption

Uses:

```text
Two Keys
```

---

Keys:

```text
Public Key
Private Key
```

---

Architecture:

```text
Public Key
      ↓
Encrypt
      ↓
Private Key
      ↓
Decrypt
```

---

Examples:

```text
RSA
ECC
```

---

# Chapter 7: Public Key & Private Key

One of the most important DevOps interview topics.

---

## Public Key

Can be shared with everyone.

---

## Private Key

Must remain secret.

---

Example:

```text
Public Key
 ↓
Encrypt Message
 ↓
Private Key
 ↓
Decrypt Message
```

---

Used In:

```text
HTTPS
SSH
Certificates
VPN
Cloud Security
```

---

Think:

```text
Public Key
   =
Open Padlock

Private Key
   =
Key To Open Padlock
```

---

# Chapter 8: Hashing

Hashing converts data into a fixed-length value.

---

Example:

```text
password123
```

becomes:

```text
482c811da5d5b4bc...
```

---

Properties:

```text
One Way
Fixed Length
Deterministic
```

---

Used For:

```text
Password Storage
File Verification
Integrity Checks
```

---

Popular Algorithms:

```text
SHA256
SHA512
bcrypt
```

---

# Chapter 9: Digital Signatures

Purpose:

```text
Verify Identity
Verify Integrity
```

---

Flow:

```text
Hash
 ↓
Sign With Private Key
 ↓
Verify With Public Key
```

---

Used In:

```text
Software Signing
Certificates
Secure Updates
```

---

# Chapter 10: SSL & TLS

SSL:

```text
Secure Sockets Layer
```

Older technology.

---

TLS:

```text
Transport Layer Security
```

Modern replacement.

---

Purpose:

```text
Encrypt Communication
```

---

Example:

```text
Browser
 ↓
TLS
 ↓
Server
```

---

# Chapter 11: HTTPS

HTTPS:

```text
HTTP + TLS
```

---

Flow:

```text
Browser
 ↓
Certificate Validation
 ↓
TLS Handshake
 ↓
Encrypted Communication
```

---

Benefits:

```text
Privacy
Integrity
Authentication
```

---

# Chapter 12: Certificates

Certificates prove:

```text
Website Identity
```

---

Issued By:

```text
Certificate Authorities
```

Examples:

```text
Let's Encrypt
DigiCert
GlobalSign
```

---

Certificate Contains:

```text
Domain
Public Key
Expiration Date
Issuer
```

---

# Chapter 13: SSH

SSH:

```text
Secure Shell
```

---

Used For:

```text
Remote Login
Server Management
File Transfer
```

---

Connection:

```text
Laptop
   ↓
SSH
   ↓
Linux Server
```

---

Generate Key:

```bash
ssh-keygen
```

---

Connect:

```bash
ssh user@server-ip
```

---

### How SSH Works

```text
Private Key
      ↓
Authentication
      ↓
Public Key On Server
      ↓
Access Granted
```

---

Interview Favorite:

```text
SSH Uses Public/Private Key Cryptography
```

---

# Chapter 14: JWT

JWT:

```text
JSON Web Token
```

---

Used For:

```text
Authentication
Authorization
```

---

Structure:

```text
Header
Payload
Signature
```

---

Flow:

```text
Login
 ↓
JWT Issued
 ↓
Request
 ↓
JWT Verified
```

---

Common In:

```text
Microservices
APIs
Cloud Applications
```

---

# Chapter 15: OAuth

OAuth allows:

```text
Third-Party Login
```

---

Example:

```text
Login With Google
Login With GitHub
```

---

Flow:

```text
User
 ↓
Google
 ↓
Authorization Token
 ↓
Application
```

---

# Chapter 16: Multi-Factor Authentication (MFA)

Uses multiple verification methods.

---

Example:

```text
Password
 +
OTP
```

---

Benefits:

```text
Additional Security Layer
```

---

Common Factors:

```text
Password
Phone
Biometrics
```

---

# Chapter 17: Secrets Management

Secrets:

```text
Passwords
API Keys
Tokens
Certificates
```

---

Bad:

```yaml
password: admin123
```

---

Good:

```text
Store Securely
Retrieve Dynamically
```

---

# Chapter 18: HashiCorp Vault

Vault is used to manage:

```text
Secrets
Certificates
Tokens
Encryption Keys
```

---

Benefits:

```text
Centralized Security
Rotation
Auditing
```

---

Used In:

```text
Kubernetes
AWS
Terraform
CI/CD Pipelines
```

---

# Chapter 19: Security In DevOps

Security should be everywhere.

---

Examples:

```text
Secure Git Repositories
Encrypted Secrets
TLS Everywhere
Least Privilege Access
Automated Security Scanning
```

---

Often Called:

```text
DevSecOps
```

---

# Chapter 20: Production Security Best Practices

Always:

```text
Use HTTPS
Enable MFA
Rotate Secrets
Patch Systems
Use IAM Roles
Use Least Privilege
Monitor Logs
```

---

Avoid:

```text
Hardcoded Passwords
Shared Accounts
Open Firewalls
Public Databases
```

---

# Chapter 21: Why Security Matters In DevOps

Everything depends on security:

```text
GitHub
AWS
Terraform
Kubernetes
Docker
Jenkins
Linux
```

Without security:

```text
Automation
Can Become
Automated Vulnerability
```

---

# 🔥 Interview Questions

### What Is Encryption?

Converting readable data into unreadable data using cryptographic algorithms.

---

### Difference Between Encryption And Hashing?

Encryption:

```text
Reversible
```

Hashing:

```text
One Way
```

---

### Difference Between Public Key And Private Key?

Public Key encrypts data.

Private Key decrypts data.

---

### What Is TLS?

Transport Layer Security is the protocol used to secure communication over networks.

---

### What Is HTTPS?

HTTP secured using TLS encryption.

---

### What Is A Certificate?

A digital document that verifies the identity of a server or website.

---

### What Is SSH?

A secure protocol used to remotely access Linux systems.

---

### How Does SSH Work?

Uses public/private key cryptography to authenticate users securely.

---

### What Is JWT?

A token-based authentication mechanism used in web applications and APIs.

---

### What Is OAuth?

A framework that enables secure third-party authentication and authorization.

---

### What Is MFA?

Multi-Factor Authentication uses multiple verification methods to improve security.

---

### What Is Vault?

A secrets management system used to securely store and manage credentials, certificates, and tokens.

---

# Mental Model

```text
User
 ↓
Authentication
 ↓
Authorization
 ↓
Application
 ↓
TLS
 ↓
Server
 ↓
Encrypted Data
```

---

# Security Ecosystem

```text
SSH
      → Secure Server Access

TLS
      → Secure Communication

Certificates
      → Identity Verification

JWT
      → User Authentication

OAuth
      → Third-Party Login

Vault
      → Secrets Management

MFA
      → Additional Protection
```

---

# One-Line Summary

Security in DevOps is the practice of protecting systems, applications, infrastructure, and data using encryption, authentication, authorization, secrets management, and secure communication protocols throughout the software delivery lifecycle.
