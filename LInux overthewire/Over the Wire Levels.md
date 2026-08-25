 ssh -p 2220 bandit8@bandit.labs.overthewire.org


Level0-1

username: bandit1,
ssh to port 2220
password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

Level1-2
username: bandit1,
Goal: stored in a file called "-located" in the home directory
Commands: ls , cd , cat , file , du , find
Solution: to open "- file need to use command: cat ./-"
password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx


Level2-3
username: bandit2
Goal:The password for the next level is stored in a file called --spaces in this filename-- located in the home directory,
solution: same command like earlier
Password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

Level3-4
username: bandit3
Password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
The password for the next level is stored in a hidden file in the inhere directory.
solution: ls -la and same as above
password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

Level4-5
username: bandit4
password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
Goal: The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.
Password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

Level5-6
username: bandit5
password:4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
Goal: The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

    human-readable
    1033 bytes in size
    not executable
Soluiton: used ls -R -la to display all the files in the folders and checked the size of the file ..in future might have use find command to find the size of the file
password: 
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

Level6-7
username: bandit6
password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
Goal: The password for the next level is stored somewhere on the server and has all of the following properties:

    owned by user bandit7
    owned by group bandit6
    33 bytes in size

Solution: find / -user bandit7 -exec ls -l {} \;
Result: bandit7 bandit6 33 Oct 14 09:26 /var/lib/dpkg/info/bandit7.password

Password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

Level7-8
username: bandit7
password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
Goal:The password for the next level is stored in the file data.txt next to the word millionth

solution: used grep in the file to extract exact match of millionth 
        example: cat filename.txt | grep "-millionth"
result:
password:dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

level8-9
username: bandit8
password:dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
Goal: The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

Solution:sort data.txt | uniq -u
password:4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

level 9-10
Username:bandit9
password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
Goal:The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.
Solution:



Password:FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

Level10-11


username: bandit10
password:FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

Goal:

Solution:

Password:dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

level 11-12
username: bandit11
password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
goal:

solution:ROT13 from cyber chef

password:7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

level 12-13
username:bandit12
password:7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
goal:
solution: first covert to binary, check file type, then convert file to gz or bzip2 and unzip it
password:FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

Level 13-14
username: bandit13
password: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

goal:The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Look at the commands that logged you into previous bandit levels, and find out how to use the key for this level
solution:

solution: save the private key in a file and change permission to 600. Then ssh -p2220 -i path-of-file bandit14@bandit.labs.overthewire.org

Level 14-15
username: bandit14
password: saved private key in previous session
goal: The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

solution: found the password at /etc/bandit_pass/banit14: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS. submit this to port 30000 to get password for next level used telnet localhost 30000 and pasted the password

Password: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

Level 15-16
username: bandit15
password: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
goal: The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL/TLS encryption.

solution: same method like previous but user openssl s_client -connect localhost:30001
password: kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

Level 16-17
username: bandit16
password: kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

Goal: The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

Solution: use -quiet in the end of the command to get the password and save the key use chmod 400 then connect like previous

Level 17-18
username: bandit17
password: see previous solution

Goal:
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**

Solution: used diff and first one is the password: x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO



level 18-19
username: bandit18
password from previous and use -t and "/bin/sh" in the end because someone has modified 

goal:The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.
solution: use above to log you in then cat the readme file

password: cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8


Level 19-20
username: bandit19
password: cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8

goal:To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary
solution:
password: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO


level 20 -21
user: bandit20
pass: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO

Goal: There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

solution: user two teminals, on one execute "nc -nlvp 12345"(some random port) and paste the password on current level, then on another terminal execute "./suconnect 12345" this will show the password
password:EeoULMCra2q0dSkYj561DX7s1CpBuOBt

level 21-22
user: bandit21
pass: EeoULMCra2q0dSkYj561DX7s1CpBuOBt

Goal: A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.
Solution: we can see that there is a .sh file running in con.d for bandit 22 and following those path will give u the password. use cat to display

Password: tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q

level 22-23
user: bandit 22
pass: tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q

Goal: A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

solution: create a folder in tmp directory and copy the content in the .sh file into the new file in the tmp directory and modify this new file to bandit 23 where the name says then exxecute that gives password

Password: 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

level 23-24
user: bandit 23
pass: 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

Goal: A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

Solution: In this module, it executes and deletes all the file. open the script file which is in cron job then navigate to the path in the script and execute "echo "cat /etc/bandit_pass/bandit24 > /tmp/passd244 " > fil.sh "

Password:gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

Level 24  -25
user: bandit24
pass: gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

Goal: A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time

Solution:

Password: 

