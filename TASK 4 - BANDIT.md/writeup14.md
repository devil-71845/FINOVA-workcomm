# Writeup 14

## Challenge Name
SSH LOGIN USING PRIVATE KEY AUTHENTICATION

---

## Objective
The objective of this level is to log in to the next Bandit level using **SSH public-key authentication** instead of a password by transferring and using a private SSH key securely.

---

## Identifying the Private Key
After logging in as `bandit13`, the contents of the home directory were listed to identify useful files.

### Command Used
```bash
ls
```

### Output
```text
sshkey.private
```

### Observation
A private SSH key named `sshkey.private` was present. This key can be used to authenticate as the next user.

---

## Copying the Private Key to Local Machine
The private key was copied from the remote Bandit server to the local machine using `scp`, which transfers files securely over SSH.

### Command Used (on local machine)
```bash
scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .
```

---

## Fixing File Permissions
SSH requires private keys to be readable **only by the owner**. The key initially had permissions that were too open, so they were restricted.

### Command Used
```bash
chmod 700 sshkey.private
```

---

## Logging in Using the Private Key
After fixing permissions, the private key was used to log in to the next Bandit level.

### Command Used
```bash
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```

---

## Result
Login was successful, and access to **Bandit Level 14** was obtained.

---

## Conclusion
The challenge was solved by securely transferring a private SSH key, fixing its permissions, and authenticating using SSH key-based login. This demonstrates the use of **public-key cryptography** as a secure alternative to passwords.
