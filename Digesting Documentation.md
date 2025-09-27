# 1. Learning from Documentation
In this challenge we explore the concept of documentation. Documentation from my understanding is a help tool to determine the correct argument to execute the desired program.

## My solve
**pwn.college{wFdVgrYvfEl872WdwfGsAbKCNX1.QX0ITO0wCO1EzNzEzW}**

To solve this challenge, I executed /challenge/challenge with the correct argument of --giveflag to retrieve the flag.

```
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{wFdVgrYvfEl872WdwfGsAbKCNX1.QX0ITO0wCO1EzNzEzW}
```

## What I learnt
I have learnt how to use documentation as a tool to obtain a specific argument for executing a program. The documentation contains all the details about a file and a program 

## References
I have used the pwn.college resources, instructions mentioned in the challenge to solve the challenge and retrieve the flag.

# 2. Learning complex usage
In this challenge, a documentation for '/challenge/challenge' program was given. This documentation provided that if we run the program, it will print arbitrary file to the terminal, when we give it the '--printfile argument'. It was also told that we have to give the path of the file as the argument to '--printfile'. 

## My solve
**pwn.college{QB-fAa8GX-sEg_W33WSdJYcrEOR.QX1ITO0wCO1EzNzEzW}**

I invoked the '/challenge/challenge' program with the '--printfile' argumant, along with the path to the flag (/flag) as the argument to '--printfile'. This entire command then printed the flag file and i got the flag.

```
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{QB-fAa8GX-sEg_W33WSdJYcrEOR.QX1ITO0wCO1EzNzEzW}
```

## What I learned
I learned that some commands take arguments to their arguments. For example, 'find' has a '-name' argument, and the '-name' argument itself takes an argument specifying the name to search for. I took a while to actually determine that I had to mention the /flag root after the argument to retrieve the flag.

## References
I have used the pwn.college resources, instructions mentioned in the challenge to solve the challenge and retrieve the flag.

# 3. Reading manuals
In this challenge, there was a secret option that, when you use it, will cause the challenge to print the flag. The 'man' command was introduced and we have to go through the manpage of 'challenge' to get the flag.

## My solve
**pwn.college{IXQD2NXmQCAG8aK6FilCifDEnRi.QX0EDO0wCO1EzNzEzW}**

I first opened the manual page of 'challenge' by using the 'man' command with 'challenge' as the argument. In the manual, it was given that '/challenge/challenge' program prints the flag if the correct argument --unlnre 821 is given. So i ran the program with the argument they gave to print the flag.  

```
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --mailif 286
Correct usage! Your flag: pwn.college{IXQD2NXmQCAG8aK6FilCifDEnRi.QX0EDO0wCO1EzNzEzW}
```

## What I learned
I learned about the man command. It will display (if available) the manual of the command you pass as an argument. For example: man cd. Manpages are stored in a centralized database and that database lives in the /usr/share/man directory, but we dont need to interact with it directly, we can just use the man command. 
Also, in man challenge, Manpages are stored in a centralized database and that database lives in the /usr/share/man directory, but we dont need to interact with it directly, we can just use the man command. 

## References
In this challenge, it was similar to the previous challenge, where we had to read the manual page of 'challenge' to find the correct argument to get the flag. But over here we have to search in the manual as the manual was very big. 

**Flag:** `pwn.college{An2Zf4yXJZ3UgR7g91wS_Td9itF.QX1EDO0wiN3kjNzEzW}`

I first opened the manual page of challenge with the 'man' command, then i searched for all the 'flag' words using '/' and '?' and 'n' and 'N' to navigate around, until i found the correct argument to use to get the flag.  

```
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --qp
Initializing...
Correct usage! Your flag: pwn.college{An2Zf4yXJZ3UgR7g91wS_Td9itF.QX1EDO0wiN3kjNzEzW}
```

## What I learned

I learned how to search for keywords inside manual pages (manpages) in linux. We have to use '/' to search or '?' to search backwards. After searching, we can click 'n' to go to the next result or 'N' to go to the previous result. You can scroll man pages with the arrow keys.

## References

The reference used was the challenge statement and docummentation given in pwn.college. The inbuilt manpages were also used.

# 4. 
In this challenge, it was similar to the previous challenge, where we had to read the manual page of 'challenge' to find the correct argument to get the flag. But over here we have to search in the manual as the manual was very big. 

## My solve
**pwn.college{EE504oyVW506z9xiL_b-RiDE_WB.QX1EDO0wCO1EzNzEzW}**

I first opened the manual page of challenge with the 'man' command, then i searched for all the 'flag' words using '/' and '?' and 'n' and 'N' to navigate around, until i found the correct argument to use to get the flag.  

```
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --nvp
Initializing...
Correct usage! Your flag: pwn.college{EE504oyVW506z9xiL_b-RiDE_WB.QX1EDO0wCO1EzNzEzW}
```

## What I learned

I learned how to search for keywords inside manual pages (manpages) in linux. We have to use '/' to search or '?' to search backwards. After searching, we can click 'n' to go to the next result or 'N' to go to the previous result. You can scroll man pages with the arrow keys.

## References
The reference used was the challenge statement and docummentation given in pwn.college. The inbuilt manpages were also used.

# 5. 
In this challenge, it hid the  manpage for the challenge by randomizing its name. It asked us to search the manpage database to find the hidden challenge man page. The following hints were given: 1)  man man teaches you advanced usage of the man command itself, and you must use this knowledge to figure out how to search for the hidden manpage that will tell you how to use /challenge/challenge. 2) though the manpage is randomly named, you still actually use /challenge/challenge to get the flag.

## My solve
**pwn.college{IJ6tGIgXTThjRdK1tqQZa6TA2xq.QX2EDO0wCO1EzNzEzW}**

I first went into the manpage of 'man' command, and searched for the keyword 'search', as we had to find a argument to search the database of all manpages. I then looked around and saw the '--wildcard' argument, which searches all the manpages names and description for a keyword. I used this argument used the keyword flag to search all the manpages for flag. It then opened the manpage for '/challenge/challenge' program and inside that manpage was the argument when used with the program, gave the flag. The argument was -wuwpbb 901.  I used this command with the argument to get the flag.  

```
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man --wildcard flag
hacker@man~searching-for-manuals:~$ /challenge/challenge --tghjdt 616
Correct usage! Your flag: pwn.college{IJ6tGIgXTThjRdK1tqQZa6TA2xq.QX2EDO0wCO1EzNzEzW}
```

## What I learned
I learned that there is a manpage for the 'man' command also. I also learned that there is a searchable database containing all the manpages, and we can search many different things in that like keywords in both program/files names or descriptions. We can always use the manpages and the searching tool inside the manpages for reference. 

## References
The reference used was the challenge statement and docummentation given in pwn.college. The inbuilt manpages was also used.

# 6.
## This program told us to use the '--help' argument with /challenge/challenge program to get hints on how to get the flag. 

**pwn.college{8NJ36pejhTpEFDcA90xVM3NG_Ei.QX3IDO0wiN3kjNzEzW}**

## My solve
I first ran the program with '--help' argument as they told, which gave a way on how we can use the command. It told at the last that we need to get a value with the '-p' argument to keep it along with the '-g' argument to get the flag. So i used the '-p' argument to get the value and i used '-g' argument along with the value to get the flag. I first accidently copy pasted the entire argument from the help page instead of replacing the placeholder (GIVE_THE_FLAG) with the value. 

```
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge --print-value
The secret value is: 233
hacker@man~helpful-programs:~$ /challenge/challenge --give-the-flag 233
Correct usage! Your flag: pwn.college{YQyE2pmZk3-eMP_JbkTGfTfkTVn.QX3IDO0wCO1EzNzEzW}
```

## What I learned
I learned that not all commands have a man page, some don't. However, we can use the '--help- or sometimes '-h' argument along with the command to know how to use the command. 

## References
The reference used was the challenge statement and docummentation given in pwn.college. The inbuilt help page with the '--help' argument was also used.

# 7. Help for builtins
### In this challenge, the challenge command is a shell builtin, rather than a program. We need to look at its help to find the secret value and get the flag. 

## My solve
**pwn.college{kVy_hYEMMvQ52wRKJUpSJPlf7BE.QX0ETO0wCO1EzNzEzW}**

I used the 'help' to lookup help for builtins, where help is a builtin in this case. In that help page, the secret value and the argument to get the flag was given. I then ran the challenge command with the argument and the secret value given in help to get the flag.  

```
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "kVy_hYEM".
hacker@man~help-for-builtins:~$ /challenge/challenge --kVy_hYEM
bash: /challenge/challenge: No such file or directory
hacker@man~help-for-builtins:~$ /challenge/challenge --secret kVy_hYEM
bash: /challenge/challenge: No such file or directory
hacker@man~help-for-builtins:~$ challenge --secret kVy_hYEM
Correct! Here is your flag!
pwn.college{kVy_hYEMMvQ52wRKJUpSJPlf7BE.QX0ETO0wCO1EzNzEzW}
```

## What I learned
I first learned about builtins, which are commands that are inbuilt into the shell itself, instead of being programs with man pages and help options. Builtins are invoked just like commands, but the shell handles them internally instead of launching other programs. We can get a list of all shell builtins with the 'help' builtin. We can get help on a specific builtin by passing it to the help builtin, like 'help cd' (in place of cd you can put any builtin, and yes cd is a builtin). I first used the /challenge/challenge with the --secret instead of challenge, which was wrong.

## References
The reference used was the challenge statement and docummentation given in pwn.college. The help command for inbuilts was also used. 
