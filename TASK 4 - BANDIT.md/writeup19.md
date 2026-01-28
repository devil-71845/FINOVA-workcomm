# Bandit Level 18 → Level 19 Writeup

## Objective
Log in to **bandit18** and retrieve the password for **bandit19**.  
This level prevents interactive shell access, so commands must be executed directly over SSH.

---

## Understanding the Problem
When logging in normally, the session immediately exits. However, SSH allows running a **single command remotely** without opening an interactive shell.

This can be done by appending the command at the end of the SSH login command.

---

## Step 1: List Files Using SSH Command Execution
Instead of opening a shell, the `ls` command is executed directly.

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 ls
```

### Output
```text
readme
```

This confirms the presence of a file named `readme`.

---

## Step 2: Read the File Directly Over SSH
The `cat` command is executed remotely to read the contents of the file.

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
```

### Output
```text
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

---

## Final Answer
🎯 **Password for bandit19:**

```
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

---

## Key Concept
SSH can be used to execute individual commands remotely even when interactive login is restricted.  
This technique is useful when shells are disabled or immediately terminated.
