# 1. Listing Processes
In this challenge, we learn how to use the ps command to know the process status of the compiler. The use of arguments -ef and aux for a more detailed newer output.

## My solve
**pwn.college{olOc4OBCyuT_5boKr_3J8FIbAmW.QX4MDO0wCO1EzNzEzW}**

To solve this challenge, I first used the ps auxww to list all the processes currently taking place in the compiler. I then ran the /challenge/25889-run-4005 to retrieve the flag.

```
hacker@processes~listing-processes:/$ ps auxww
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   17:23   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0 231708  2560 ?        S    17:23   0:00 /run/dojo/bin/sleep 6h
root         132  0.0  0.0   4132  2560 ?        S    17:23   0:00 /challenge/25889-run-4005
root         135  0.0  0.0   2744  1280 ?        S    17:23   0:00 sleep 6h
hacker       137  0.0  0.0 231576  3520 pts/0    Ss   17:23   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/bin/bash /run/dojo/bin/ssh-entrypoint
hacker       143  0.0  0.0 231940  4160 pts/0    S    17:23   0:00 /run/dojo/bin/bash --login
hacker       155  0.0  0.0 233600  3840 pts/0    R+   17:26   0:00 ps auxww
hacker@processes~listing-processes:/$ /challenge/25889-run-4005
Yahaha, you found me! Here is your flag:
pwn.college{olOc4OBCyuT_5boKr_3J8FIbAmW.QX4MDO0wCO1EzNzEzW}
Now I will sleep for a while (so that you could find me with 'ps').
```

## What I learnt
I have learnt the use and execution of the ps command to list all the processes in the compiler. The use of ww at the end avoids the truncating nature of the ps command to the width of the terminal. a is to list processes for all users, x to list processes that aren't running in a terminal, and u for a "user-readable" output. These can be combined into a single argument aux.

## References
The instructions of the pwn.college have helped me solve this challenge.


# 2. Killing Processes
In this challenge, we are to use the kill command to kill an existing process to retrieve the flag. /challenge/run will not run unless /challenge/dont_run is killed.

## My solve
**pwn.college{kej813OzPU9cu_yWtJ39OS9d-Vh.QXyQDO0wCO1EzNzEzW}**

```
hacker@processes~killing-processes:~$ ps aux | grep dont_run
hacker       136  0.0  0.0 231576  3520 ?        Ss   07:40   0:00 /challenge/dont_run
hacker       154  0.0  0.0   5656  2880 pts/0    S+   07:43   0:00 /bin/bash /challenge/dont_run
hacker       175  0.0  0.0   5656  2880 pts/1    S+   07:45   0:00 /bin/bash /challenge/dont_run
hacker       193  0.0  0.0 230696  2560 pts/2    S+   07:47   0:00 grep --color=auto dont_run
hacker@processes~killing-processes:~$ kill 175
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{kej813OzPU9cu_yWtJ39OS9d-Vh.QXyQDO0wCO1EzNzEzW}
```

## What I learnt
I learnt about the kill command, which will terminate a process when we pass the PID of the process as the argument. 

## References
The instructions of the pwn.college have helped me solve this challenge.

# 3. Interrupting Processes
In this challenge, we are to use the Ctrl+C command which sends an 'interrupt' to whatever process is waiting at the input from the terminal, causing the application to cleanly exit.

## My solve
**pwn.college{w8PAjiod8NIwm18ZyEdM4QL4jWR.QXzQDO0wCO1EzNzEzW}**

To solve this challenge, I first executed the /challenge/run command followed by Ctrl+C to 'declog' the terminal and forcefully making it exit.

```
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{w8PAjiod8NIwm18ZyEdM4QL4jWR.QXzQDO0wCO1EzNzEzW}
```

## What I Learnt
I learnt about how we can interrupt a process using ctrl-c. Ctrl-c sends an "interrupt" to whatever application is waiting on input from the terminal and, typically, this causes the application to cleanly exit.

## References
The instructions of the pwn.college have helped me solve this challenge.


# 4. Killing Misbehaving Processes
In this challenge,

## My solve
**

```

```

## What I learnt

## References
The instructions of the pwn.college have helped me solve this challenge.

# 5. Suspending Processes
In this challenge we are to Use the terminal to launch /challenge/run, then suspend it using Ctrl+Z, then launch another copy while the first is suspended. 

## My solve
**pwn.college{03CMGZHcf8s1cuDSw6zK-iKzBXg.QX1QDO0wCO1EzNzEzW}**

I first ran /challenge/run, then I clicked Ctrl-Z to suspend the process. Then I ran /challenge/run again to get the flag. 

```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         145     129  0 12:31 pts/0    00:00:00 bash /challenge/run
root         147     145  0 12:31 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         145     129  0 12:31 pts/0    00:00:00 bash /challenge/run
root         152     129  0 12:31 pts/0    00:00:00 bash /challenge/run
root         154     152  0 12:31 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{03CMGZHcf8s1cuDSw6zK-iKzBXg.QX1QDO0wCO1EzNzEzW}
```

## What I learnt
I learned that we can suspend processes to the background using ctrl-z. 

## References
The instructions of the pwn.college have helped me solve this challenge.

# 6. Resuming Processes
In this challenge, we are to first suspend the program, then resume it by using the fg command to get the flag. 

## My solve
**

To solve this challenge, I first ran /challenge/run process, then I suspended it with ctrl-z. I then resumed the process using fg command with the process as argument and got the flag.

```
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg /challenge/run
/challenge/run
I'm back! Here's your flag:
pwn.college{E3gqkVMzOZLGZo3R0bRVhx7gEaY.QX2QDO0wCO1EzNzEzW}
Don't forget to press Enter to quit me!

Goodbye!
```

## What I learnt
I learned about the fg command, which resumes the suspended processes, and puts it back in the foreground of the terminal. 

## References
The instructions of the pwn.college have helped me solve this challenge.


# 7. Backgrounding Processes
In this challenge, we are to suspend a process using Ctrl+Z then resume it in the background using the bg command.

## My solve
**pwn.college{AB9t6SBtuQyNq2fDp90hd_4-fzf.QX3QDO0wCO1EzNzEzW}**

```
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         145 S+   bash /challenge/run
root         147 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg /challenge/run
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         145 S    bash /challenge/run
root         155 S    sleep 6h
root         156 S+   bash /challenge/run
root         158 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{AB9t6SBtuQyNq2fDp90hd_4-fzf.QX3QDO0wCO1EzNzEzW}
```

## What I learnt
I learned about the bg command, which will basically resume the process like fg, but in the background, while fg will resume it in the foreground. This will allow the process to keep running, while giving you your shell back to invoke more commands in the meantime. 

## References
The instructions of the pwn.college have helped me solve this challenge.

# 8. Foregrounding Processes
In this challennge, we are to first suspend a program, then resume in the background, then brought to the foreground without suspending it.

## My solve
**pwn.college{wo_2ikss0BkpG2hc82wRAOJ6L8F.QX4QDO0wCO1EzNzEzW}**

To solve this challenge, I first ran /challenge/run, which displayed the steps to solve this challenge. I first clicked ctrl-z to suspend the run process. Then I resumed it in the background using the bg command. I then brought it to the foreground using the fg command. 

```
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg /challenge/run
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.

hacker@processes~foregrounding-processes:~$ fg /challenge/run
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{wo_2ikss0BkpG2hc82wRAOJ6L8F.QX4QDO0wCO1EzNzEzW}
```

## What I learnt
I learned that we can foreground a backgrounded process with fg, just like how we foreground a suspended process. 

## References
The instructions of the pwn.college have helped me solve this challenge.

# 9. Starting Backgrounded Processes
In this challenge, they told that this challenge's run process should be launched backgrounded to get the flag.

## My solve
**pwn.college{Qg58mYKiMLg9B7VqHb_I4xVIoM_.QX5QDO0wCO1EzNzEzW}**

To solve this challenge, I ran /challenge/run process, appended with "&" to retrieve the flag. 

```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 150
hacker@processes~starting-backgrounded-processes:~$


Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{Qg58mYKiMLg9B7VqHb_I4xVIoM_.QX5QDO0wCO1EzNzEzW}
```

## What I learnt
I learned that we dont have to suspend a process to background them like previous challenges, we can start/launch them backgrounded by appending the command with "&".  

## References
The instructions of the pwn.college have helped me solve this challenge.

# 10. Process exit codes
In this challenge, we are to retrieve the exit code returned by /challenge/get-code and then run /challenge/submit-code with that error code as an argument to get the flag. 

## My solve
**pwn.college{EPyuM51Mz-wwmINzstqF4u3qjnf.QX5YDO1wCO1EzNzEzW}**

To solve this challenge, I first ran /challenge/get-code. Then I read the exit code of the command using the "?" variable with echo command (echo $?). We have to use "$" because "?" is a variable. I then got the error code, which was 40, then i ran /challenge/submit-code with 40 as argument to get the flag.

```
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
218
hacker@processes~process-exit-codes:~$ /challenge/submit-code 218
CORRECT! Here is your flag:
pwn.college{EPyuM51Mz-wwmINzstqF4u3qjnf.QX5YDO1wCO1EzNzEzW}
```

## What I learnt
I learned how we can access the error codes of of the most recently-terminated command using the special "?" variable (don't forget to prepend it with "$" to read its value). 

## References
The instructions of the pwn.college have helped me solve this challenge.







