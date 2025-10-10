# 1. Changing file ownership
In this challenge, we are to change the ownership of the /flag file to our username, that is hacker in pwn.college using chown command and then read the flag from that file. 

## My solve
**pwn.college{ED0cDkBR8txmB8heviwgAs3JyqK.QXxEjN0wCO1EzNzEzW}**

To solve this challenge, I first used the chown command and changed the owner of /flag file to hacker from root. Then I read it using cat command and get the flag.

```
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{ED0cDkBR8txmB8heviwgAs3JyqK.QXxEjN0wCO1EzNzEzW}
```

## What I learnt
I learned about the chown command, which is used to change the ownership of a file from one user to another. Generally, we need to be root to use this command. We can also check the permissions of a file or directory using ls -l.

## References
The instructions of the pwn.college helped me solve the challenge.

# 2. Groups and files
In this challenge, we are to change the group ownership of the /flag file to whatever group the user is in, and then read the file for the flag. They told that the flag is readable by whatever group owns it. They also told that it is possible in this challenge to invoke chgrp as the hacker user.

## My solve
**pwn.college{0plqRzr7fn6Tps9VXaWZspQP8Lu.QXxcjM1wCO1EzNzEzW}**

To solve this challenge, I first used the id command to see what groups we are in. I then used the chgrp command to change the group ownership of /flag file to hacker group from root. I then read the file using cat command to get the flag.

```
hacker@permissions~groups-and-files:~$ id
uid=1000(hacker) gid=1000(hacker) groups=1000(hacker)
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{0plqRzr7fn6Tps9VXaWZspQP8Lu.QXxcjM1wCO1EzNzEzW}
```

## What I learnt
I learned about the chgrp command, which is used to change the group ownership of a file. syntax: chgrp "group name" "file name". I also learned that we can check what groups you are part of with the id command. 

## References
The instructions of the pwn.college helped me solve the challenge.

# 3. Fun with group names
In this challenge, they told that they have randomized the name of the group that your user is in. Like the previous level, we have to use the id command to figure that name out, then use chgrp and access /flag file.

## My solve
**pwn.college{sr7zttuWZ2BfcIcpN-Qlpb8fH6p.QXycjM1wCO1EzNzEzW}**

To solve this challenge,

```
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp19929) groups=1000(grp19929)
hacker@permissions~fun-with-groups-names:~$ chgrp grp19929 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{sr7zttuWZ2BfcIcpN-Qlpb8fH6p.QXycjM1wCO1EzNzEzW}
```

## What I learnt
I have learnt when and how to use the chgrp command.

## References
The instructions of the pwn.college helped me solve the challenge.

# 4. Changing permissions
In this challenge, we are to change the permissions of the flag file and then read it to get the flag. 

## My solve
**pwn.college{klrfleh-uaob2E7ptcViQaeHzdC.QXzcjM1wCO1EzNzEzW}**

To solve this challenge, I used the chmod command with o+r as argument, so that other users will get access to read the flag file. I then read the flag file using cat command. 

```
hacker@permissions~changing-permissions:~$ chmod o+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{klrfleh-uaob2E7ptcViQaeHzdC.QXzcjM1wCO1EzNzEzW}
```

## What I learnt
I learned how we can change permissions of a file using chmod command. 

r - user/group/other can read the file (or list the directory)

w - user/group/other can modify the files (or create/delete files in the directory)

x - user/group/other can execute the file as a program (or can enter the directory, e.g., using `cd`)

"-" - nothing 

u+r, as above, adds read access to the user's permissions

g+wx adds write and execute access to the group's permissions

o-w removes write access for other users

a-rwx removes all permissions for the user, group, and world

## References
The instructions of the pwn.college helped me solve the challenge.

# 5. Executable files
In this challenge, we are to first make /challenge/run executable, then execute it to get the flag.

## My solve
**pwn.college{gXanva4oAzmW1A5kUyMy5dQR1ay.QXyEjN0wCO1EzNzEzW}**

To solve this challenge, I used the chmod command with o+x as argument, and then tried running the program, but it did not work. So I again used chmod but this time with a+x as argument, then ran the program and got the flag.  

```
hacker@permissions~executable-files:~$ chmod o+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
bash: /challenge/run: Permission denied
hacker@permissions~executable-files:~$ chmod a+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{gXanva4oAzmW1A5kUyMy5dQR1ay.QXyEjN0wCO1EzNzEzW}
```

## What I learnt
I learnt that we can change the executable permissions of a program with chmod.

## References
The instructions of the pwn.college helped me solve the challenge.

# 6. Permission tweaking practice
In this challenge, it is told that this challenge will ask us to change the permissions of the /challenge/pwn file in specific ways a few times in a row. If we get the permissions wrong, the game will reset and we can try again. If we get the permissions right eight times in a row, the challenge will let us chmod /flag to make it readable for ourselves. They told us to launch /challenge/run to start the challenge.

## My solve
**

To solve this challenge, 

```

```

## What I learnt


## References
The instructions of the pwn.college helped me solve the challenge.






