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
**pwn.college{wSGt1c-flZFXfMK80Xye1iJQ0fz.QXwEjN0wCO1EzNzEzW}**

To solve this challenge, I first launched /challenge/run to begin the 8 rounds. I used the chmod command for all the 8 rounds according to what they gave. After that when i got the permission to chmod /flag, i made it readable, writeable, and executable to everyone by using "chmod a+rwx /flag". I then read the flag using cat command.

```
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-rw-r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g+w /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": rw-rw-r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-rwxr--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g+x /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": rw-rwxr--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwxrwxr-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod uo+x /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": rwxrwxr-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwx---r-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g-rwx /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": rwx---r-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -wx---r-x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u-r /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": -wx---r-x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -wx-w-r-x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g+w /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": -wx-w-r-x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -wx-w-r--
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o-x /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": -wx-w-r--
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wx-wxr--
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g+x /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod a+rwx /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{wSGt1c-flZFXfMK80Xye1iJQ0fz.QXwEjN0wCO1EzNzEzW}
```

## What I learnt
I learned how to use the chmod command efficienty.  

## References
The instructions of the pwn.college helped me solve the challenge.

# 7. Permissions Setting Practice
In this challenge, they told it is like the previous challenge, but it will request more radical permission changes, which we will need "=" and "," "-" chaining to achieve.

## My solve
**pwn.college{YAE5B7h7yu7-nGkDDQInK_uVn0E.QXzETO0wCO1EzNzEzW}**

Like the previous challenge, I first ran /challenge/run to start the rounds. I then used chmod to solve the rounds but this time with "=" and "," to completely overwrite the old permissions with the new ones. After the 8 rounds were done, I changed the permissions of the flag file to let anyone read, write, or execute it. I then read the /flag file using cat command. 

```
hacker@permissions~permissions-setting-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -w-rwx---
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=rwx,o=x /challenge/pwn
NEEDED, BUT UNMET permissions of "/challenge/pwn": -w-rwx---
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

CURRENT, INCORRECT permissions of "/challenge/pwn": rwxrwx--x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

You set the permissions incorrectly! Restarting the game!
hacker@permissions~permissions-setting-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -w-rwx---
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=w,g=rwx,o= /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": -w-rwx---
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wxrw-r--
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=wx,g=rw,o=r /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": -wxrw-r--
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r--r-x-w-
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=rx,o=w /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": r--r-x-w-
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wx-w---x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=wx,g=w,o=x /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": -wx-w---x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwxrwx--x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=rwx,o=x /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": rwxrwx--x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --xrw--w-
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=x,g=rw,o=w /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": --xrw--w-
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r--rw-r-x
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=rw,o=rx /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": r--rw-r-x
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -wxr----x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=wx,g=r,o=x /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod a+rwx /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{YAE5B7h7yu7-nGkDDQInK_uVn0E.QXzETO0wCO1EzNzEzW}
```

## What I learnt
I learned that with chmod, we can also overwrite the old permissions with the new ones by using "=" and ",". For example: "chmod u=rw,g=r FILENAME" will set the user permissions to read and write, and the group permissions to read-only. We can also remove all the permissions by keeping "-" after "=". For example: "chmod u=rw,g=r,o=- FILENAME" will set the user permissions to read and write, the group permissions to read-only, and the world permissions to nothing at all.

## References
The instructions of the pwn.college helped me solve the challenge.

# 8. The SUID Bit
In this challenge, they told we have to add the SUID bit to the /challenge/getroot program. If we do this, root shell will spawn and we can read the flag directly using cat command. 

## My solve
**pwn.college{EPjBu5P6nZgnEnW1mGkf-ENTMgP.QXzEjN0wCO1EzNzEzW}**

To solve this challenge, I used the chmod command and "u+s" to add the SUID bit to /challenge/getroot, then i ran /challenge/getroot. After the root shell opened, i read the flag file using cat command. 

```
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root!
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{EPjBu5P6nZgnEnW1mGkf-ENTMgP.QXzEjN0wCO1EzNzEzW}
```

## What I learnt
I learned that with set user id (SUID), a user can run a program as the owner of that program's file. As the owner of a file, you can set a file's SUID bit by using chmod: "chmod u+s FILENAME". 

## References
The instructions of the pwn.college helped me solve the challenge.










