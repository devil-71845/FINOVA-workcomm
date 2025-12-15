# Name of the Challenge
 SPACE IN FILENAMES
## Procedure and Process
 I just followed the description provided and used the secret password from bandit1 "263JGJPfgU6LtdEvgfWU1XP5yac29mFx" to access bandit2 and after then,I used ls -al to display all the files and then I got to know about the --spaces in this filename-- file and used cat function required for the --spaces in this filename-- file in proper way to read the contents in it and eventually got the password for the next level i.e for bandit 3
## Input
```bash
bandit2@bandit:~$ ls -al
total 24
drwxr-xr-x   2 root    root    4096 Oct 14 09:26 .
drwxr-xr-x 150 root    root    4096 Oct 14 09:29 ..
-rw-r--r--   1 root    root     220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root    root    3851 Oct 14 09:19 .bashrc
-rw-r--r--   1 root    root     807 Mar 31  2024 .profile
-rw-r-----   1 bandit3 bandit2   33 Oct 14 09:26 --spaces in this filename--
bandit2@bandit:~$ cat -- "--spaces in this filename--"
```

## Output
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

## Conclusion
 Now I must use the password I just got in bandit2 to log in into bandit3 and solve the next challenge
```