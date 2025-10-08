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
