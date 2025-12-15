# Task 1

## Name of the Challenge
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

---

# Task 2

## Name of the Challenge
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

---

# Task 3

## Name of the Challenge
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

---

# Task 4

## Name of the Challenge
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

---

# Task 5

## Name of the Challenge
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

---
