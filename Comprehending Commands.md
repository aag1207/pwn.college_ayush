# 1. cat: not the pet, but the command
This challenge deals with the cat command. It is one of the most critical linux commands used for reading out the files.

## My solve
**pwn.college{IS0oGiZJWk1uiu7WmdTGhh9-trK.QXxcTN0wCO1EzNzEzW}**

It was mentioned in the challenge that the required flag was copied into the flag file of the home directory. So, in order to read the flag file and retrieve the flag, cat flag was the program executed

```
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{IS0oGiZJWk1uiu7WmdTGhh9-trK.QXxcTN0wCO1EzNzEzW}
hacker@commands~cat-not-the-pet-but-the-command:~$
```

## What I leant
I learnt the use of the cat command. In order to read any file, the cat command is used.

## References
I have reffered to the video and the instructions mentioned to complete this challenge.

# 2. catting absolute paths
This challenge also deals with the cat command. In this case, the flag is not copied directly onto my home directory. We are to first change directory(cd) to the root directory and then execute cat flag.

## My flag
**pwn.college{kFcb9xO0XK1dSe5lF_fNucqNITj.QX5ETO0wCO1EzNzEzW}**

It was mentioned that this time, the flag wasn't directly copied onto my home directory. So, in order to read the flag folder, cat /flag(absolute path) was used.

```
hacker@commands~catting-absolute-paths:/home$ cat /flag
pwn.college{kFcb9xO0XK1dSe5lF_fNucqNITj.QX5ETO0wCO1EzNzEzW}
```

## What I learnt
I learnt how to use the cat command and the absolute path combined. 

## References
I have reffered to the video and the instructions mentioned to complete this challenge.

# 3. more catting practice
In this challenge, the flag is to be retrieved from a directory which isn't the home directory or a directory which is not given directly. Absolute paths are to be used.

## My flag
**pwn.college{ETpb5lrdlx5Mh8POQ-BewG7_fdc.QXwITO0wCO1EzNzEzW}**

To solve this challenge, I entered cat to read the absolute path '/lib/modprobe.d/flag' and retrieve the flag. The twist in this challenge is that the directory in which the flag file is stored wasn't directly mentioned. At the start, I did not see that the absolute path was mentioned, so I tried many ways to retrieve the flag. However, then I realized that the path was mentioned in the instructions of the terminal and I had to read it with the cat program to retrieve the flag.

```
hacker@commands~more-catting-practice:~$ cat /lib/modprobe.d/flag
pwn.college{ETpb5lrdlx5Mh8POQ-BewG7_fdc.QXwITO0wCO1EzNzEzW}
```

## What I learnt
I have now learnt how to retrieve a folder when the exact directory and location is not mentioned. I was to use an absolute path to find the solution.

## References
I have reffered to the video and the instructions mentioned to complete this challenge.


# 4. grepping for a needle in a haystack
In this challenge I explored the grep command. It is used to find a specific line(whose text is known) , in a lot of lines of a file(haystack). In case we need to find a line whose text we know in a bunch of lines of a file, the grep command is used.

## My flag
**pwn.college{AiIAHYO5ir65nDlx0z4lLgfJcFO.QX3EDO0wCO1EzNzEzW}**

To solve this challenge, I entered the grep command with the common text of the flag(pwn.college) followed by the file in which the search is to be done to retrieve the flag. It is to note that the text is to be mentioned first followed by a space and then the file in which the search is to be done.

```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{AiIAHYO5ir65nDlx0z4lLgfJcFO.QX3EDO0wCO1EzNzEzW}
```

## What I learnt
I have now learnt how to find a specific line whose text we know among a bunch of lines in a given file. The grep command can be used to efficiently locate the lines of need.

## Resources
I have reffered to the video and the instructions mentioned to complete this challenge.

# 5. Comparing files
In this challenge we are to explore how to compare the data in two files and finding the difference between them. For this, we are to explore the diff command to retrieve the flag.

## My flag
**pwn.college{o6FGcXW-eI_cNrfRFuZHt1T1j22.01MwMDOxwCO1EzNzEzW}**

To solve this challenge, diff command was entered along with the two files which are to be compared. On executing the program, the difference which is the flag, was given as the output. In the first file, 100 fake flags were present and in the second file 100 fake flags were present along with the flag to retrieve. On finding the difference, the flag was found.

```
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
89a90
> pwn.college{o6FGcXW-eI_cNrfRFuZHt1T1j22.01MwMDOxwCO1EzNzEzW}
```

## What I learnt
I have learnt the working and application of the diff command and how to compare two files effciently. One more thing is that, the two files are to be separated by a space.

## References
I have reffered to the video and the instructions mentioned to complete this challenge.

# 6. listing files
In this challenge we learn the application and execution of the ls command. ls is used to list all the files or programs or other directories in a given directory. We have to now find the name of /challenge/run by listing the files and components of the /challenge directory. 

## My flag
**pwn.college{Mwe0cW2IfuFk9ZdNfT_JyJulJcD.QX4IDO0wCO1EzNzEzW}**

To solve this challenge, I first read all the components of the /challenge directory with the ls command. Once executed, I received two names, "4359-renamed-run-5690"  "DESCRIPTION.md". Assuming that 
"4359-renamed-run-5690" is a file, I tried reading it with the cat command. I didn't recieve the flag, which means it is a program. I ran it as is and recieved the flag.

## What I learnt
I have learnt the use and execution of the ls command. It is used to list all the components of a given directory to find their names.

## References
I have reffered to the video and the instructions mentioned to complete this challenge.

# 7. touching files
In this challenge, we are to explore how to create new files by using the touch command. 

## My solve
**pwn.college{gMsNE0T7YY77YnDSDDChmeN1mAn.QXwMDO0wCO1EzNzEzW}**

To solve this challenge, I first used the touch command to create two files /tmp/pwn and /tmp/college and then ran /challenge/run to retrieve the flag.

```
hacker@commands~touching-files:~$ touch /tmp/pwn
hacker@commands~touching-files:~$ touch /tmp/college
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{gMsNE0T7YY77YnDSDDChmeN1mAn.QXwMDO0wCO1EzNzEzW}
```

## What I learnt
I learnt how to use the touch command to make new files.

## References
I have reffered to the video and the instructions mentioned to complete this challenge.

# 8. removing files
In this challenge we explore the rm command to remove unnecessary files. 

## My solve
**pwn.college{Y01S73WgYUC0h7H5qdt5u2Ku2bY.QX2kDM1wCO1EzNzEzW}**

To solve this challenge, I used the rm command to delete the delete_me file and then ran /challenge/check to retrieve the flag.

```
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{Y01S73WgYUC0h7H5qdt5u2Ku2bY.QX2kDM1wCO1EzNzEzW}
```

## What I learnt
I have learnt how to use the rm command to remove unnecessary files in a directory.

## References
I have reffered to the video and the instructions mentioned to complete this challenge.

# 9. moving files
In this challenge we are to explore the mv command to move files around in a directory or within directories.

## My solve
**pwn.college{Ul511sj5cs9wHErYXM13P3X4nwt.0VOxEzNxwCO1EzNzEzW}**

To solve this challenge, I used the mv command to move /flag to /tmp/hack-the-planet separated by spaces. I then ran the /challenge/check to retrieve the flag.

```
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{Ul511sj5cs9wHErYXM13P3X4nwt.0VOxEzNxwCO1EzNzEzW}
```

## What I learnt
I have learnt how to move a file to a given directory by using the mv command.

## References
I have reffered to the video and the instructions mentioned to complete this challenge.

## 10. hidden files
In this challenge, we are required to invoke hidden files which were not listed by the use of a normal ls command. To read these files ls -a is to be executed to read the a. files which were hidden from the ls.

## My solve
**pwn.college{wubPRbomrALfiFEwH3iWhtVxPdE.QXwUDO0wCO1EzNzEzW}**

To solve this challenge, I first executed the ls -a / command to list all the hidden files in the root directory. I then read the /.flag-2292245832612 to retrieve the flag. 

```
hacker@commands~hidden-files:~$ ls -a /
.   .dockerenv           bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-2292245832612  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:~$ cat /.flag-2292245832612
pwn.college{wubPRbomrALfiFEwH3iWhtVxPdE.QXwUDO0wCO1EzNzEzW}
```

## What I learnt
I have learnt how to list hidden files by using the ls -a command which may be hidden by the normal ls command. I first executed the ls -a command without the /, which meant I was listing files in the home directory. I then realized to add the / from where I recieved my flag.

## References
I have reffered to the video and the instructions mentioned to complete this challenge.

# 11. An epic file system quest

