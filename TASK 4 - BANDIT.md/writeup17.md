# Writeup 17

## Challenge Name
PORT SCANNING, SSL SERVICE IDENTIFICATION, AND SSH KEY AUTHENTICATION

---

## Objective
The objective of this level is to retrieve the credentials for the next Bandit level by:
- Scanning a range of ports on localhost
- Identifying the correct SSL-enabled service
- Submitting the current level password over SSL
- Extracting and using an SSH private key for authentication

---

## Port Scanning on Localhost
First, the ports in the range **31000–32000** were scanned to identify which services were listening.

### Command Used
```bash
nmap -p 31000-32000 localhost
```

### Output
```text
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown
```

### Observation
Five ports were open. Further interaction was required to identify which service provided the next credentials.

---

## Connecting to the SSL Service
Based on the challenge hint, SSL-enabled services were tested. The correct service was running on **port 31790**.

### Command Used
```bash
openssl s_client -quiet -connect localhost:31790
```

### Observation
- The server used a self-signed certificate.
- The SSL connection was established successfully.

---

## Submitting the Current Password
After the SSL connection was established, the password for **bandit16** was submitted.

### Input Provided
```text
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

### Output
```text
Correct!
-----BEGIN RSA PRIVATE KEY-----
...
-----END RSA PRIVATE KEY-----
```

### Observation
Instead of a password, the service returned an **RSA private SSH key** for the next level.

---

## Saving the SSH Private Key
Since write access to the home directory is restricted, a temporary working directory was created.

### Commands Used
```bash
cd /tmp
mktemp -d
cd /tmp/tmp.RmrQzdvCIC
nano sshkey17.private
```

The full RSA private key was pasted into the file and saved.

> Note: The nano warning about `.local/share/nano` can be ignored as it does not affect file saving in `/tmp`.

---

## Fixing File Permissions
SSH requires private keys to be readable only by the owner.

### Command Used
```bash
chmod 700 sshkey17.private
```

---

## Transferring the Key to the Local Machine
SSH connections from localhost are blocked, so the key was copied to the local machine.

### Command Used (on local machine)
```bash
scp -P 2220 bandit16@bandit.labs.overthewire.org:/tmp/tmp.RmrQzdvCIC/sshkey17.private .
```

---

## Logging in Using the SSH Key
After fixing permissions on the local machine, the private key was used to authenticate.

### Commands Used
```bash
chmod 700 sshkey17.private
ssh -i sshkey17.private bandit17@bandit.labs.overthewire.org -p 2220
```

---

## Result
Login was successful, and access to **Bandit Level 17** was obtained using SSH key-based authentication.

---

## Conclusion
This level demonstrated:
- Port scanning to discover services
- Identifying and interacting with SSL-enabled services
- Secure retrieval of credentials over SSL
- Proper handling and usage of SSH private keys

Key-based authentication was required instead of a traditional password.
