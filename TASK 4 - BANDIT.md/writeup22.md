# Bandit Level 21 → Level 22 Writeup

## Objective
Retrieve the password for **bandit22** by analyzing a cron job that periodically writes the password to a temporary file.

---

## Step 1: Inspect Cron Jobs
Cron jobs are scheduled tasks executed automatically by the system.  
All system-wide cron jobs are stored in `/etc/cron.d`.

```bash
bandit21@bandit:~$ ls -la /etc/cron.d
```

### Observation
Among the listed files, `cronjob_bandit22` is related to the next level.

---

## Step 2: Examine the Cron Script
The cron job executes a shell script located at `/usr/bin/cronjob_bandit22.sh`.

```bash
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
```

### Script Content
```bash
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

### Explanation
- The script copies the password for **bandit22** into a file inside `/tmp`.
- File permissions are set to `644`, making it readable by all users.

---

## Step 3: Read the Temporary File
Since the cron job runs automatically, the password file is already created and readable.

```bash
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

### Output
```text
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```

---

## Final Answer
🎯 **Password for bandit22:**

```
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```

---

## Key Concept
This level demonstrates how **cron jobs** can unintentionally expose sensitive data if file permissions are not properly restricted.  
Monitoring scheduled tasks is important for identifying such information leaks.
