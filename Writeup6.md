# Writeup 6

## Challenge Name
FIND FILE WITH SPECIFIC SIZE

---

## Objective
The objective of this level is to locate a hidden file inside multiple directories that matches a **specific file size** and extract the password for the next Bandit level.

---

## Initial Access
Logged in as `bandit5` and listed all files in the home directory to understand the directory structure.

### Command Used
```bash
ls -al
```

### Output
```bash
total 24
drwxr-xr-x   3 root root    4096 Oct 14 09:26 .
drwxr-xr-x 150 root root    4096 Oct 14 09:29 ..
-rw-r--r--   1 root root     220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root root    3851 Oct 14 09:19 .bashrc
drwxr-x---  22 root bandit5 4096 Oct 14 09:26 inhere
-rw-r--r--   1 root root     807 Mar 31  2024 .profile
```

### Observation
An `inhere` directory was present, which likely contained the required files.

---

## Navigating to the Target Directory
Changed directory to `inhere` and listed its contents.

### Commands Used
```bash
cd inhere
ls -al
```

### Output
```bash
total 88
drwxr-x--- 22 root bandit5 4096 Oct 14 09:26 .
drwxr-xr-x  3 root root    4096 Oct 14 09:26 ..
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere00
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere01
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere02
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere03
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere04
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere05
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere06
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere07
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere08
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere09
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere10
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere11
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere12
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere13
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere14
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere15
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere16
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere17
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere18
drwxr-x---  2 root bandit5 4096 Oct 14 09:26 maybehere19
```

---

## Searching for the Required File
The challenge hinted that the correct file had a **size of exactly 1033 bytes**.

### Command Used
```bash
find . -size 1033c
```

### Output
```bash
./maybehere07/.file2
```

---

## Reading the File Contents
The contents of the identified file were displayed to obtain the password.

### Command Used
```bash
cat ./maybehere07/.file2
```

### Output
```text
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

---

## Conclusion
The password for the next Bandit level was successfully obtained by navigating nested directories and using the `find` command with a size filter.
