# Writeup 11

## Challenge Name
DECODE BASE64 ENCODED FILE

---

## Objective
The objective of this level is to decode a **Base64 encoded text file** to retrieve the password for the next Bandit level.

---

## Viewing File Contents
First, the contents of the file were displayed to understand the type of data stored inside it.

### Command Used
```bash
cat data.txt
```

### Output
```text
VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
```

### Observation
The output appeared to be **Base64 encoded**, indicated by the character pattern and the trailing `==`.

---

## Decoding the File
The file was decoded using the `base64` command with the decode option.

### Command Used
```bash
base64 -d data.txt
```

### Output
```text
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

---

## Identifying the Password
From the decoded output, the password was extracted successfully.

### Password Found
```text
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

---

## Conclusion
The password for the next Bandit level was successfully obtained by:
- Identifying Base64 encoded content
- Decoding it using the `base64 -d` command
- Extracting the revealed password

This password can now be used to log in to **Bandit Level 11**.
