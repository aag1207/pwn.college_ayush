# 1. Becoming root with su
In this challenge, they asked us to become the root with su and then read the flag. The root password was given (hack-the-planet).

## My solve
**pwn.college{Ay-RV0g2WiYYdzp5oV6-7L1rWd6.QX1UDN1wCO1EzNzEzW}**

To solve this challenge, I first used su and then entered the password to become the root. I then read the flag file using cat command. 

```
hacker@users~becoming-root-with-su:~$ su
Password:
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{Ay-RV0g2WiYYdzp5oV6-7L1rWd6.QX1UDN1wCO1EzNzEzW}
```

## What I learnt
I learnt that we can become the root of the system using su command. su asks for a password before giving you root status. This check against the root password is what obsoletes su. Modern systems very rarely have root passwords, and different mechanisms (that we will learn later) are used to grant administrative access. su and sudo are the two utilities we can use to become the root.

## References
I have used the instructions from pwn.college to solve this challenge. 

# 2. Other users with su
In this challenge, we are to switch to the zardus user and then run /challenge/run. Zardus' password is dont-hack-me.

## My solve
**pwn.college{Ym8DsadcuvbiEJ5MfHLKYigMuuV.QX2UDN1wCO1EzNzEzW}**

To solve this challenge,

```
hacker@users~other-users-with-su:~$ su zardus
Password:
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{Ym8DsadcuvbiEJ5MfHLKYigMuuV.QX2UDN1wCO1EzNzEzW}
```

## What I learnt
I learned how we can switch users with su. We have to keep the username as the argument of the su command.

## References
I have used the instructions from pwn.college to solve this challenge. 

# 3. Cracking passwords
In this challenge, we were given a leak of /etc/shadow in /challenge/shadow-leak. They asked us to crack the password of zardus, then su to zardus and then run /challenge/run to get the flag. 

## My solve
**pwn.college{gHBvJLu1pU9xH2ZTQh-QDD89RAq.QX3UDN1wCO1EzNzEzW}**


To solve this challenge, I first used the famous John the ripper on /challenge/shadow-leak to crack passwords. I also used the --show argument later to arrange it properly and i found the password of zardus. I then switched the user to zardus using su and entering the password found and ran /challenge/run to get the flag. 

```
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Created directory: /home/hacker/.john
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:21 100% 2/3 0.04587g/s 267.1p/s 267.1c/s 267.1C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak --show
hacker:NO PASSWORD:20357:0:99999:7:::
zardus:aardvark:20371:0:99999:7:::

2 password hashes cracked, 0 left
hacker@users~cracking-passwords:~$ su zardus
Password:
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{gHBvJLu1pU9xH2ZTQh-QDD89RAq.QX3UDN1wCO1EzNzEzW}
```

## What I learnt
I learnt how we can crack passwords using john. The passwords used to be stored in /etc/passwd, but because /etc/passwd is a globally-readable file, this is not good for passwords, these were moved to /etc/shadow. The passwords in the file are generally encrypted. 

## References
I have used the instructions from pwn.college to solve this challenge. 

# 4. Using sudo
In this challenge, we are to use the sudo access to read the flag.

## My solve
**pwn.college{0RWi4yXOoFKD2UrY-UvSJJWCGL_.QX4UDN1wCO1EzNzEzW}**

To solve this challenge, I used the cat command on /flag with sudo at the start to read the flag with root access. 

```
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{0RWi4yXOoFKD2UrY-UvSJJWCGL_.QX4UDN1wCO1EzNzEzW}
```

## What I learnt
I learned that we can put sudo at the start of the command to run the command as a root. Unlike su, which defaults to launching a shell as a specified user, sudo defaults to running a command as root. Unlike su, which relies on password authentication, sudo checks policies to determine whether the user is authorized to run commands as root. These policies are defined in /etc/sudoers. 

## References
I have used the instructions from pwn.college to solve this challenge. 


