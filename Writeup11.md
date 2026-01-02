# Writeup 11

## Challenge Name
BASIC DECODING

---

## Objective
The objective of this level is to decode a **Base64 encoded file** in order to extract the password for the next Bandit level.

---

## Listing Files in Home Directory
Listed all files in the home directory of `bandit10` to identify the relevant file.

### Command Used
```bash
ls -al
```

### Output
```bash
total 24
drwxr-xr-x   2 root     root     4096 Oct 14 09:25 .
drwxr-xr-x 150 root     root     4096 Oct 14 09:29 ..
-rw-r--r--   1 root     root      220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root     root     3851 Oct 14 09:19 .bashrc
-rw-r-----   1 bandit11 bandit10   69 Oct 14 09:25 data.txt
-rw-r--r--   1 root     root      807 Mar 31  2024 .profile
```

### Observation
A small file named `data.txt` was present. The challenge hinted that the contents were **Base64 encoded**.

---

## Decoding the File Contents
The `base64` command was used with the `--decode` option to decode the file and reveal the hidden password.

### Command Used
```bash
cat data.txt | base64 --decode
```

### Output
```text
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

---

## Identifying the Password
From the decoded output, the password was extracted.

### Password Found
```text
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

---

## Conclusion
The password for the next Bandit level was successfully obtained by:
- Identifying Base64 encoded data
- Decoding it using the `base64 --decode` command
- Extracting the revealed password

This password can now be used to log in to **Bandit Level 11**.
