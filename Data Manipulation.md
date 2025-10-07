# 1. Transalating Characters
In this challenge, we learn how to modify characters using the tr command either to replace one letter with another or to interchange capital letters with small ones.

## My solve
**pwn.college{MWa4yC8PMD2ZtEGjxfkXy1FvfEI.01MxEzNxwCO1EzNzEzW}**

To solve this challenge, I first wrote the /challenge/run followed by | with the tr command to interchange ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz with abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ

```
hacker@data~translating-characters:~$ /challenge/run | tr ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
yOUR CASE-SWAPPED FLAG:
pwn.college{MWa4yC8PMD2ZtEGjxfkXy1FvfEI.01MxEzNxwCO1EzNzEzW}
```

## What I learnt
I have learnt the proper use of the tr command, how to interchange letters or change their case using the command.

## References
The pwn.college instructions have helped me solve the challenge.

# 2. Deleting Characters
In this challenge, we learn how to delete characters using the tr -d command.

## My solve
**pwn.college{4_eMS3-9cFSkUKNYHG05mzMEId5.0FNxEzNxwCO1EzNzEzW}**

To solve this challenge, I wrote the /challenge/run and used the tr -d command to delete the ^ and % characters from the flag.

```
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^%
Your character-stuffed flag:
pwn.college{4_eMS3-9cFSkUKNYHG05mzMEId5.0FNxEzNxwCO1EzNzEzW}
```

## What I learnt
I have learnt how to use the tr -d command to delete desired characters from an output.

## References
The pwn.college instructions have helped me solve the challenge.


# 3. Deleting Newlines
In this challenge, we learnt the new line command \n and executed how to delete them in this case.

## My solve
**pwn.college{sk3Tn1mf0o7os8NeCErSFvYKr9z.0VNxEzNxwCO1EzNzEzW}**

To solve this challenge, I first used the tr -d command with the _"\n" to delete the extra lines to retrieve the flag.

```
hacker@data~deleting-newlines:~$ /challenge/run | tr -d _"\n"
Your line-split flag: pwn.college{sk3Tn1mf0o7os8NeCErSFvYKr9z.0VNxEzNxwCO1EzNzEzW}
```

## What I learnt
I have learnt the _"\n" to input a new line because generally enter executes the command. I also learnt that the /n must always be in double quotes to ensure it is not read instead.

## References
The pwn.college instructions have helped me solve the challenge.


# 4. Extracting the first lines with head
In this challenge, we learn how to only display the first few(default 10) lines of an input. We can specify how many lines we require using the -n command.

## My solve
**pwn.college{oWS9J4Nrp_C6_L065XKP-gWwuhN.0lNxEzNxwCO1EzNzEzW}**

To solve this challenge, I first displayed the first 7 lines of the /challenge/pwn command by using head -n 7 then piped it onto /challenge/college

```
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{oWS9J4Nrp_C6_L065XKP-gWwuhN.0lNxEzNxwCO1EzNzEzW}
```

## What I learnt
I have learnt how to display the first few lines of an output using the head command and how to use -n to specify the number of lines you want displayed.

## References
The pwn.college instructions have helped me solve the challenge.

# 5. Extracting specific sections of text
In this challenge, we learn how to extract specific columns using the cut command. 

## My solve
**pwn.college{Egd7JiJ62Et0IuQrSgbodjhAhsx.01NxEzNxwCO1EzNzEzW}**

To solve this challenge, I first ran the /challenge/run to determine the column I am to display which was 2. I then executed /challenge/run | cut -d " " -f 2. I then used tr -d "\n" to delete extra lines

```
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run
16428 p
7623 w
8210 n
15583 .
31177 c
7792 o
32707 l
29419 l
13432 e
26340 g
14772 e
4802 {
16403 E
15466 g
31610 d
13811 7
4243 J
25329 i
27281 J
3586 6
17494 2
2370 E
21609 t
29418 0
6810 I
7703 u
6887 Q
28929 r
12615 S
16642 g
5852 b
25453 o
11066 d
4359 j
1374 h
24244 A
11361 h
11511 s
5673 x
32093 .
25835 0
14828 1
21340 N
28921 x
2036 E
21722 z
20438 N
1494 x
20194 w
25498 C
10633 O
8010 1
13478 E
6807 z
28464 N
16437 z
23830 E
26996 z
17853 W
7157 }
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 | tr -d "\n"
pwn.college{Egd7JiJ62Et0IuQrSgbodjhAhsx.01NxEzNxwCO1EzNzEzW}
```

## What I learnt

## References
The pwn.college instructions have helped me solve the challenge.


# 6. Sorting data
In this challenge, we learn how to sort files in a given input and output them in a given order.

## My solve
**The pwn.college instructions have helped me solve the challenge.**

To solve this challenge, I used the sort command using the -u argument which arranges all the unique lines and separates the duplicates.

```
hacker@data~sorting-data:~$ sort -u /challenge/flags.txt
ovm.colkegd{cFHacFlK6XdE5alvQvNEigUS9n-.0FM0MDOxvCO0DyMyDyW}
ovn.bnllefe{cGHadFkJ6XeE4alvQvNEihUR9m-.0FL0MCOxwCO0EyNzEzW}
ovn.bokldfd{cGHacFlK6XdD5blvPvMEihUS9m-.0FM0MDNxwCO1EyNyEzW}
ovn.cnkldgd{bFHacFlK6XeD5alvQuMEhgTR9m-.0FM0MCOxvCN1EzNyEzW}
ovn.cnklege{cGGadFkK6XeD5blvPvNEihUS9n-.0FM0MDNwwCN1DzMzDzV}
ovn.cnllege{cFHadFlK6XeE5bkvQvNEihUS9n-.0FM0MDOxwBO1DzNyDzW}
owm.bokkegd{cFHadFlJ6XeD5blvQuNEhhTR8n-.0FL0MDOxwCO0EzNzEzW}
owm.bolkege{cGHacElK5XeE5alvPvMEihUS9n-.0FL0MDNwwBO0EzNzEyW}
owm.cnkkdfe{bGHadFkK6WeE5alvQvMDhhUS9n-.0FL0MDNxwCN1EyNzDzV}
owm.cnkkegd{cGHacElK6XdE4bluQvNEhhUR8m-.0EM0LDOxwCN1EzNzEzV}
owm.cnllege{cFGadFlK6WeD4bluQvNDigUS9m-.0EM0MDOxwCO1EzNzEyW}
owm.cokkegd{cGHacFkJ5XeE4blvQvNEigUS9n-.0EM0LDNxwCO1EzMyEzW}
owm.colkege{cGHadElK5XeD5bluPuMEihTS9m-.0FL0MDOxwCO1EzMyEyW}
owm.colldge{bGHadFlK6XeD5alvPvNDhhTS9n-.0EL0LDOxwBO1EzMzEyW}
owm.collegd{bGGadFlJ6XeE4blvQvNEhhUS9n-.0FM0MDOwwCO1DzMzEzW}
owm.collegd{bGGadFlK6WeE5blvQvNEihUS9n-.0FM0MDOwwCO1EzMzEzW}
own.bnlldge{cGHadFlK5XdE5bkvQvMEihTS9m-.0FM0LCNwvBN1DzNyEzV}
own.cnkldgd{bGHadElK5XeE5alvQuMDhgUR9n-.0EL0MDNwwBO1DzNzEyW}
own.cnklegd{cFHadFlJ6XeE5alvQvNDigUS9m-.0FM0LCNwwBN0EzNzDzV}
own.cnlldge{cGHadFkK5XdE4akuQuMEigUS9n-.0FL0MCOxvCN1EzNzDyV}
own.cokkege{cGHacFlK6XdE5bluPvNEigUS9m-.0FL0MDOxvCO1DyMzEzW}
own.coklege{bGHadFlJ6XeD5alvQuNEhhUS8n-.0FM0MCOxwBO1EzNzEzV}
own.coklege{cGHadFlK6XdE5blvQvNEigUS9m-.0FM0MCOwwCO1EzNzEzW}
own.colkdgd{cFHadFkK6XeE5bluQvMEihUS9n-.0EM0MCNxwCO1EzMzEzV}
own.collegd{cFGadFlJ5XeD5bkvQvMEihUS9m-.0FL0LDOwvCO0EzNyEzV}
own.college{bGHacElK5XeD5blvQvNEihUR9n-.0FM0MDNxwCO1DzMzEzW}
own.college{cGGadFkK6XeE5blvPvNDihTS9n-.0FL0LDOxwCO1EzNzDzV}
own.college{cGHadFlK6XeE4blvQvNEihUS9n-.0FM0MCOxwCO1EzNzEzW}
own.college{cGHadFlK6XeE5blvQvNEigUS9n-.0FM0MDOxwCO1DzNzEzW}
pvm.bollegd{bGGadFlK5XdD5blvPvNEihTS8m-.0FM0MDNxvBO1EyNyDyW}
pvm.colldfe{cGHadFlK6XeE4blvQvNEigUR9m-.0EM0MDNxwBO1EyNyEzW}
pvn.bnklege{bGGadFlJ6XdE5bkuQvMEihUR9m-.0FM0LDOxwCO1EyNzEzW}
pvn.bolkdgd{cGHadFlK5XdE5blvQvNDihUS8m-.0FL0MCNxvBO1DzNzEzW}
pvn.bollegd{cFGadFkJ5XeE5akuQvNEihUR9n-.0EM0MCNxwBO0EzNzEyV}
pvn.cnkldgd{cFGadFlK6WdE4bkvQvMEihTR9n-.0FM0MCOxwCN0EyNzEzW}
pvn.cnlldge{cGHacFlK6XeE5akuQvNDhgTR9n-.0FM0MCOxwCO1EyNzEzW}
pvn.cnllege{cGHacFlK6XeE4akvQvNEihTR9m-.0FL0MDOxwCN0DzNzEzW}
pvn.cnllege{cGHadFlJ6XdE5akuQvNEigUS9m-.0FM0MDOxwBO1EzNzEzW}
pvn.cnllege{cGHadFlK6XeE4blvPvNEhhUR9n-.0FM0LDNxwBN1DzMzDzW}
pvn.cokldge{cGHacFlK6XeE4bluQvNDihUS9n-.0EM0MDNwwBN1EzNzEzW}
pvn.collegd{cFHacElK5XeE5blvQvNEihUR9n-.0FM0LDNxwCO1DyNzEzV}
pvn.college{bGHadFkK5XdD5blvPvNEigUR8n-.0FL0MCOxvBN1EzMzEzV}
pvn.college{cGGadFlK6XeE5blvQvNEhhUS9n-.0EM0MDOxwCN1EzNzEzW}
pwm.bnlkdfd{cGHadElK5WeD5blvPvNEhgUR9n-.0FM0MDOwwCN0EyMyDyW}
pwm.bolldge{bGHacFlJ6XdE5alvPuNEihUS9n-.0FL0MDOxwBO1EyNzEzW}
pwm.cnkkege{bGHadFlK6WeE5alvQuNEhhUS8n-.0FM0MDOwwCN0EzMzEzW}
pwm.cnklege{bGHacElK5XeE5akuQvNEhhUR9n-.0FM0MDOwwCO0EzMzDzW}
pwm.coklege{bGHadFlK6WeD5blvQvNEihUS9n-.0FM0MDOxwCO1EzNzEyW}
pwm.coklege{cGHadFlK6XdE5alvPvNEihUS9n-.0FM0MDOxwCO1EzNzEzV}
pwm.colldgd{cGGadFlK6XeE4bkvQvMDhhUS8m-.0EM0MDOwwBN1EzNzDzW}
pwm.collefe{cGGadFlK6WeE5bluQvMEihUR9n-.0FM0MDOxvCO1EzNzEzW}
pwm.collegd{cGHadFkK5XdE5blvQvMEihUR9n-.0FM0MCOxwCO1EzMyDyV}
pwm.college{bFHadFlK5XdE5aluQvNEihUS8n-.0EM0MDOxwCO0EyNzEyW}
pwn.bnlkdgd{cGGadFlJ6XeD5bkvPvMEigUR9n-.0FM0MDOxvCO0EzNzEzV}
pwn.bnllege{cGHadFlK6XeE5blvQvNEihTS8n-.0EM0LDOxvBO0DzMyEzW}
pwn.bokldge{cGHadFlK6XeD5blvQvNDihUR8n-.0FM0MDNxwCO1EzNyEyW}
pwn.boklefe{cGHadElK5XeE4bkvQvNEihTS8n-.0FM0MCOxwCO1DzNzEzW}
pwn.bolldge{bGHadEkK6XeE5blvQuNEihUR9n-.0FM0MDOxwCO1EzNzEzV}
pwn.bollefe{cGHadFlK6XeE5blvQvNEihUS9n-.0FM0MDOxwCO0EzNzEzW}
pwn.bollege{bFHadFlK6XeE5blvQvNEihUS8n-.0FM0MDOxwCO1EzNzEzW}
pwn.bollege{cFHacFlK6XdE4bkuQvMDigTS9n-.0FM0LCOxvCO0DzNzDzW}
pwn.bollege{cGGadFlK6XeE4blvQvNEihUS8n-.0FM0MDOxwCO1DzNzEzV}
pwn.bollege{cGHadFlK6XeD5bluQvNEihUS9m-.0FL0MDOxwCO1EzMyEzV}
pwn.cnkkdge{bFGacFlK6WeE4blvQvNEhhUS8n-.0FM0MDOwvCO0EzMzEzV}
pwn.cnkldfe{cGHadFlK6XeE5bluQvNEigUS9n-.0FM0MDOwvBO1EzNzEzW}
pwn.cnklegd{bGHadFkJ6XdD5aluPvNEigUR9n-.0FM0MCOwwCO0EyNzEyW}
pwn.cnklege{bGHadElJ6XeD4blvPvMDihUS8n-.0EM0MDOwwBO0EyMzEzW}
pwn.cnlkdge{cFHadEkK6WeE5blvQvNEihUS9n-.0FL0MDOxwCO0EzMzEzW}
pwn.cnlkegd{cFHadElK5XeE5blvQvNDigTR9n-.0EM0MDOxwBN0DzNzEzW}
pwn.cnlldge{cGGacFkK6XdD5blvPvNDihUS9n-.0FM0MDNxwCO1EzNzEzW}
pwn.cnlldge{cGHadElK6WdE5blvPuMDhhUS8n-.0FM0MCOxwCO0EzMzEzW}
pwn.cnllefd{cFHacElK6WeE4aluQuMDhhTS9n-.0FL0MCOxwBO1DzNyEzV}
pwn.cnllege{cGGacElK6XeE4akvQvNDihUS9n-.0FL0MDNxvBO1EzNyEyW}
pwn.cnllege{cGHadElK6WeE5blvQuNEihUS9n-.0FM0MDOxwCO0EzNzEzW}
pwn.coklege{cGHadElK6XeE5blvQvNEhhUS9n-.0FM0MDOxwCO1EzNzEzW}
pwn.colkefe{cFHacFlK6XeE4bkvQvNEihUS9n-.0FM0MDOwvCN1DyNzEyW}
pwn.colldfd{cFHadFlK6XdE5blvQvMEihTS9n-.0FM0MDNwwCN1EzNzEzW}
pwn.colldge{cGHadFlK6XdE4blvQvNEihUS9n-.0FM0LDOxwCO1EzNzEzV}
pwn.collefe{cGHadFlK6XeE5blvQvNEigUS9n-.0FM0LDOxwCO0DzNzEzW}
pwn.college{bFHadEkJ6WdE4akvQvNEhhUS8n-.0EL0LCNwwCN0EzMzDzW}
pwn.college{bGHadFlK6XeD5blvPuNDhhTS9n-.0FM0MCOxwCN1EyNzEyW}
pwn.college{bGHadFlK6XeD5blvQvNEhhUS9n-.0FL0MDOxwCO1EzNzEyW}
pwn.college{bGHadFlK6XeE5blvQvNEihUS9m-.0FM0MDOxwCO1EzNzEyV}
pwn.college{cFHadFlK6XeD5alvQvMDihUS9n-.0FM0MCOxwCO1EzNzEzW}
pwn.college{cGGadFlJ6XeE4blvQvNEhhUS9n-.0FL0MDOxvCO1EzNzEzW}
pwn.college{cGHacFlK6XeE4blvQvNEihUS9n-.0FM0MDOxwCO1EzNzEzW}
pwn.college{cGHadElJ5XeE5bluPvMEihUS9n-.0FM0MDOxwCN1EzNyDzW}
pwn.college{cGHadFlJ6XdE5blvQvNEihUS8n-.0FM0MDOxwCO0EzNzEzW}
pwn.college{cGHadFlK5XeE5blvQvNEihUS8n-.0FM0MDNxwCN1EzNzDzW}
pwn.college{cGHadFlK6XdE5blvQvNEihUS9n-.0FM0MDOxwCO1EzNzEzW}
pwn.college{cGHadFlK6XeE4blvPvNEihTS9n-.0FM0MDNxwBO1EzNzEzW}
pwn.college{cGHadFlK6XeE4blvQvNEihUS9m-.0FL0MDNxwCO1DzNzEzW}
pwn.college{cGHadFlK6XeE5blvQuNEihUS9n-.0FM0MDOxwCO0EzNzEzW}
pwn.college{cGHadFlK6XeE5blvQvMEihUS9m-.0FM0MDOxwCO1DzNzEzW}
pwn.college{cGHadFlK6XeE5blvQvMEihUS9n-.0FM0MDOxwCO1EzNzEzW}
pwn.college{cGHadFlK6XeE5blvQvNEihUS9m-.0FM0MDOxwCO1EzMzEzW}
pwn.college{cGHadFlK6XeE5blvQvNEihUS9n-.0FM0MDOxvCO1EzNzEzV}
pwn.college{cGHadFlK6XeE5blvQvNEihUS9n-.0FM0MDOxvCO1EzNzEzW}
pwn.college{cGHadFlK6XeE5blvQvNEihUS9n-.0FM0MDOxwCN1EzMzEzW}
pwn.college{cGHadFlK6XeE5blvQvNEihUS9n-.0FM0MDOxwCO1EyNzEzW}
pwn.college{cGHadFlK6XeE5blvQvNEihUS9n-.0FM0MDOxwCO1EzNzEzW}
```

## What I learnt
I learnt the different arguments, -r: reverse order (Z to A), -n: numeric sort (for numbers), -u: unique lines only (remove duplicates), -R: random order!

## References 
The pwn.college instructions have helped me solve the challenge.
