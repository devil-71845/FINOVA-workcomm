# Name of the Challenge
 FIND FILES WITH GIVEN SIZE/TYPE
## Procedure and Process
 I just followed the description provided and used the secret password from bandit3 "2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ" to access bandit4 and after then,I used ls -al to display all the files and got to know about the inhere directory then I changed the directory to inhere by using cd inhere then with the help of " find . -type f -exec file {} + | grep ASCII " I got the idea how to extract the hidden file and opened the file and the contents in it and eventually got the password for the next level i.e for bandit 5
## Input
```bash
bandit4@bandit:~$ ls -al
total 24
drwxr-xr-x   3 root root 4096 Oct 14 09:26 .
drwxr-xr-x 150 root root 4096 Oct 14 09:29 ..
-rw-r--r--   1 root root  220 Mar 31  2024 .bash_logout
-rw-r--r--   1 root root 3851 Oct 14 09:19 .bashrc
drwxr-xr-x   2 root root 4096 Oct 14 09:26 inhere
-rw-r--r--   1 root root  807 Mar 31  2024 .profile
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls -al
total 48
drwxr-xr-x 2 root    root    4096 Oct 14 09:26 .
drwxr-xr-x 3 root    root    4096 Oct 14 09:26 ..
-rw-r----- 1 bandit5 bandit4   33 Oct 14 09:26 -file00
-rw-r----- 1 bandit5 bandit4   33 Oct 14 09:26 -file01
-rw-r----- 1 bandit5 bandit4   33 Oct 14 09:26 -file02
-rw-r----- 1 bandit5 bandit4   33 Oct 14 09:26 -file03
-rw-r----- 1 bandit5 bandit4   33 Oct 14 09:26 -file04
-rw-r----- 1 bandit5 bandit4   33 Oct 14 09:26 -file05
-rw-r----- 1 bandit5 bandit4   33 Oct 14 09:26 -file06
-rw-r----- 1 bandit5 bandit4   33 Oct 14 09:26 -file07
-rw-r----- 1 bandit5 bandit4   33 Oct 14 09:26 -file08
-rw-r----- 1 bandit5 bandit4   33 Oct 14 09:26 -file09
bandit4@bandit:~/inhere$ find . -type f -exec file {} + | grep ASCII
./-file07: ASCII text
bandit4@bandit:~/inhere$ cat ./-file07
```

## Output
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

## Conclusion
 Now I must use the password I just got in bandit4 to log in into bandit5 and solve the next challenge
```