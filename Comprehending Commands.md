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
In this challenge, we are to retrieve the flag following a list of clues hidden in various files and directories using the cd, ls and cat commands.

## My solve
**

To solve this challenge, 

```
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
EVIDENCE  boot       dev  flag  lib    lib64   media  nix  proc  run   srv  tmp  var
bin       challenge  etc  home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~an-epic-filesystem-quest:/$ cat /EVIDENCE
Congratulations, you found the clue!
The next clue is in: /opt/busybox/busybox-1.33.2/include/config/feature/ifconfig/memstart/ioaddr

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /opt/busybox/busybox-1.33.2/include/config/feature/ifconfig/memstart/ioaddr
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/include/config/feature/ifconfig/memstart/ioaddr$ ls
TIP  irq.h
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/include/config/feature/ifconfig/memstart/ioaddr$ cat TIP
Tubular find!
The next clue is in: /usr/share/X11/xkb

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/include/config/feature/ifconfig/memstart/ioaddr$ cd /usr/share/X11/xkb
hacker@commands~an-epic-filesystem-quest:/usr/share/X11/xkb$ ls
MESSAGE  compat  geometry  keycodes  rules  symbols  types
hacker@commands~an-epic-filesystem-quest:/usr/share/X11/xkb$ cat MESSAGE
Congratulations, you found the clue!
The next clue is in: /opt/pwndbg/.venv/lib/python3.8/site-packages/rpyc/utils
hacker@commands~an-epic-filesystem-quest:/usr/share/X11/xkb$ cd /opt/pwndbg/.venv/lib/python3.8/site-packages/rpyc/utils
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/rpyc/utils$ ls
MEMO         __pycache__        classic.py  helpers.py   server.py         zerodeploy.py
__init__.py  authenticators.py  factory.py  registry.py  teleportation.py
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/rpyc/utils$ cat MEMO
Lucky listing!
The next clue is in: /usr/share/racket/pkgs/htdp-lib/lang/private
hacker@commands~an-epic-filesystem-quest:/opt/pwndbg/.venv/lib/python3.8/site-packages/rpyc/utils$ cd /usr/share/racket/pkgs/htdp-lib/lang/private
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/htdp-lib/lang/private$ ls
INSIGHT            continuation-mark-key.rkt   provide-and-scribble.rkt   teach-module-begin.rkt  textbook-pls-spec.rkt
advanced-funs.rkt  create-htdp-executable.rkt  rewrite-error-message.rkt  teach-shared.rkt        todo.rkt
and-or-map.rkt     firstorder.rkt              set-result.rkt             teach.rkt               tp-dialog.rkt
beginner-funs.rkt  imageeq.rkt                 signature-syntax.rkt       teachhelp.rkt
compiled           intermediate-funs.rkt       sl-eval.rkt                teachprims.rkt
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/htdp-lib/lang/private$ cat INSIGHT
Congratulations, you found the clue!
The next clue is in: /usr/local/lib/python3.8/dist-packages/mpmath/calculus/__pycache__

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/htdp-lib/lang/private$ cat /usr/local/lib/python3.8/dist-packages/mpmath/calculus/__pycache__
cat: /usr/local/lib/python3.8/dist-packages/mpmath/calculus/__pycache__: Is a directory
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/htdp-lib/lang/private$ ls /usr/local/lib/python3.8/dist-packages/mpmath/calculus/__pycache__
LEAD-TRAPPED                  calculus.cpython-38.pyc         inverselaplace.cpython-38.pyc  polynomials.cpython-38.pyc
__init__.cpython-38.pyc       differentiation.cpython-38.pyc  odes.cpython-38.pyc            quadrature.cpython-38.pyc
approximation.cpython-38.pyc  extrapolation.cpython-38.pyc    optimization.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/htdp-lib/lang/private$ cat /usr/local/lib/python3.8/dist
-packages/mpmath/calculus/__pycache__/LEAD-TRAPPED
Yahaha, you found me!
The next clue is in: /usr/lib/x86_64-linux-gnu/gdk-pixbuf-2.0

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/htdp-lib/lang/private$ cd  /usr/lib/x86_64-linux-gnu/gdk-pixbuf-2.0
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/gdk-pixbuf-2.0$ ls
2.10.0  README  gdk-pixbuf-query-loaders
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/gdk-pixbuf-2.0$ cat README
Tubular find!
The next clue is in: /usr/local/lib/python3.8/dist-packages/traitlets/config

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/gdk-pixbuf-2.0$ cd  /usr/local/lib/python3.8/dist-packages/traitlets/config
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/traitlets/config$ ls -a
.   .NUGGET      __pycache__     argcomplete_config.py  loader.py   sphinxdoc.py
..  __init__.py  application.py  configurable.py        manager.py
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/traitlets/config$ cat /.NUGGET
cat: /.NUGGET: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/traitlets/config$ cat .NUGGET
Lucky listing!
The next clue is in: /usr/share/racket/pkgs/rackunit-lib/rackunit/private/compiled
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/traitlets/config$ cd /usr/share/racket/pkgs/rackunit-lib/rackunit/private/compiled
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/rackunit-lib/rackunit/private/compiled$ ls
BLUEPRINT           check-info_rkt.zo     equal-within_rkt.zo  location_rkt.zo    test-case_rkt.zo    test_rkt.zo
base_rkt.dep        check_rkt.dep         format_rkt.dep       result_rkt.dep     test-suite_rkt.dep  util_rkt.dep
base_rkt.zo         check_rkt.zo          format_rkt.zo        result_rkt.zo      test-suite_rkt.zo   util_rkt.zo
check-info_rkt.dep  equal-within_rkt.dep  location_rkt.dep     test-case_rkt.dep  test_rkt.dep
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/rackunit-lib/rackunit/private/compiled$ cat BLUEPRINT
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{gFACbllozUzHvi_cWyqq71g9oWz.QX5IDO0wCO1EzNzEzW}
```

## What I learnt
I have learnt how to efficiently use the cat ls and cd command to retrieve the flag. I followed the clues given by the pwn.college and the bash. One clue let to another and so on. I started off with cd'ing to the root directory, then listed all the files. I then kept reading the clues which led me to further directories to which I kept cd'ing to

## References
I have reffered to the video and the instructions mentioned to complete this challenge.

# 12. making directories
In this challenge, we are to explore the mkdir command to make new directories. Firstly mkdir is executed to make the /tmp/pwn directory and touch is used to make the /challenge file

## My solve
**pwn.college{IAQTHt2_qCycbF-g59FKLNqeFHC.QXxMDO0wCO1EzNzEzW}**

To solve this challenge, I first used the mkdir command to create the /tmp/pwn directory. I then used the touch command to make the /challenge file. To retrieve the flag, /challenge/run was executed.

```
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{IAQTHt2_qCycbF-g59FKLNqeFHC.QXxMDO0wCO1EzNzEzW}
```

## What I learnt
I have learnt how to use the mkdir command to create new directories. I've also then learnt to first cd into the new directory to  make a new file in it.

## References
I have reffered to the video and the instructions mentioned to complete this challenge.

# 13. finding files
In this challenge, we deal with the file command to find a specific file in a directory.

## My solve
**pwn.college{gFACbllozUzHvi_cWyqq71g9oWz.QX5IDO0wCO1EzNzEzW}**

To solve this challenge I first used the find command (find / -name flag) to list all the files named flag. I then started reading the files to retrieve the flag, ignoring the ones saying "permission denied"

```
hacker@commands~finding-files:~$ find / -name flag
find: ‘/tmp/tmp.TpSOPGOVKK’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/share/locale/kv/LC_MESSAGES/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/root’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/nix/store/ka6xbd6z6wj5d6frl7ym4nzfc6p2wkdx-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/f31j0igg7ms3yrj5gm3cm76bjcmdl8w5-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/n6vb30rd7kkwjj595pgm0dmsmfaqi6i5-rizin-0.7.3/share/rizin/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/8qvj9mzdq2qxgjigw4ysqgbkcx1zi80y-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/dz2qxywk6d8hc1gkarpwbhyxb50sh2ak-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ cat /nix/store/f31j0igg7ms3yrj5gm3cm76bjcmdl8w5-python3.12-pwntools-4.13.1/lib/python3.
hacker@commands~finding-files:/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/flag
cat: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag$ cat /usr/share/l
ocale/kv/LC_MESSAGES/flag
pwn.college{U4motvGsRGymlDou25lCH2oCHhr.QXyMDO0wCO1EzNzEzW}
```

## What I learnt
I have learnt how to use the find command to find a given file in a directory.

## References
I have reffered to the video and the instructions mentioned to complete this challenge.

# 14. linking files
In this challenge,
