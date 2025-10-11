# 1. Chaining with semicolons
In this challenge, they asked us to run the /challenge/pwn and then /challenge/college, chaining them with a semicolon.

## My solve
**pwn.college{0PrMOnyC4MJfBEi7NcuX7ke2NUe.QX1UDO0wCO1EzNzEzW}**

To solve this challenge, I ran /challenge/pwn and /challenge/college programs chained with a semicolon (;) to get the flag.

```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{0PrMOnyC4MJfBEi7NcuX7ke2NUe.QX1UDO0wCO1EzNzEzW}
```

## What I learnt
I learned that we can chain commands with a semicolon (;). In most contexts, ; separates commands in a similar way to how Enter separates lines.

## References
I have used the pwn.college instructions to solve this challenge.

# 2. Building on success
In this challenge, they asked us to chain the programs /challenge/first-success and /challenge/second using the "&&" operator.

## My solve
**pwn.college{MozimqtmCWLHTGAlpnSdmKCZSC0.0lM0MDOxwCO1EzNzEzW}**

To solve this challenge, I first ran /challenge/first-success along with the AND operator (&&) and /challenge/second (/challenge/first-success && /challenge/second) to get the flag. 

```
hacker@chaining~building-on-success:~$ /challenge/first-success
hacker@chaining~building-on-success:~$ echo $?
0
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{MozimqtmCWLHTGAlpnSdmKCZSC0.0lM0MDOxwCO1EzNzEzW}
```

## What I learnt
I learned about the "&&" operator. It allows us to run a second command only if the first command succeeds (in Linux convention, this means it exited with code 0). syntax: "command1 && command2", this means run command1, and if it succeeds then run command2.  

## References
I have used the pwn.college instructions to solve this challenge.

# 3. Handling failure
In this challenge, we are asked us to chain the programs /challenge/first-failure and /challenge/second using the OR operator (||).

## My solve
**pwn.college{oFzMxUjNiyiC3_UpjbV1j0c3BIv.01M0MDOxwCO1EzNzEzW}**

To solve this challenge, I first ran /challenge/first-failure along with the OR operator (||) and /challenge/second (/challenge/first-failure || /challenge/second) to get the flag. 

```
hacker@chaining~handling-failure:~$ /challenge/first-failure
hacker@chaining~handling-failure:~$ echo $?
1
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{oFzMxUjNiyiC3_UpjbV1j0c3BIv.01M0MDOxwCO1EzNzEzW}
```

## What I learnt
I learned about the OR (||) operator. It allows us to run a second command only if the first command fails (in Linux convention, this means it exited with a non zero code ). syntax: "command1 || command2", this means run command1, and if it fails then run command2.  

## References
I have used the pwn.college instructions to solve this challenge.

# 4. Your first shell script
In this challenge, they told us to run /challenge/pwn and then /challenge/college, but in a shell script, and then run it with bash to get the flag. 

## My solve
**pwn.college{gAvcF8YBBTibRuBT1HB9FxkgDkl.QXxcDO0wCO1EzNzEzW}**

To solve this challenge, I used nano command to create a shell script named x.sh, and inside nano i typed /challenge/pwn && /challenge/college. I then launched x.ch using bash command in the main terminal and got the flag. 
 

```
hacker@chaining~your-first-shell-script:~$ nano x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{gAvcF8YBBTibRuBT1HB9FxkgDkl.QXxcDO0wCO1EzNzEzW}
```

## What I learnt
I learned how to make a shell script. They generally end with .sh and Linux has nano, which is a commandline text editor which we can use to make or edit shell scripts. To open a shell script in nano, we have to type "nano FILENAME" on the commandline. We have to use bash command to execute the file. When we use bash command, the shell reads commands from the file rather than the user.  

## References
I have used the pwn.college instructions to solve this challenge.


# 5. Redirecting script output
 In this challenge, they told us create a script that calls the /challenge/pwn command followed by the /challenge/college command, and pipe the output of the script into a single invocation of the /challenge/solve command. 

 ## My solve
 **pwn.college{gy8bXDFJT-65Jt13xS9mELzSa_S.QX4ETO0wCO1EzNzEzW}**

 To solve this challenge, I used nano command to create a shell script named x.sh, and inside nano I typed /challenge/pwn and /challenge/college, on two different lines. Then i connected the output of the shell script using bash (bash x.sh) to the input of /challenge/solve using pipe (|) operator and got the flag.  

```
hacker@chaining~redirecting-script-output:~$ nano x.sh
hacker@chaining~redirecting-script-output:~$ bash x.sh
It looks like you are not piping this script out to /challenge/solve! Remember
to pipe the output of your script into /challenge/solve using '|'.
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{gy8bXDFJT-65Jt13xS9mELzSa_S.QX4ETO0wCO1EzNzEzW}
```

## What I learnt
I learned that for the shell, the shell script is just like another command. So we can redirect its input and output with various methods we learned in previus modules like >,|.2>,<,>>,etc.  

## References
I have used the pwn.college instructions to solve this challenge.

# 6. Executable shell sccripts
In this challenge, they told us to create a script that will invoke the /challenge/solve, make it executable, and then run it without invoking bash to get the flag. 

## My solve
**pwn.college{MVDyfXw4q-X0u-PkkS2HX4C9GNd.QX0cjM1wCO1EzNzEzW}**

To solve this challenge, I used nano command to create a shell script named x.sh, and inside nano I typed /challenge/solve. I then changed the permissions of the file to allow the user (that is me) to execute the file using chmod u+x. I then executed the x.sh file to get the flag. 

```
hacker@chaining~executable-shell-scripts:~$ nano x.sh
hacker@chaining~executable-shell-scripts:~$ ./x.sh
bash: ./x.sh: Permission denied
hacker@chaining~executable-shell-scripts:~$ chmod u+x ./x.sh
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{MVDyfXw4q-X0u-PkkS2HX4C9GNd.QX0cjM1wCO1EzNzEzW}
```

## What I learnt
I learned that we can directly execute the shell script files, if we have executable (x) permissions for that.   

## References
I have used the pwn.college instructions to solve this challenge.

# 7. Understandinf Shebangs
In this challenge, they asked us to create a script at /home/hacker/solve.sh that has a proper shebang and outputs "hack the planet". We had to make it executable, then run /challenge/run to verify your script works correctly to get the flag.

## My solve
**pwn.college{MIgbPEsp43Cotj3yLzF4fScspP6.0VOzMDOxwCO1EzNzEzW}**

To solve this challenge, I used nano command to create a shell script named solve.sh. Inside the shell script, I kept the shebang as #!/bin/bash as its a bash script and typed echo "hack the planet". I then made it executable using chmod command and then ran /challenge/run to get the flag. 

```
hacker@chaining~understanding-shebangs:~$ nano solve.sh
hacker@chaining~understanding-shebangs:~$ chmod u+x ./solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{MIgbPEsp43Cotj3yLzF4fScspP6.0VOzMDOxwCO1EzNzEzW}
```

## What I learnt
I learned about shebangs. They start with #!. There are a bunch of different types of programs, but if the program file starts with the characters #!, Linux treats the file as an interpreted program, and the contents of the rest of the line as the path to the interpreter. It then invokes the interpreter with the path to the program file as its only argument. The shebang line must be the VERY FIRST line of the file - no blank lines or spaces before it. Common shebangs:

## References
I have used the pwn.college instructions to solve this challenge.

# 8. Scripting with arguments
In this challenge, we are to take 2 inputs and swap them using the echo command. Inside the shell script, I assigned the value of $2 to $1 using the echo command to reverse and output.

## My solve
**

To solve this challenge, I echoed the value of $2 to $1 inside the shell script. I then ran the /challenge/run to get my flag.

```
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{8p9CzXnw-EsOhUNQwww76RsbQRz.0VNzMDOxwCO1EzNzEzW}
```

## What I learnt
I learnt how to effectively execute shell script and swap values to get the output.

## References
I have used the pwn.college instructions to solve this challenge.


# 9. Scripting with conditionals
In this challenge, they told us to make a script such that it takes 1 argument, and if the argument is pwn, then it outputs college, and for any other input it outputs nothing. Once the script is done they asked us to run /challenge/run to get the flag.

## My solve
**pwn.college{crsKVxBpLXPOplQvpU3B7DBBhE7.0lNzMDOxwCO1EzNzEzW}**

To solve this challenge, I executed an if statement saying that if input is pwn, then echo college.

```
hacker@chaining~scripting-with-conditionals:~$ nano solve.sh
hacker@chaining~scripting-with-conditionals:~$ chmod u+x ./solve.sh
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{crsKVxBpLXPOplQvpU3B7DBBhE7.0lNzMDOxwCO1EzNzEzW}
```

## What I learnt
I learnt how to effectively use the if statement for bash and executing desired outputs.

## References
I have used the pwn.college instructions to solve this challenge.

# 10. Scripting with default cases
In this challenge, we are to execute an if else statement. If the input is pwn, we output college, else "nope"

## My solve
**pwn.college{4Umx0uxma0x-f8nhw67wYB_4Y4N.01NzMDOxwCO1EzNzEzW}**

To solve this challenge, I first executed the if statement, to echo college when input is pwn, else echo nope

```
hacker@chaining~scripting-with-default-cases:~$ nano solve.sh
hacker@chaining~scripting-with-default-cases:~$ chmod u+x ./solve.sh
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{4Umx0uxma0x-f8nhw67wYB_4Y4N.01NzMDOxwCO1EzNzEzW}
```

## What I learnt
I learnt how to properly execute an if else statement to get the desired output.

## References
I have used the pwn.college instructions to solve this challenge.

# 11. Scripting with multiple conditions
In this challenge, they told us to make a script such that it takes 1 argument, if the argument is pwn, then it outputs college, if the argument is "hack", then it outputs "the planet", if the argument is learn, then it outputs linux and for any other input it outputs unknown. Once the script is done they asked us to run /challenge/run to get the flag.

## My solve
**pwn.college{kHtYRxhvfnTw3GsZIdDohwTnhTz.0FOzMDOxwCO1EzNzEzW}**

To solve this challenge, I used nano command to create a shell script named solve.sh, and inside nano i typed the script for the given conditions. Then i ran /challenge/run to get the flag.  

```
hacker@chaining~scripting-with-multiple-conditions:~$ nano solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ chmod u+x ./solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
pwn.college{kHtYRxhvfnTw3GsZIdDohwTnhTz.0FOzMDOxwCO1EzNzEzW}

nano:
if [ "$1" == "hack" ]
then
echo "the planet"
elif [ "$1" == "pwn" ]
then
echo "college"
elif [ "$1" == "learn" ]
then
echo "linux"
else
echo "unknown"
fi
```

## What I learnt
I learned that we can also use elif (else if) in bash script. Syntax is same as if. We need to keep then over here also.

## References
I have used the pwn.college instructions to solve this challenge.


# 12. Reading shell scripts
In this challenge, they told us that /challenge/run is a shell script, that requires you to put in a secret password, but that password is hardcoded into the script iself. They asked us to read the script, find the password and then get the flag.

## My solve
**

To solve this challenge, I first read the script of /challenge/run using cat command. Then i found the password, which was hack the PLANET. I ran /challenge/run, entered the password, and got the flag.

```

```

