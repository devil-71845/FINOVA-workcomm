# Writeup 9

## Challenge Name
DATA FILTERING

---

## Objective
The objective of this level is to find the **unique line** in a text file where all other lines are duplicated, and extract the password for the next Bandit level.

---

## Initial Observation
A file named `data.txt` was already present in the home directory of `bandit8`.  
The challenge hint indicated that the password appears **only once**, while all other lines appear multiple times.

---

## Identifying the Unique Line
To isolate the unique line, the file contents were:
1. Sorted alphabetically
2. Filtered to show only lines that appear **exactly once**

### Command Used
```bash
cat data.txt | sort | uniq -u
```

### Output
```text
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

---

## Conclusion
The password for the next Bandit level was successfully obtained by:
- Sorting the file contents
- Using `uniq -u` to extract the non-repeating line

This password can now be used to log in to **Bandit Level 9**.
