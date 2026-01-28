# Bandit Level 22 → Level 23 Writeup

## Objective
Retrieve the password for **bandit23** by understanding how a cron job dynamically generates a filename using hashing.

---

## Step 1: Inspect Cron Jobs
First, list the cron jobs to find the one related to bandit23.

```bash
bandit22@bandit:~$ ls -la /etc/cron.d
```

### Observation
The file `cronjob_bandit23` looks relevant.

---

## Step 2: Read the Cron Job Configuration
```bash
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
```

### Output
```text
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
```

This shows the script runs every minute as user **bandit23**.

---

## Step 3: Analyze the Cron Script
```bash
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
```

### Script Content
```bash
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
```

### Explanation
- `whoami` returns `bandit23`
- A string `I am user bandit23` is hashed using **MD5**
- The hash is used as a filename in `/tmp`
- The password is copied to that file

---

## Step 4: Recreate the Filename
Manually generate the same MD5 hash.

```bash
bandit22@bandit:~$ echo I am user bandit23 | md5sum | cut -d ' ' -f 1
```

### Output
```text
8ca319486bfbbc3663ea0fbe81326349
```

---

## Step 5: Read the Password File
```bash
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
```

### Output
```text
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```

---

## Final Answer
🎯 **Password for bandit23:**

```
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```

---

## Key Concept
This level demonstrates how **predictable hashing** and **cron jobs** can expose sensitive data.  
If the logic is known, dynamically generated filenames can still be guessed and accessed.
