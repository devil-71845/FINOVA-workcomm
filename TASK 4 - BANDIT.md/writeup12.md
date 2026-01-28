# Writeup 12

## Challenge Name
DECODE ROT13 ENCODED TEXT

---

## Objective
The objective of this level is to decode text that has been encrypted using the **ROT13 substitution cipher** in order to obtain the password for the next Bandit level.

---

## Viewing the Encoded File
The contents of the file were displayed and piped through a character translation command to decode the encrypted text.

### Command Used
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

### Output
```text
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

---

## Explanation
ROT13 works by shifting each alphabetical character **13 positions forward** in the alphabet.  
The `tr` command performs this translation by mapping:
- `A-Z` → `N-ZA-M`
- `a-z` → `n-za-m`

This effectively reverses the ROT13 encoding.

---

## Identifying the Password
From the decoded output, the password was extracted.

### Password Found
```text
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

---

## Conclusion
The password for the next Bandit level was successfully obtained by:
- Recognizing ROT13 encoded text
- Decoding it using the `tr` command
- Extracting the revealed password

This password can now be used to log in to **Bandit Level 12**.
