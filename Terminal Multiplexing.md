# 1. Launching Screen
In this challenge, we learn about 'screen' which is a virtual terminal inside the main terminal.

## My solve
**pwn.college{8asKmD3gYHZOC1S6hjnGMiG_nqO.0VN4IDOxwCO1EzNzEzW}**

To solve this challenge, I executed 'screen' in the termina'

```
Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{8asKmD3gYHZOC1S6hjnGMiG_nqO.0VN4IDOxwCO1EzNzEzW}
```

## What I learnt
I learnt how to open a screen( a virtual terminal) within a terminal.

## References
I have used the instructions of pwn.college to solve this challenge

# 2.  Detaching and Attaching
In this challenge, we learn how to detach and reattach from a screen. If we lose connection, all our work is not lost in case of a screen, we can easily reattach.. which is one of the advantages of it.

## My solve
**pwn.college{E6gHnpiI0uuec6AgVzzoMGHp6LN.0lN4IDOxwCO1EzNzEzW}**

To solve this challenge, I first opened a screen using "screen". I then clicked Ctrl+A and then d to detach. I executed /challenge/run first then executed screen -r to reattach.

```
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen
[detached from 139.pts-0.terminal-multiplexing~detaching-and-attaching]
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 139.pts-0.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:

  screen -r

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
Yes! Flag is: pwn.college{E6gHnpiI0uuec6AgVzzoMGHp6LN.0lN4IDOxwCO1EzNzEzW}
```

## What I learnt
I learnt how to detach(using Ctrl+A then d) and reattach(screen -r) to a screen.

## References
I have used the instructions of pwn.college to solve this challenge

# 3. Finding Sessions
In this challenge, we learn how to navigate through various sessions within a screen by reattaching using the screen -r [aug] where the aug can be either the name of the screen or the PID of the screen.

## My solve
**

To solve this challenge, I first listed all the sessions in a screen using the -ls command. I then used the screen -r aug command to check various sessions for flag using their PID.

```
hacker@terminal-multiplexing~finding-sessions:~$ screen -ls
There are screens on:
        150.pts-0.terminal-multiplexing~launching-screen        (Remote or dead)
        154.pts-1.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        178.pts-3.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        200.pts-3.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        139.pts-0.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        144.session_821e7f828892b710    (Detached)
        147.session_91e2b17b2bb07508    (Detached)
        150.session_0b9e12904f69c2de    (Detached)
8 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 144
[detached from 144.session_821e7f828892b710]
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 147
[detached from 147.session_91e2b17b2bb07508]
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 150
Remove dead screens with 'screen -wipe'.
[detached from 150.session_0b9e12904f69c2de]
hacker@terminal-multiplexing~finding-sessions:~$  echo 'Congratulations! You found the right session!'
Congratulations! You found the right session!
hacker@terminal-multiplexing~finding-sessions:~$  echo pwn.college{8NgnZ8du6lnncRPle-6V1_uu__K.01N4IDOxwCO1EzNzEzW}
pwn.college{8NgnZ8du6lnncRPle-6V1_uu__K.01N4IDOxwCO1EzNzEzW}
```

## What I learnt
I have learnt how to navigate through files and check various sessions to find the required data.

## References
I have used the instructions of pwn.college to solve this challenge

# 4. Switching Windows
In this challenge, we are to explore windows. Multiple windows can be opened within a screen and we must know how to navigate between them.

## My solve
**pwn.college{436iCE3PuOkLk_zHY1EH9kCLYgg.0FO4IDOxwCO1EzNzEzW}**

To solve this challenge, I first listed all the screens.. then I attached to the challenge_session. I then switched to windows 0 using Ctrl+A and 0 to retrieve the flag.

```
hacker@terminal-multiplexing~switching-windows:~$ screen -ls
There are screens on:
        150.pts-0.terminal-multiplexing~launching-screen        (Remote or dead)
        154.pts-1.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        178.pts-3.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        200.pts-3.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        139.pts-0.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        144.session_821e7f828892b710    (Remote or dead)
        147.session_91e2b17b2bb07508    (Remote or dead)
        150.session_0b9e12904f69c2de    (Remote or dead)
        135.challenge_session   (Detached)
        174.pts-2.terminal-multiplexing~switching-windows       (Detached)
10 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~switching-windows:~$ screen -r 135
 cat <<MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
MSG
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Welcome to the window switching challenge!
> You are currently in window 1.
> The flag is hidden in window 0.
> Use Ctrl-A 0 to switch to window 0!
> MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{436iCE3PuOkLk_zHY1EH9kCLYgg.0FO4IDOxwCO1EzNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{436iCE3PuOkLk_zHY1EH9kCLYgg.0FO4IDOxwCO1EzNzEzW}
```

## What I learnt
I have learnt the concept of windows. I have learnt how to navigate through windows using multiple methods.
Ctrl-A c - Create a new window
Ctrl-A n - Next window
Ctrl-A p - Previous window
Ctrl-A 0 through Ctrl-A 9 - Jump directly to window 0-9
Ctrl-A " - bring up a selection menu of all of the windows

## References
I have used the instructions of pwn.college to solve this challenge


# 5. Detaching and Attaching(TMUX)
In this challenge, we learn about the terminal multiplexer which is a newer version of a screen using Ctrl B instead of Ctrl A.

## My solve
**pwn.college{4olgASgZCMCaJhkLRpktqKYxIyE.0VO4IDOxwCO1EzNzEzW}**

To solve this challenge, I first ran tmux, then detached from it, then reattached to it to retrieve the flag.

```
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Found detached tmux session: 0
Sending flag to your tmux session...

Flag sent! Now reattach to your tmux session with:
  tmux attach

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux attach
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$  echo Congratulations, here is your flag: pwn.college{4olgASgZCMCaJhkLRpktqKYxIyE.0VO4IDOxwCO1EzNzEzW}
Congratulations, here is your flag: pwn.college{4olgASgZCMCaJhkLRpktqKYxIyE.0VO4IDOxwCO1EzNzEzW}
```

## What I learnt
I learnt how to detach reattach and launch the terminal multiplexer.

## References
I have used the instructions of pwn.college to solve this challenge


# 6. Switching Windows
In this challenge, we learn to navigate windows in the tmux using multiple methods.

## My solve
**pwn.college{w4T0TV3EVypK6KlKz8JAIPMYpk7.0FM5IDOxwCO1EzNzEzW}**

To solve this challenge, I first attached to a tmux and then switched to the windows 0 to retrieve the flag.

```
hacker@terminal-multiplexing~switching-windows-tmux:~$ tmux
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{w4T0TV3EVypK6KlKz8JAIPMYpk7.0FM5IDOxwCO1EzNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{w4T0TV3EVypK6KlKz8JAIPMYpk7.0FM5IDOxwCO1EzNzEzW}
```

## What I learnt
I learnt how to navigate through windows within a tmux.

## References
I have used the instructions of pwn.college to solve this challenge

