# 1. cat: not the pet, but the command
This challenge deals with the cat command. It is one of the most critical linux commands used for reading out the files.

## My solve
**pwn.college{IS0oGiZJWk1uiu7WmdTGhh9-trK.QXxcTN0wCO1EzNzEzW}**

It was mentioned in the challenge that the required flag was copied into the flag file of the home directory. So, in order to read the flag file and retrieve the flag, cat flag was the program executed

'''
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{IS0oGiZJWk1uiu7WmdTGhh9-trK.QXxcTN0wCO1EzNzEzW}
hacker@commands~cat-not-the-pet-but-the-command:~$
'''

## What I leant
I learnt the use of the cat command. In order to read any file, the cat command is used.

## References
I have reffered to the video and the instructions mentioned to complete this challenge.

# 2. catting absolute paths
This challenge also deals with the cat command. In this case, the flag is not copied directly onto my home directory. We are to first change directory(cd) to the root directory and then execute cat flag.

## My flag
**pwn.college{kFcb9xO0XK1dSe5lF_fNucqNITj.QX5ETO0wCO1EzNzEzW}**

It was mentioned that this time, the flag wasn't directly copied onto my home directory. So, in order to read the flag folder, cat /flag(absolute path) was used. I had first done it
