# Digesting Documentation

**Date:** 27 Sep 2025
**Author:** Vedant Lohan

# Learning From Documentation
The challenge asks us to execute the program /challenge/challenge using proper argument.

## My solve
**Flag:** `pwn.college{gXz8AV9poZpeB9GBeX-6O2wlRps.QX0ITO0wSM3kjNzEzW}`

To run the program with the proper argument --giveflag, we type in /challenge/challenge followed by the argument that is --giveflag.

```bash
hacker@man~learning-from-documentation:~$  /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{gXz8AV9poZpeB9GBeX-6O2wlRps.QX0ITO0wSM3kjNzEzW}
```

## What I learned
I learned that to properly execute big programs, we need to specify the right arguments.

## References 
none

# Learning Complex Usage
The challenge asks us to find the flag using a program /challenge/challenge which allows you to print arbitrary files to the terminal, when given the --printfile argument. The argument to the --printfile argument is the path of the flag to read.

## My solve
**Flag:** `pwn.college{4GSSteiMABnxgvVmYHw1shbXVrf.QX1ITO0wSM3kjNzEzW}`

The flag stays in /flag. To print it we use the /challenge/challenge --printfile followed by the path that is /flag

```bash
hacker@man~learning-complex-usage:/$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{4GSSteiMABnxgvVmYHw1shbXVrf.QX1ITO0wSM3kjNzEzW}
```

## What I learned
I learned that usage of some commands can get complex and even arguments can have their own arguments.

## References 
none

# Reading Manuals
The challenge asks us to use the man command to understand how to use /challenge/challene to print the flag.

## My solve
**Flag:** ` pwn.college{EI16P4tXZnFDO1KWa1p8FkZXsa4.QX0EDO0wSM3kjNzEzW}`

First we read the manual of challenge using man challenge. Now we see that,
```bash
--tnapks NUM
              print the flag if NUM is 164
```
To print the flag we must give the argument --tnapks 164 to /challenge/challenge,so

```bash
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --tnapks 164
Correct usage! Your flag: pwn.college{EI16P4tXZnFDO1KWa1p8FkZXsa4.QX0EDO0wSM3kjNzEzW}
```

## What I learned
I learned about the man command which is short for manual. It basically gives an overview of a command and how to use it. You use the man command by typing in man followed by the name of the actual command and not its path.

## References 
none

# Searching Manuals
This challenge asks us to use the man command and find the right argument to print the flag using /challenge/challenge.

## My solve
**Flag:** `pwn.college{g6q3ZLReNxOthXC8Fe-ZidG-_Un.QX1EDO0wSM3kjNzEzW}`
We start by opening the manual for challenge using man challenge. Now we search for the argument which prints the flag, we do this by typing in /flag and keep looking for the right argument by pressing n. Once we reach there, we use it to print the flag. The correct argument in this case was --kb.

```bash
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --kb
Initializing...
Correct usage! Your flag: pwn.college{g6q3ZLReNxOthXC8Fe-ZidG-_Un.QX1EDO0wSM3kjNzEzW}
```

## What I learned
I learned that we can easily search through the manual by using / or ?,/ searches forward whereas ? searches backward from the location of your cursor. To see the next search result just use n and for the previous one use N.

## References 
none

# Searching For Manuals
In this challenge the name of the manpage for /challenge/challenge is something else. We need to look into man man and search for the right manpage and further use that to get the correct argument to end up with the flag. 

## My solve
**Flag:** `pwn.college{8upS-AbYvZDQoN8Q6E7RxFWc9rv.QX2EDO0wSM3kjNzEzW}`
We start by opening up man man, we see some commands as man -k, man -f, man -l, etc. If we scroll down a bit more we see examples on how to use these commands. Here it is mentioned that-

 man -k printf
           Search the short descriptions and manual page names for the keyword printf as regular  expression.   Print out any matches.  Equivalent to apropos printf.

This means we have to use man -k challenge to search in the database for the correct manpage name.
```bash
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k challenge
upbvoxcrvw (1)       - print the flag!
```
upbvoxcrvw is the hidden name
```bash
hacker@man~searching-for-manuals:~$ man upbvoxcrvw
```
now in manpage of this we get the correct argument as  --upbvox 886
so,
```bash
hacker@man~searching-for-manuals:~$ /challenge/challenge --upbvox 886
Correct usage! Your flag: pwn.college{8upS-AbYvZDQoN8Q6E7RxFWc9rv.QX2EDO0wSM3kjNzEzW}
```


## What I learned
I learned that we can even man has its manpage along with arguments we can use for it.
All the manpages are gathered in a database. man -k argument searches for the keyword 
argument in the database and shows a short description of the manpages containing this keyword. man -f is similar but searches for the exact match and not a substring match.
## References 
none

# Helpful Programs
In this challenge we need to learn about the program not by using man, but by --help, -h, -? etc. as agrument.

## My solve
**Flag:** `pwn.college{AbRgwl2lmw9d4T2IhSITbPN6gFe.QX3IDO0wSM3kjNzEzW}`
We type in /challenge/challenge --help
this is what we get->
```bash
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
```
We see that -g argument will give us the flag, and -p will give us the value which cause the -g option to give us the flag.

```bash
hacker@man~helpful-programs:~$  /challenge/challenge -p
The secret value is: 294
hacker@man~helpful-programs:~$  /challenge/challenge -g 294
Correct usage! Your flag: pwn.college{AbRgwl2lmw9d4T2IhSITbPN6gFe.QX3IDO0wSM3kjNzEzW}
```

## What I learned
I learned that not all programs might have a manpage. Some might just tell us their description by --help, -h, -?, help, etc. as arguments.
## References 
none

# Help for Builtins
In this challenge, the command challenge is a shell builtin and we need to use the command 'help' to learn about it and gather the flag.

## My solve
**Flag:** `pwn.college{IHiRFMMwMVbh1Ppd4wDhOoihWtm.QX0ETO0wSM3kjNzEzW}`
We type in 'help challenge' and get the argument to print flag as '--secret' , followed by the correct value, which in this case was IHiRFMMw.
```bash
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "IHiRFMMw".
hacker@man~help-for-builtins:~$ challenge --secret IHiRFMMw
Correct! Here is your flag!
pwn.college{IHiRFMMwMVbh1Ppd4wDhOoihWtm.QX0ETO0wSM3kjNzEzW}
```

## What I learned
Some commands are internally built into the shell and are known as shell builtins.
I learned that we can learn about shell builtins by just typing in 'help builtin', where builtin is any builtin command known by the shell.
## References 
none


