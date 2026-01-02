# Writeup 10

## Challenge Name
FILE INSPECTION

---

## Objective
The objective of this level is to extract a **human-readable password** from a file that contains mostly non-printable characters by filtering readable strings and identifying the correct password.

---

## Listing Files in Home Directory
Listed all files in the home directory of `bandit9` to identify the relevant data file.

### Command Used
```bash
ls -al
```

### Output
```bash
total 40
drwxr-xr-x   2 root     root     4096 Oct 14 09:25 .
drwxr-xr-x 150 root     root     4096 Oct 14 09:29 ..
-rw-r--r--   1 root     root      220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root     root     3851 Oct 14 09:19 .bashrc
-rw-r-----   1 bandit10 bandit9 19382 Oct 14 09:25 data.txt
-rw-r--r--   1 root     root      807 Mar 31  2024 .profile
```

### Observation
A file named `data.txt` was present. The challenge hint suggested that the password was hidden among readable strings inside this file.

---

## Extracting Human-Readable Strings
The `strings` command was used to extract readable text from the file.  
The output was then filtered using `grep` to find lines containing the `=` character, which helped narrow down the password.

### Command Used
```bash
strings data.txt | grep =
```

### Output
```text
FB`=
c\5D=
========== the
?/=l
=Uc1
=vG*2P
========== password
k=ezG
E========== is
=%r_
.?=Dm
O&A=n
5========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
=*^Y
=L3jT
q<=,
'QHE=
+=NBf
```

---

## Identifying the Password
From the filtered output, the line containing the actual password was clearly visible after the text **"password is"**.

### Password Found
```text
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

---

## Conclusion
The password for the next Bandit level was successfully obtained by:
- Extracting human-readable strings from a binary file
- Filtering relevant lines using `grep`
- Identifying the password embedded in readable text

This password can now be used to log in to **Bandit Level 10**.
