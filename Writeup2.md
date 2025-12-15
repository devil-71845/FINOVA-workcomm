# Name of the Challenge
 FIND A FILE
## Procedure and Process
 I just followed the description provided and used the secret password from bandit0 "ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If" to access bandit1 and after then,I used ls -al to display all the files and then I got to know about the - file and used cat function required for the - file in proper way to read the contents in it and eventually got the password for the next level i.e for bandit 2
## Input
```bash
bandit1@bandit:~$ ls -al
total 24
-rw-r-----   1 bandit2 bandit1   33 Oct 14 09:26 -
drwxr-xr-x   2 root    root    4096 Oct 14 09:26 .
drwxr-xr-x 150 root    root    4096 Oct 14 09:29 ..
-rw-r--r--   1 root    root     220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root    root    3851 Oct 14 09:19 .bashrc
-rw-r--r--   1 root    root     807 Mar 31  2024 .profile
bandit1@bandit:~$ cat ./-
```

## Output
263JGJPfgU6LtdEvgfWU1XP5yac29mFx

## Conclusion
 Now I must use the password I just got in bandit1 to log in into bandit2 and solve the next challenge
```