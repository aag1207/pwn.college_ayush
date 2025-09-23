# 1. The Root
The challege requires us to use the "/" which is the root directory, the "outermost" box in which the rest of the files of a file system are stored.

## My solve
**pwn.college{MirczFephLtBTNjOgjScI5UBgcj.QX4cTO0wCO1EzNzEzW}**

On reading the instructions, I typed in "/pwn" into the terminal. The forward slash is to access the root directory while pwn is the program written to invoke the flag.

'''
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{MirczFephLtBTNjOgjScI5UBgcj.QX4cTO0wCO1EzNzEzW}
'''

## What I learnt
So, I have learnt that in a file system, the root directory is the outermost "box" in which rest of the files are stored. On using a forward slash with a program, the given flag was retrieved.

## References
I have used the video and instructions provided in the pwn.college as my references.

# 2. Program and absolute paths
The challenge requires us to execute an absolute path. In this challenge we are required to execute the run program which is in the challenge directory which is inturn in the root directory.

## My solve
**pwn.college{kEIcdPSqkGvExcouHuoySWbAI6K.QX1QTN0wCO1EzNzEzW}**

Based on the instructions, I executed the /challenge/run program which executed the run file in the challenge challenge directory in the root directory from where I retrieved the flag

'''
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{kEIcdPSqkGvExcouHuoySWbAI6K.QX1QTN0wCO1EzNzEzW}
'''

## What I learnt
So, I have learnt how to execute an absolute path. An absolute path starts with the forward slash indicating the root directory, "challenge" is the directory within the root directory in which the run program is stored. On running, the flag was retrieved.

## References
I have used the video and instructions provided in the pwn.college as my references.

# 3. Position thy self
This challenge requires us to use the "cd" command. First we had to run the /challenge/run program, then navigate around the directories. To navigate, cd(change directory) was to be typed along with the specific path given by the compiler

## My solve
**pwn.college{EOUQH609eSqijjT5CTHTf2naSWC.QX2QTN0wCO1EzNzEzW}**

Based on the instructions, I first ran the /challenge/run program. The terminal then gave me the correct path which I ran with the "cd". I then finally re executed the /challenge/run program to retrieve the flag.

'''
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /usr/share/build-essential directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /usr/share/build-essential
hacker@paths~position-thy-self:/usr/share/build-essential$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{EOUQH609eSqijjT5CTHTf2naSWC.QX2QTN0wCO1EzNzEzW}
'''
 ## What I learnt
 In this scenario I have learnt that the "cd" command is used to navigate between the directories. It expands to "change directory". On giving the terminal the /challenge/run program, it gives back a specific path to be executed.

 ## References
 I have used the video and instructions provided in the pwn.college as my references.

# 4. Position elsewhere
This challenge also deals with the cd command. First we are to run the /challenge/run program. The terminal then gives a specific path to which we have to cd to.

## My solve
**pwn.college{E18ed6fqFGJIL6bFLReaQExNOlc.QX3QTN0wCO1EzNzEzW}**

Based on the instructions, I first ran the /challenge/run program. The terminal then gave the correct path "/tmp" to which I had to cd. I then finally reexecuted the /challenge/run program to retrieve the flag.

'''
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /tmp directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /tmp
hacker@paths~position-elsewhere:/tmp$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{E18ed6fqFGJIL6bFLReaQExNOlc.QX3QTN0wCO1EzNzEzW}
'''

## What I learnt
I have learnt how to use the cd command to navigate between the directories. On giving a program to the terminal, it gives a specific path (/tmp in this case) to cd to the correct directory. From there, the program was executed.

## References
 I have used the video and instructions provided in the pwn.college as my references.

# 5. Position yet elsewhere
Once again this challenge deals with the cd command to navigate within the directories. The terminal then gives a specific path to which we have to cd to.

## My solve
**pwn.college{I8pO6FP1tDjEAxzps75xY4CUuE5.QX4QTN0wCO1EzNzEzW}**

Based on the instructions, I first ran the /challenge/run program. The terminal then gave the correct path "/tmp" to which I had to cd. I then finally reexecuted the /challenge/run program to retrieve the flag.

'''
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /var/lib/apt/lists directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /var/lib/apt/lists
hacker@paths~position-yet-elsewhere:/var/lib/apt/lists$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{I8pO6FP1tDjEAxzps75xY4CUuE5.QX4QTN0wCO1EzNzEzW}
hacker@paths~position-yet-elsewhere:/var/lib/apt/lists$
'''

## What I learnt
I have learnt how to use the cd command to navigate between the directories. On giving a program to the terminal, it gives a specific path (/var/lib/apt/lists in this case) to cd to the correct directory. From there, the program was executed.

## References
I have used the video and instructions provided in the pwn.college as my references.

# 6. Implicit relative paths, from /
This challenge requires us to deal with relative paths. While in the case of absolute paths, the current directory does not matter but in the case of relative paths, the current directory matters. Relative paths do not start with a /.

## My solve
**pwn.college{UkBDZ2vCg4V1Eqm8MDIQQFW5JLY.QX5QTN0wCO1EzNzEzW}**

I first used cd command to navigate to the / directory. Now, we are in the root directory. Input the program challenge/run (relative path) to retrieve the flag.

'''
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{UkBDZ2vCg4V1Eqm8MDIQQFW5JLY.QX5QTN0wCO1EzNzEzW}
'''

## What I learnt
I have learnt how to use relative paths. First I was to navigate to the root directory using the cd command. Once in the directory, run the program challenge/run.

## References
I have used the video and instructions provided in the pwn.college as my references.

# 7. Explicit relative paths from /
This challenge requires us to deal with ".". The "." refers to the same directory. Once we cd into a new directory, "." is used to signify presence in the same directory.

## My solve
**pwn.college{Mh9M1Q7ih3kLlDlk4MZHbvOg1hT.QXwUTN0wCO1EzNzEzW}**

I first used the cd command to enter into the root directory. I then ran the ./challenge/run within the root directory.

'''
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Mh9M1Q7ih3kLlDlk4MZHbvOg1hT.QXwUTN0wCO1EzNzEzW}
'''

## What I learnt
I have learnt the use and meaning of ".". The "." indicates the current working directory.

## Refereces
I have used the video and instructions provided in the pwn.college as my references.

# 8. Implicit relative paths
This challenge requires us to deal with ".". Once we are in a /challenge command, entering a "naked" /run shows an error. Using the ./ signifies its presence in the current working directory avoiding error.

## My solve
**pwn.college{sruYjkbDbkSVYTO1OJQVxvizV5e.QXxUTN0wCO1EzNzEzW}**

First we use the cd /challenge to navigate into the directory. Next we enter ./run to execute the program. The ./ indicates its presence in the current working directory and avoids errors

'''
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{sruYjkbDbkSVYTO1OJQVxvizV5e.QXxUTN0wCO1EzNzEzW}
hacker@paths~implicit-relative-path:/challenge$
'''

## What I learnt
I've learnt that the ./ is mandatory to indicate that the prompt is present in the current working directory and without it an error is displayed.

## References
I have used the video and instructions provided in the pwn.college as my references.

# 9. home sweet home
This challenge requires us to deal with the home directory. Bash uses ~ as the home directory as a default, expanding to /home/hacker.

## My solve
**pwn.college{w3xYrHuaW5oAiuzjiULHhF5jhzH.QXzMDO0wCO1EzNzEzW}**

So, I first wrote the command in the prompt(/challenge/run) followed by a space and the argument of home(~) with a 3 letter or less of my choice(h) which copied the flag to the file of my choice.

'''
hacker@paths~home-sweet-home:~$  /challenge/run ~/h
Writing the file to /home/hacker/h!
... and reading it back to you:
pwn.college{w3xYrHuaW5oAiuzjiULHhF5jhzH.QXzMDO0wCO1EzNzEzW}
hacker@paths~home-sweet-home:~$
'''

## What I learnt
I have learnt how to properly use an argument along with a command and copy a flag to the file of my choice.

## References
I have used the video and instructions provided in the pwn.college as my references.





