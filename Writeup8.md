# Writeup 8

## Challenge Name
FIND SPECIFIC WORD IN A LARGE FILE

---

## Objective
The objective of this level is to locate a specific word inside a large text file and extract the password associated with that word for the next Bandit level.

---

## Initial Access
Logged into the Bandit server as `bandit7` using SSH.

### Command Used
```bash
ssh -p 2220 bandit.labs.overthewire.org -l bandit7
```

### Observation
Login was successful and access to the Bandit Level 7 environment was obtained.

---

## Listing Files in Home Directory
Listed all files in the home directory to identify relevant files.

### Command Used
```bash
ls -al
```

### Output
```bash
total 4108
drwxr-xr-x   2 root    root       4096 Oct 14 09:26 .
drwxr-xr-x 150 root    root       4096 Oct 14 09:29 ..
-rw-r--r--   1 root    root        220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root    root       3851 Oct 14 09:19 .bashrc
-rw-r-----   1 bandit8 bandit7 4184396 Oct 14 09:26 data.txt
-rw-r--r--   1 root    root        807 Mar 31  2024 .profile
```

### Observation
A large file named `data.txt` was present. This file likely contained the required password.

---

## Searching for the Required Word
According to the challenge hint, the password was located next to the word **"millionth"** inside the file.

### Command Used
```bash
cat data.txt | grep millionth
```

### Output
```text
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

---

## Conclusion
The password for the next Bandit level was successfully obtained by:
- Identifying the relevant file
- Searching for a specific keyword using `grep`
- Extracting the corresponding password

This password can now be used to log in to **Bandit Level 8**.
