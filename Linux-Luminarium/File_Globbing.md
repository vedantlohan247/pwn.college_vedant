# File Globbing

**Date:** 27 Sep 2025
**Author:** Vedant Lohan

# Matching with *
We need to use globbing with * to change directory to /challenge and then execute the program /challenge/run from there to get the flag. But we need to use globbing to keep the argument we pass to cd to at most four characters

## My solve
**Flag:** `pwn.college{8NJh6HJDrYwpFXx9dWTaPTp94Ma.QXxIDO0wSM3kjNzEzW}`
We type in cd /ch*
to get into the directory /challenge and the just run /challenge/run and get the flag.

```bash
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{8NJh6HJDrYwpFXx9dWTaPTp94Ma.QXxIDO0wSM3kjNzEzW}
```

## What I learned
I learned about globbing with *, whenever we use *, the shell will treat it as a wildcard and will try to replace the argument with the files that match that pattern. * ignores a leading '.' and '/'.

## References 
none


# Matching with ?
We need to use globbing with ? to change the directory to /challenge but the catch is that we can't use 'c' or 'l' in the argument.

## My solve
**Flag:** `pwn.college{8MhNUwwcpuQyLdzfSYg5h_bAUrJ.QXyIDO0wSM3kjNzEzW}`
We type in cd /?ha??enge
to get into the directory /challenge and the just run /challenge/run and get the flag.

```bash
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{8MhNUwwcpuQyLdzfSYg5h_bAUrJ.QXyIDO0wSM3kjNzEzW}
```

## What I learned
I learned that globbing with ? is similar to * but ? only matches one character and nothing more.

## References 
none


# Matching with []
Here we need to use globbing with [] to get to the flag. There are a bunch of files in /challenge/files.We need to change our working directory to /challenge/files and run /challenge/run with a single argument that bracket-globs into file_b, file_a, file_s, and file_h.
## My solve
**Flag:** `pwn.college{UC7r8DFQNT5-UFRRJ1qosafR0MP.QXzIDO0wSM3kjNzEzW}`
First we change our directory to /challenge/files using cd /challenge/files, then we type in /challenge/run file_[absh] to get the flag. We used [absh] because these are the only characters that are being used.

```bash
hacker@globbing~matching-with-:/challenge$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[absh]
You got it! Here is your flag!
pwn.college{UC7r8DFQNT5-UFRRJ1qosafR0MP.QXzIDO0wSM3kjNzEzW}
```

## What I learned
I learned that square brackets are a limited form of ?. Instead matching any character [] matches only the subset characters mentioned inside of [].

## References 
none


# Matching paths with []
Here we need to use globbing with [] and absolute paths to get to the flag. There are a bunch of files in /challenge/files. Starting from the home directory, we need to run /challenge/run with a single argument that bracket-globs into the absolute paths to the file_b, file_a, file_s, and file_h files!
## My solve
**Flag:** `pwn.college{8RMkHwHOwRW3gy0_ZeanOolXISN.QX0IDO0wSM3kjNzEzW}`

From our home directory we just need to type /challenge/run /challenge/files/file_[absh] to get the flag. We used [absh] because these are the only characters that are being used.

```bash
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[absh]
You got it! Here is your flag!
pwn.college{8RMkHwHOwRW3gy0_ZeanOolXISN.QX0IDO0wSM3kjNzEzW}
```

## What I learned
I learned that globbing happens on path basis, which means we can expand the paths with the globbed arguments.

## References 
none

# Multiple Globs
In this challenge we have to go to /challenge/files and run /challenge/run with an argument such that it covers all the files which have the character 'p'.
## My solve
**Flag:** `pwn.college{g047_ECKVx1lUueRtuiY9KWUOlF.0lM3kjNxwSM3kjNzEzW}`

First we change our directory to /challenge/files, then we type /challenge/run `*p*`
We wrote two '*'s before and after p because can be anywhere in the file name. So it searches for anything then looks for 'p' and then anything can be there.

```bash
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{g047_ECKVx1lUueRtuiY9KWUOlF.0lM3kjNxwSM3kjNzEzW}
```

## What I learned
I learned that we can use multiple globs in an argument.

## References 
none

# Mixing globs
In this challenge we need to change the directory to /challenge/files and then search for "challenging", "educational", and "pwning", using globbing. The number of characters should be less than 6.
## My solve
**Flag:** `"pwn.college{smP0QLy1JU2e6yk1nIpkcKNfYBz.QX1IDO0wSM3kjNzEzW}`

First we change our directory to /challenge/files, then we type /challenge/run [cep]*
to search the files. This works because the first character in the three are c, e, p and are followed by different strings of characters which is handled by *.

```bash
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{smP0QLy1JU2e6yk1nIpkcKNfYBz.QX1IDO0wSM3kjNzEzW}
```

## What I learned
I learned that sometimes you have to try different approaches to meet the required conditions and get to the answer.

## References 
none

# Exclusionary globbing
In this challenge we need to change the directory to /challenge/files and then search for files which do not start with p,w and n.
## My solve
**Flag:** `pwn.college{IGCIp80EAdXzoTyQ7TewrCXx4Ee.QX2IDO0wSM3kjNzEzW}`

First we change our directory to /challenge/files, then we type /challenge/run [!pwn]*
to search the files. [!pwn] means that the first character should not be a p,w or n and * means it can be followed by anything.

```bash
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{IGCIp80EAdXzoTyQ7TewrCXx4Ee.QX2IDO0wSM3kjNzEzW}
```

## What I learned
I learned that [!xyz] or [^xyz] turns the effect of globbing opposite and search for files not containing these chars.

## References 
none

# Tab completion
In this challenge we have to cat /challenge/pwncollege, but we can't type in the whole thing. We have to use the tab completion to get to the flag.

## My solve
**Flag:** `pwn.college{wBpKj16UGJDORDAx5ay9Wv_mYQC.0FN0EzNxwSM3kjNzEzW}`

We type in cat /challenge/pwnc and press tab, this gives us the flag.

```bash
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​
pwn.college{wBpKj16UGJDORDAx5ay9Wv_mYQC.0FN0EzNxwSM3kjNzEzW}
```

## What I learned
I learned that we can not be using * everywhere and because it could lead to unintended files. Instead of this we can use tab to autocomplete.

## References 
none

# Multiple options for tab completion
In this challenge there are multiple files /challenge/files starting with pwncollege. Out of these any of them could be containing the flag. By using tab we need to make our way to the flag.

## My solve
**Flag:** `pwn.college{w1E4Ib0mSocRjl1BxczJ2tTtNc5.0lN0EzNxwSM3kjNzEzW}`

We type in cat /challenge/files/pwncollege and press tab, this gives us cat /challenge/files/pwncollege-, we press tab again and bash lists all the files starting with pwncollege-. cat /challenge/files/pwncollege-flag gives us the flag.

```bash
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-
pwncollege-family      pwncollege-flag        pwncollege-flamingo    pwncollege-flyswatter  pwncollege-hacking
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-flag
pwn.college{w1E4Ib0mSocRjl1BxczJ2tTtNc5.0lN0EzNxwSM3kjNzEzW}
```

## What I learned
I learned that when there are multiple matches for tab, bash will auto-expand until the first point when there are multiple options. And when you hit tab for the second time it will list all those matching options. Other shells will just cycle through all the options when you press tab in this case.

## References 
none

# Tab completion on commands
In this challenge we need to run a command which produces the flag. This commands starts from pwncollge. We need to use tab to autofill and run the command.

## My solve
**Flag:** `pwn.college{4MyPFsZdlKxY-VwVdaeGrtWMRyg.0VN0EzNxwSM3kjNzEzW}`

Just type in pwncollege, hit tab, this give you the commands. Now hit enter and you have the flag.

```bash
hacker@globbing~tab-completion-on-commands:~$ pwncollege-5525
Correct! Here is your flag:
pwn.college{4MyPFsZdlKxY-VwVdaeGrtWMRyg.0VN0EzNxwSM3kjNzEzW}
```

## What I learned
I learned that we can also use tab autofill completion for commmands aswell.

## References 
none

