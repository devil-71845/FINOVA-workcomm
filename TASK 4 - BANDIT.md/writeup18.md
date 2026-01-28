# Bandit Level 17 → Level 18 Writeup

## Objective
Find the password for **bandit18** by comparing two files: `passwords.old` and `passwords.new`.

---

## Step 1: Compare files using `diff`
```bash
bandit17@bandit:~$ diff passwords.old passwords.new
```

Output:
```
42c42
< BMIOFKM7CRSLI97voLp3TD80NAq5exxk
---
> x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

This shows that line 42 is different in both files.

---

## Step 2: Find unique entries
```bash
bandit17@bandit:~$ sort passwords.old passwords.new | uniq -u
```

Output:
```
BMIOFKM7CRSLI97voLp3TD80NAq5exxk
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

These are the only lines that differ between the two files.

---

## Step 3: Identify the correct password
The correct password must be present in `passwords.new`.

```bash
bandit17@bandit:~$ cat passwords.new | grep x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

Output:
```
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

The other value is not present in `passwords.new`.

---

## Final Answer
Password for **bandit18**:
```
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

---

## Key Takeaway
This level demonstrates how tools like `diff`, `sort`, `uniq`, and `grep` can be combined to efficiently compare files and extract meaningful differences.
