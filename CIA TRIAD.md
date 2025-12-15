# CIA Triad and SSH Setup – Documentation

## Overview

This repository contains documentation for understanding the **CIA Triad** (Confidentiality, Integrity, Availability) and setting up a secure **SSH (Secure Shell)** connection to a client system. The purpose of this task is to learn basic cybersecurity principles and apply them practically using SSH, while documenting the process using Markdown files.

---

## What is SSH?

**SSH (Secure Shell)** is a network protocol that allows secure remote login and command execution on another computer over an unsecured network. It is widely used by system administrators and developers to manage servers safely.

SSH provides:
- Encrypted communication
- Secure authentication
- Protection against eavesdropping and tampering

---

## SSH Setup and Connection Steps

### Step 1: Check if SSH is Installed

```bash
ssh -V
```

---

### Step 2: Generate SSH Key Pair (Optional but Recommended)

```bash
ssh-keygen
```

This creates:
- A private key (kept secret)
- A public key (shared with the server)

---

### Step 3: Connect to the Client

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

---

### Step 4: Verify Connection

```bash
whoami
pwd
```

---

## CIA Triad – Security Fundamentals

### Confidentiality
Ensures only authorized users can access information.

SSH encrypts data during transmission.

### Integrity
Ensures data is not altered during transmission.

SSH verifies data packets.

### Availability
Ensures systems are accessible when needed.

SSH allows reliable remote system access.

---

## How SSH Supports the CIA Triad

| Principle | Description |
|---------|-------------|
| Confidentiality | Encrypted communication |
| Integrity | Data protection |
| Availability | Reliable access |

---

## Conclusion

This documentation shows how SSH supports the CIA Triad in real-world secure communication.

---
