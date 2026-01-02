# Writeup 7

## Challenge Name
FIND PERMISSION AND OWNERSHIP

---

## Objective
The objective of this level is to locate a file anywhere in the system that:
- Is owned by user `bandit7`
- Belongs to group `bandit6`
- Has an exact size of **33 bytes**
and then extract the password for the next Bandit level.

---

## Searching the Entire File System
Since the file location was unknown, a recursive search from the root directory (`/`) was required using the `find` command with multiple filters.

### Command Used
```bash
find / -user bandit7 -group bandit6 -size 33c
```

### Output
```bash
/var/lib/dpkg/info/bandit7.password
```
*(Several “Permission denied” messages appeared during the search, which is expected when scanning protected system directories.)*

---

## Reading the Password File
After locating the correct file, its contents were displayed to retrieve the password.

### Command Used
```bash
cat /var/lib/dpkg/info/bandit7.password
```

### Output
```text
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

---

## Conclusion
The password for the next Bandit level was successfully obtained by:
- Performing a system-wide search
- Filtering files based on **user**, **group**, and **size**
- Ignoring expected permission errors during traversal

This password can now be used to log in to **Bandit Level 7**.
