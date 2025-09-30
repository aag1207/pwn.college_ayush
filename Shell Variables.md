# 1. Printing Variables
In this challenge, we are to learn how to print variables. We can use the echo command with a $ sign to print variables and retrieve the flag in this case.

## My solve
**pwn.college{c0P4u6F2u465O9R1DLFbh4qHm9S.QX3UTN0wCO1EzNzEzW}**

To solve this challenge, I executed the echo command followed by a $ sign with the variable "FLAG". I first wrote flag instead of FLAG which did not give me the flag.

```
hacker@variables~printing-variables:~$ echo $flag

hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{c0P4u6F2u465O9R1DLFbh4qHm9S.QX3UTN0wCO1EzNzEzW}
```

## What I learnt
I have learnt how to print variables using the $ command and that many other commands can be used other than echo.

## References
https://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html and the pwn.college instructions.

# 2. Setting Variables
In this challenge, we learn how to assign values to variables using the = sign.

## My solve
**pwn.college{ADR28pqEhkE5vEXc6v_b1s4N_JV.QX5UTN0wCO1EzNzEzW}**

To solve this challenge, I used the = sign to assign the value of COLLEGE to PWN which led me to my flag.

```
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{ADR28pqEhkE5vEXc6v_b1s4N_JV.QX5UTN0wCO1EzNzEzW}
```

## What I learnt
I have learnt how to assign values to variables using the = sign. Also, note that there are no spaces between the variable, equal to sign, and the value being assigned. They are ALL case sensitive.

## References
https://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html and the pwn.college instructions.

# 3. Multi-word variables
In this challenge, we learn how to assign a multi-word value to a varible containing spaces in between.

## My solve
**pwn.college{g6TZ4jj33ZxtHhsELtfhR0SzGKZ.QXwYTN0wCO1EzNzEzW}**

To solve this challenge, I assigned the value "COLLEGE YEAH" to the variable PWN using double quotes since it was a 2 word assignment.

```
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
```

## What I learnt
I have learnt how to assign a multi word value to a variable using double quotes.

## References
https://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html and the pwn.college instructions.

# 4. Exporting Variables
In this challenge, we learn how to export variables. Generally, without exporting, the value assigned to the variables do not carry forward to the child programs within. On exporting them, they do.

## My solve
**pwn.college{oYHUidqD0TP5dZdCvRLkfVGwcpA.QXyYTN0wCO1EzNzEzW}**

To solve this challenge, I assigned the value COLLEGE to the variable PWN and exported it. I then assigned the value PWN to the variable COLLEGE without exporting it. I then ran /challenge/run to retrive the flag.

```
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
Incorrect...
You have not set the COLLEGE variable to the correct value (it should be
'PWN'). Do that before running this script! Even though it is not exported, in
this challenge, we have ways to check...
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great
job! Here is your flag:
pwn.college{oYHUidqD0TP5dZdCvRLkfVGwcpA.QXyYTN0wCO1EzNzEzW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```

## What I learnt
I learnt how to export values assigned to variable if you want them to remain assigned through many programs using "export".

## References
https://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html and the pwn.college instructions.


# 5. Printing exported variables
In this challenge, we learn to print all the exported variables in a shell using the env command.

## My solve
**pwn.college{c9Rzft5AMCn2yj0QQHRWqDHu9Tp.QX4UTN0wCO1EzNzEzW}**

To solve this challenge,

```
hacker@variables~printing-exported-variables:~$ env $FLAG
env: ‘pwn.college{c9Rzft5AMCn2yj0QQHRWqDHu9Tp.QX4UTN0wCO1EzNzEzW}’
```

## What I learnt

## References
https://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html and the pwn.college instructions.


# 6. Storing Command Output
In this challenge, we learn how to assign the output of a program to a variable using ().

## My solve
**pwn.college{YMOMEuKaTB8AKCpH6eOOMzYnh3N.QX1cDN1wCO1EzNzEzW}**

To solve this challenge, I assigned the output of /challenge/run to the variable PWN then read it using echo $PWN

```
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{YMOMEuKaTB8AKCpH6eOOMzYnh3N.QX1cDN1wCO1EzNzEzW}
```

## What I learnt
I have learnt how to assign the output of a program to a variable using ().

## References
https://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html and the pwn.college instructions.

# 7. Reading Input
In this challenge, we learn how to read an input from the user which reads the input into the variable

## My solve
**pwn.college{0_jki9d2vADgQjxIpSQeOosZmOf.QX4cTN0wCO1EzNzEzW}**

To solve this challenge, I first executed read -p "INPUT:COLLEGE" PWN and then assigned COLLEGE to PWN to retrieve the flag.

```
hacker@variables~reading-input:~$ read -p "INPUT:COLLEGE" PWN
INPUT:COLLEGE
hacker@variables~reading-input:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{0_jki9d2vADgQjxIpSQeOosZmOf.QX4cTN0wCO1EzNzEzW}
```

## What I learnt
I have learnt how to read the input given by us and assign it to the variable using "read".

## References
https://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html and the pwn.college instructions.

# 8. Reading Files
In this challenge, we learn how to read files excluding extra steps.

## My solve
**pwn.college{gfgMtM9gfwsJ1HhNRJkh-YTVxr9.QXwIDO0wCO1EzNzEzW}**

To solve this challenge, I read the /challenge/read_me file to VAR which basically read the file to retrieve the flag.

```
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{gfgMtM9gfwsJ1HhNRJkh-YTVxr9.QXwIDO0wCO1EzNzEzW}
```

## What I learnt
I have learnt how to read files directly into a variable through the read command.

## References
https://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-5.html and the pwn.college instructions.







