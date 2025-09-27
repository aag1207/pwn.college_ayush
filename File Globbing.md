# 1. Matching with * 
In this challenge, it was given to change your directory to '/challenge', but use globbing to keep the argument you pass to cd to at most four characters. After that it told to run '/challenge/run' to get the flag.

## My solve
**pwn.college{wXyH3hpyNqWoAXhkAWsZNKOEFbJ.QXxIDO0wCO1EzNzEzW}**

I changed my cwd to '/challenge' and kept it within 4 characters by using '*' glob. After the cwd changed, i ran the program to get the flag. 

```
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{wXyH3hpyNqWoAXhkAWsZNKOEFbJ.QXxIDO0wCO1EzNzEzW}
```

## What I learned
I first learned about globbing. Globbing lets you reference files without typing out their full paths. Before executing commands that you enter, the shell first performs expansions on them, and one of these 
expansions is globbing. In this challenge, i learned about the "star" glob, When it encounters a "star" character in any argument, the shell will treat it as a wildcard and try to replace that argument with any files 
that match the pattern. It can match multiple files or single files also if only 1 file is there with that pattern. When zero files are matched,the shell leaves the glob unchanged. The "star" matches any part of the 
filename except for "/" or a leading ".".

## References
I used the instructions mentioned in the challenge and the resources of pwn.college to crack this challenge.

# 2. Matching with ? 
In this challenge, it was given to change your directory to '/challenge' from home directory using the '?' glob instead of c and l. After that it was given to run '/challenge/run' to get the flag. 

## My solve
**pwn.college{QzOSU5B4Ur2hl7-ssEMKt2-VD3-.QXyIDO0wCO1EzNzEzW}**

I first used the cd command along with '/?ha??enge' command, as they told to replace c and l with glob. Then i ran the program to get the flag.

```
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{QzOSU5B4Ur2hl7-ssEMKt2-VD3-.QXyIDO0wCO1EzNzEzW}
```

## What I learned
I learned about the '?' glob. It is similar to the star glob but it only matches one character. The shell basically treats it like a single character wildcard. 

## References
I used the instructions mentioned in the challenge and the resources of pwn.college to crack this challenge.

# 3. Matching with []
In this challenge, it asked us to first Change our working directory to /challenge/files and run /challenge/run with a single argument that bracket-globs into file_b, file_a, file_s, and file_h.

## My solve
**pwn.college{E5ON64mhPrfAbSLqdT5IiHH9_oY.QXzIDO0wCO1EzNzEzW}**

I first used the cd command to change the cwd to /challenge/files. Then I used the square bracket glob with letters b,a,s,h inside (like bash) as the argument for /challenge/run to get the flag.

```
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run files_[bash]
Your expansion did not expand to the requested files (file_a, file_b, file_h,
and file_s). Instead, it expanded to:
files_[bash]
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{E5ON64mhPrfAbSLqdT5IiHH9_oY.QXzIDO0wCO1EzNzEzW}
```

## What I learned
I learned about the square bracket glob. The square brackets are, essentially, a limited form of "?", in that instead of matching any character, square bracket is a wildcard for some subset of potential characters, specified within the brackets. For example, "[pwn]" will match the character p, w, or n. I first wrote files insead of file which resulted in getting files[bash] as output instead of file[a] file[b] etc...

## References
I used the instructions mentioned in the challenge and the resources of pwn.college to crack this challenge.

# 4. Matching paths with [] 
This challenge was similar to the previous challenge, Just that we have to start from our home directory and we have to run /challenge/run with a single argument that bracket-globs into the absolute paths to the file_b, file_a, file_s, and file_h files.

## My solve
**pwn.college{Ec2UBkjOHrK7LcTYtmxoKRBsdTC.QX0IDO0wCO1EzNzEzW}**

I ran the /challenge/run program with the absolute path of all the files globbed into a square bracket.

```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{Ec2UBkjOHrK7LcTYtmxoKRBsdTC.QX0IDO0wCO1EzNzEzW}
```

## What I learned
I learned that we can also expand entire paths with globbed arguments. I also learned that globbing happens on a path basis. 

## References
I used the instructions mentioned in the challenge and the resources of pwn.college to crack this challenge.

# 5. Multiple globs
In this challenge/ it asked us to change the working directory to /challenge/files, then  run /challenge/run, providing a single argument: a short (3 characters or less) globbed word with two * globs in it that covers every word that contains the letter p.

## My solve
**pwn.college{8TTh7yaojLDGP_pbmDCL6PH9TQn.0lM3kjNxwCO1EzNzEzW}**

I first used the cd command to change the cwd to /challenge/files. Then I used the /challenge/run with two star globs and p in between as arguments to get the flag. 

```
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ ls
amazing      delightful   great       jovial    magical     pwning   splendid   victorious  youthful
beautiful    educational  happy       kind      nice        queenly  thrilling  wonderful   zesty
challenging  fantastic    incredible  laughing  optimistic  radiant  uplifting  xenial
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{8TTh7yaojLDGP_pbmDCL6PH9TQn.0lM3kjNxwCO1EzNzEzW}
```

## What I learned
I learned that we can use multiple globs at a time that too in a single word also. 

## References
I used the instructions mentioned in the challenge and the resources of pwn.college to crack this challenge.

# 6. Mixing globs
In this challenge, they asked us to cd to /challenge/files, then using the globbing we learned till now, we had to write a single, short (6 characters or less) glob that (when passed as an argument to /challenge/run) will match the files "challenging", "educational", and "pwning".

## My solve
**pwn.college{cAZuZ4eKit4n14OFCYTysbICDFZ.QX1IDO0wCO1EzNzEzW}**

I first used cd command to change the cwd to /challenge/files, then I ran the program with /challenge/run with c,e,p inside square brackets and 1 star as globs as the argument, this argument was exactly 6 characters, and i got the flag. This argument will match all the files that start with either c,p or e. 

```
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ ls
amazing      delightful   great       jovial    magical     pwning   splendid   victorious  youthful
beautiful    educational  happy       kind      nice        queenly  thrilling  wonderful   zesty
challenging  fantastic    incredible  laughing  optimistic  radiant  uplifting  xenial
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{cAZuZ4eKit4n14OFCYTysbICDFZ.QX1IDO0wCO1EzNzEzW}
```

## What I learned
I learned that we can use different types of globs into the same argument and the shell will expand it. 

## References
I used the instructions mentioned in the challenge and the resources of pwn.college to crack this challenge.

# 7. Exclusionary globbing: 

### In this challenge, they asked us to go to /challenge/files and then run /challenge/run with all files that don't start with p, w, or n as argument. 

## My solve
**pwn.college{c2Wf1QeUnuB1uiw6f1syEg6w-yh.QX2IDO0wCO1EzNzEzW}**

As they gave, i first changed the cwd to /challenge/files using cd command. Then i ran the program along with using the square brackets glob with (!pwn) inside to exclude those files which are starting with p,w, or n (exclusionary globbing), and i kept the star glob to include all files after that. 

```
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ ls
amazing      delightful   great       jovial    magical     pwning   splendid   victorious  youthful
beautiful    educational  happy       kind      nice        queenly  thrilling  wonderful   zesty
challenging  fantastic    incredible  laughing  optimistic  radiant  uplifting  xenial
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{c2Wf1QeUnuB1uiw6f1syEg6w-yh.QX2IDO0wCO1EzNzEzW}
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [^pwn]*
You got it! Here is your flag!
pwn.college{c2Wf1QeUnuB1uiw6f1syEg6w-yh.QX2IDO0wCO1EzNzEzW}
```

## What I learned
I learned that we can also exclude some characters while globbing using square bracket glob and starting either ! or ^ inside the bracket and then keeping the letters we want to exclude. 

## References
I used the instructions mentioned in the challenge and the resources of pwn.college to crack this challenge.

# 8. Tab completion
In this challenge, they copied the flag into /challenge/pwncollege, and we can freely cat that file. But we can't type the filename. We have to tab-complete (click tab on your keyboard) to get the flag.

**pwn.college{kzT5nJEx-G5DF2lK6gp_mstZ4pf.0FN0EzNxwCO1EzNzEzW}**

I read /challenge/pwncollege using the cat command, but I clicked tab after typint till pwn, as they told we muct tab-complete in the challenge to get the flag. 

```
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege
cat: /challenge/pwncollege: No such file or directory
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​
pwn.college{kzT5nJEx-G5DF2lK6gp_mstZ4pf.0FN0EzNxwCO1EzNzEzW}
```

## What I learned
I learned that instead of using the star glob, which is risky as it might expand to unintended files, we can click tab when we are writing the path of the file and the shell will try to figure out what you're going to type and automatically complete it. All we have to do is click tab.

## References
I used the instructions mentioned in the challenge and the resources of pwn.college to crack this challenge.

# 9. Multiple options for tab completion
In this challenge,

# 10. Tab completion on commands
In this challenge, it was given that there is a command that starts with  pwncollege, and it'll give you the flag. It told us to type pwncollege and hit the tab key to auto-complete it.

## My solve
**pwn.college{U9_so8uiyvE2DtEHsem_oEnbEVF.0VN0EzNxwCO1EzNzEzW}**

As given in the challenge statement, I first typed pwncollege then clicked tab, it auto completed the command and I executed the command to get the flag. 

```
hacker@globbing~tab-completion-on-commands:~$ pwncollege-19959
Correct! Here is your flag:
pwn.college{U9_so8uiyvE2DtEHsem_oEnbEVF.0VN0EzNxwCO1EzNzEzW}
```

## What I learned
I learned that we can use the tab key for completing not only files, but we can use it for commands also. But we must be careful when we auto complete and check if the command is correct to prevent wrong commands with a similar name from being executed. 

## References
I used the instructions mentioned in the challenge and the resources of pwn.college to crack this challenge.

