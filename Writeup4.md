# Name of the Challenge
 HIDDEN FILES
## Procedure and Process
 I just followed the description provided and used the secret password from bandit2 "MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx" to access bandit3 and after then,I used ls -al to display all the files and got to know about the inhere directory then I changed the directory to inhere by using cd inhere then with the help of " find . -type f -exec file {} + | grep ASCII " I got the idea how to extract the hidden file and opened the file and the contents in it and eventually got the password for the next level i.e for bandit 4
## Input
```bash
bandit3@bandit:~$ ls -al
total 24
drwxr-xr-x   3 root root 4096 Oct 14 09:26 .
drwxr-xr-x 150 root root 4096 Oct 14 09:29 ..
-rw-r--r--   1 root root  220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root root 3851 Oct 14 09:19 .bashrc
drwxr-xr-x   2 root root 4096 Oct 14 09:26 inhere
-rw-r--r--   1 root root  807 Mar 31  2024 .profile
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ find . -type f -exec file {} + | grep ASCII
./...Hiding-From-You: ASCII text
bandit3@bandit:~/inhere$ cat ./...Hiding-From-You
```

## Output
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

## Conclusion
 Now I must use the password I just got in bandit3 to log in into bandit4 and solve the next challenge
```