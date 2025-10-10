# 1. The path variable
In this challenge, we understand the importance of paths. We are to blank out the path of /challenge/run so that it cannot delete the flag using the rm command.

## My solve
**pwn.college{oZvfoNnfDSI4jY4PTEUsRplBMqW.QX2cDM1wCO1EzNzEzW}**

To solve this challenge, I first listed using ls. I then executed PATH="" and then ran /challenge/run. Since I blanked out /challenge/run, it could not delete the /flag/

```
hacker@path~the-path-variable:~$ ls
COLLEGE  Desktop  PWN  foo.1x.dvi  h  instructions  myflag  the-flag
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{oZvfoNnfDSI4jY4PTEUsRplBMqW.QX2cDM1wCO1EzNzEzW}
```

## What I learnt
I have learnt the importants of paths to execute commands. Blanking out the path renders the input useless.

## References
The instructions of the pwn.college have helped me solve this challenge.

# 2. Setting Path
In this challenge, we are to play around with the PATH variable, assigning paths to get the desired outcome

## My solve
**pwn.college{kcLO88YMLUk_5IiLbZDa07CaWzb.QX1cjM1wCO1EzNzEzW}**

To solve this challenge, I first made the path /challenge/more_commands which was not initially in the path. I then ran /challenge/run to get the flag.

```
hacker@path~setting-path:~$ PATH=/challenge/more_commands
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{kcLO88YMLUk_5IiLbZDa07CaWzb.QX1cjM1wCO1EzNzEzW}
```

## What I learnt
I have learnt how to assign a new path directory to the path variable and playing around with directories not previously in the main path.

## References
The instructions of the pwn.college have helped me solve this challenge.

# 3. Finding Commands
In this challenge, we understand the "which?" question. When a command is executed, one of the many directories in the $Path gets executed, using which, we understand which file precisely?

## My solve
**pwn.college{ocSfBZG3m4eQ9Gun-8i1ejAr7EI.01NzEzNxwCO1EzNzEzW}**

To solve this challenge,

```
hacker@path~finding-commands:~$ which win
/challenge/paths/24870/win
hacker@path~finding-commands:~$ cat /challenge/paths/24870/flag
pwn.college{ocSfBZG3m4eQ9Gun-8i1ejAr7EI.01NzEzNxwCO1EzNzEzW}
```

## What I learnt
I have learnt how to find out which directory is executed when a command is typed and how to figure it out using the which command.

## References
The instructions of the pwn.college have helped me solve this challenge.

# 4. Adding Commands

