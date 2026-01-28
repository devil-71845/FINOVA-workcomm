# Bandit Level 20 → Level 21 Writeup

## Objective
Retrieve the password for **bandit21** by interacting with a setuid binary that communicates over a network socket.

---

## Understanding the Challenge
In this level, a setuid binary named `suconnect` runs as **bandit21**.  
It expects a connection on a specified port, reads the password for the current level, and if correct, returns the password for the next level.

---

## Step 1: Start a Local Listener Using Netcat
A listener is started on a local port that sends the current level password when a connection is made.

```bash
bandit20@bandit:~$ echo -n '0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO' | nc -l -p 1234 &
```

### Explanation
- `echo -n` sends the password without a newline
- `nc -l -p 1234` starts a listener on port 1234
- `&` runs the command in the background

---

## Step 2: Run the Setuid Program
The `suconnect` binary is executed and instructed to connect to the listening port.

```bash
bandit20@bandit:~$ ./suconnect 1234
```

---

## Step 3: Observe the Output
Once connected, the program reads the password and verifies it.

```text
Read: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
Password matches, sending next password
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

---

## Final Answer
🎯 **Password for bandit21:**

```
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

---

## Key Concept
This level demonstrates:
- Communication between processes using network sockets
- Use of `netcat` to simulate a network service
- How setuid binaries can securely exchange credentials over a local connection
