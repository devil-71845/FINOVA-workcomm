# Writeup 16

## Challenge Name
USING SSL/TLS CONNECTION WITH OPENSSL

---

## Objective
The objective of this level is to connect securely to a service running on **localhost port 30001** using SSL/TLS, send the current level password, and retrieve the password for the next Bandit level.

---

## Understanding the Service
Unlike the previous level which used plain `netcat`, this service requires an **encrypted SSL/TLS connection**.  
The `openssl s_client` command is used to establish such secure connections.

---

## Connecting to the SSL Service
An SSL connection was initiated to the local service running on port **30001**.

### Command Used
```bash
openssl s_client -connect localhost:30001
```

### Observation
- The connection was successfully established.
- A **self-signed certificate** was presented by the server.
- Despite the verification warning, the encrypted connection was usable.

---

## Sending the Current Password
Once the SSL connection was established, the password from the previous level was entered manually into the connection.

### Input Provided
```text
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

---

## Receiving the Response
After sending the correct password, the service responded with confirmation and provided the next level password.

### Output
```text
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

---

## Identifying the Password
The password for the next Bandit level is:

```text
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

---

## Conclusion
The challenge was successfully completed by:
- Recognizing the need for an SSL/TLS connection
- Using `openssl s_client` to establish a secure channel
- Sending the correct password through the encrypted connection

This level demonstrates how secure services require encrypted communication instead of plain text connections.
