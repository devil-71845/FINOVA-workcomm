# Writeup 15

## Challenge Name
USING NETCAT TO SEND DATA TO A LOCAL SERVICE

---

## Objective
The objective of this level is to retrieve the password for the next Bandit level by sending the current level’s password to a service running locally on a specific port.

---

## Reading the Current Level Password
First, the password for `bandit14` was read from the system password file.

### Command Used
```bash
cat /etc/bandit_pass/bandit14
```

### Output
```text
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

---

## Connecting to the Local Service
A service was running on **localhost port 30000** that expects the correct password as input.  
The `nc` (netcat) command was used to connect to this service.

### Command Used
```bash
nc localhost 30000
```

### Input Provided
```text
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

### Output
```text
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

---

## Identifying the Password
After sending the correct password, the service responded with the password for the next level.

### Password Found
```text
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

---

## Conclusion
The password for the next Bandit level was successfully obtained by:
- Reading the current level password
- Connecting to a local network service using `netcat`
- Sending the password as input and receiving the response

This demonstrates how **network services** can accept input and return sensitive data when the correct information is provided.
