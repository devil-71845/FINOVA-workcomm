# Name of the Challenge
 SSH BASICS
## Procedure and Process
 I just followed the basics of opening in ssh by entering the secret password bandit0 and after then,I used ls -al to display all the files and then I got to know about the readme file and used cat function for the readme file to read the contents in it and eventually got the password for the next level
## Input
```bash
bandit0@bandit:~$ ls -al
total 24
drwxr-xr-x   2 root    root    4096 Oct 14 09:26 .
drwxr-xr-x 150 root    root    4096 Oct 14 09:29 ..
-rw-r--r--   1 root    root     220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root    root    3851 Oct 14 09:19 .bashrc
-rw-r--r--   1 root    root     807 Mar 31  2024 .profile
-rw-r-----   1 bandit1 bandit0  438 Oct 14 09:26 readme
bandit0@bandit:~$ cat readme
output:Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walkthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!

The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
 
## Conclusion
 Now I must use the password I just got in bandit0 to log in into bandit1 and solve the next challenge


```