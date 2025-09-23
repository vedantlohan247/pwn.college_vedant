# Pondering Paths

**Date:**  22 Sep 2025
**Author:** Vedant Lohan

# The Root
The challenge asks to run a program named pwn by providing its path

## My solve
**Flag:** `pwn.college{4y-mqZamGSW3mXZica5j-BDdkZL.QX4cTO0wSM3kjNzEzW}`

To run a program just type in its absolute path, which in this case would be /pwn.

```bash
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{4y-mqZamGSW3mXZica5j-BDdkZL.QX4cTO0wSM3kjNzEzW}
```

## What I learned
I learned that you can invoke a program by providing its path in the command line

## References 
https://www.youtube.com/watch?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&v=b67Jq6IZ3U8

# Program and absolute paths
This challenge asks us to run a program by providing its absolute path

## My solve
**Flag:** `pwn.college{UIFLaGBomDei433qWCgA5E2X1dN.QX1QTN0wSM3kjNzEzW}`

The program named run is located in the directory challenge which is located in the root. To execute program named run, we provide the absolute path that is: /challenge/run

```bash
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{UIFLaGBomDei433qWCgA5E2X1dN.QX1QTN0wSM3kjNzEzW}
```

## What I learned
I learned that you can invoke a program by providing its path in the command line

## References 
https://www.youtube.com/watch?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&v=b67Jq6IZ3U8

# Position thy self
The challenge asks us to execute a program run from a specific path which was from /sys.

## My solve
**Flag:** `pwn.college{gKb-EDdcb9jVbHEwp2JHMADI19b.QX2QTN0wSM3kjNzEzW}`

We needed to execute the command /challenge/run from a specific path. Firslty we try /challenge/run and it says we need to be in /sys to be able to run this command. So we change directory to /sys and then execute /challenge/run

```bash
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /sys directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /sys
hacker@paths~position-thy-self:/sys$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{gKb-EDdcb9jVbHEwp2JHMADI19b.QX2QTN0wSM3kjNzEzW}
```

## What I learned
You can run a program by writing its absolute path. An absolute path is the complete path of the directory starting from the root / directory.Every executable can be run while being in any directory if you mention its complete absolute path but in this challenge we had to be in /sys to be able to invoke the program.

## References 
https://www.youtube.com/watch?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&v=b67Jq6IZ3U8

# Position elsewhere
The challenge asks us to execute a program run from a specific path which was from /proc/131/fd

## My solve
**Flag:** `pwn.college{sy6M3hOo8zCP0uSDbwjrm8F-ZrY.QX3QTN0wSM3kjNzEzW}`

We needed to execute the command /challenge/run from a specific path. Firslty we try /challenge/run and it says we need to be in /proc/131/fd to be able to run this command. So we change directory to /proc/131/fd and then execute /challenge/run

```bash
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /proc/131/fd directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /proc/131/fd
hacker@paths~position-elsewhere:/proc/131/fd$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{sy6M3hOo8zCP0uSDbwjrm8F-ZrY.QX3QTN0wSM3kjNzEzW}
hacker@paths~position-elsewhere:/proc/131/fd$
```

## What I learned
You can run a program by writing its absolute path. An absolute path is the complete path of the directory starting from the root / directory.Every executable can be run while being in any directory if you mention its complete absolute path but in this challenge we had to be in /sys to be able to invoke the program.

## References 
https://www.youtube.com/watch?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&v=b67Jq6IZ3U8

# Position yet elsewhere
The challenge asks us to execute a program run from a specific path which was from /sys/kernel

## My solve
**Flag:** `pwn.college{guSfQ1oYciAJ4tTCCBHYnyAyUUN.QX4QTN0wSM3kjNzEzW}`

We needed to execute the command /challenge/run from a specific path. Firslty we try /challenge/run and it says we need to be in /sys/kernel to be able to run this command. So we change directory to /sys/kernel and then execute /challenge/run

```bash
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /sys/kernel directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /sys/kernel
hacker@paths~position-yet-elsewhere:/sys/kernel$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{guSfQ1oYciAJ4tTCCBHYnyAyUUN.QX4QTN0wSM3kjNzEzW}
hacker@paths~position-yet-elsewhere:/sys/kernel$
```

## What I learned
You can run a program by writing its absolute path. An absolute path is the complete path of the directory starting from the root / directory.Every executable can be run while being in any directory if you mention its complete absolute path but in this challenge we had to be in /sys to be able to invoke the program.

## References 
https://www.youtube.com/watch?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&v=b67Jq6IZ3U8

# implicit relative paths, from/
The challenge asks us to execute a program run using a relative path from /.

## My solve
**Flag:** `pwn.college{IIwqTT7mjCCE7i3uerXosCPfofH.QX5QTN0wSM3kjNzEzW}`

We needed to execute challenge/run which is a relative path while being in the root directory. So we had to change directory to / using cd / and the run the command challenge/run

```bash
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{IIwqTT7mjCCE7i3uerXosCPfofH.QX5QTN0wSM3kjNzEzW}
```

## What I learned
A relative path does not start with / and is relative to the current working directory. You can execute program while being in any directory using the absolute path, but if you wish to use relative path then you should be in a directory which is in the path of that program.

## References 
https://www.youtube.com/watch?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&v=b67Jq6IZ3U8

# explicit relative paths, from/
The challenge asks us to execute a program run using an explicit relative path.

## My solve
**Flag:** `pwn.college{Ij34pDjgK3bL613hxc6j2u533RE.QXwUTN0wSM3kjNzEzW}`

We needed to execute challenge/run using an explicit relative path while being in /.
We change the directory to / and then execute ./challenge/run

```bash
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Ij34pDjgK3bL613hxc6j2u533RE.QXwUTN0wSM3kjNzEzW}
```

## What I learned
If a relative path conatains . or .. it is called an explicit relative path else it is called an implicit relative path. Using . means you are referring to the current working directory and .. means that you are referring to the parent directory of the current working directory.

## References 
https://www.youtube.com/watch?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&v=b67Jq6IZ3U8

# implicit relative path
The challenge asks us to execute a program run which is in the directory /challenge while being in the directory /challenge.

## My solve
**Flag:** `pwn.college{AJ2i-yppK6jjzAdaWtzcexMVo3A.QXxUTN0wSM3kjNzEzW}`

First we need to change directory to challenge by using cd /challenge, now to execute run we will type ./run

```bash
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ run
bash: run: command not found
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{AJ2i-yppK6jjzAdaWtzcexMVo3A.QXxUTN0wSM3kjNzEzW}
```

## What I learned
Naked paths are those which dont start with a / or ./ or ../ that is an implicit relative path.
If you want to run a program which is in the same directory you are currently in then, you can either provide the complete absolute path or explicitly write the relative path. 
Linux wont execute the program if you are in the same directory as the program and provide a naked path to run it. This is a safety measure to ensure you don't accidently execute programs in your cwd which have the same names as the core system utilities.

## References 
https://www.youtube.com/watch?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&v=b67Jq6IZ3U8

# home sweet home
The challenge asks us to run a program /challenge/run which will write a copy of the flag to any file we specify as an argument on the commandline. We need to provide the file as the argument, with these constraints:

1. Your argument must be an absolute path.
2. The path must be inside your home directory.
3. Before expansion, your argument must be three characters or less.


## My solve
**Flag:** `pwn.college{U4KRBCco01mHi5s6xmcVs4FM2v2.QXzMDO0wSM3kjNzEzW}`

In the command we need to execute firstly we will write /challenge/run which will execute the program followed by the argument. We write the argument as ~/a. This meets all the requirements as it is an absolite path, is inside the home directory and only contains 3 characters before expansion.

```bash
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{U4KRBCco01mHi5s6xmcVs4FM2v2.QXzMDO0wSM3kjNzEzW}
```

## What I learned
I learned that ~ is short for /home/user
We can use it in the beginning of an absolute path.
Only the leading ~ is expanded that means, ~/~ will be expanded to /home/hacker/~ rather than /home/hacker/home/hacker.

## References 
https://www.youtube.com/watch?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&v=b67Jq6IZ3U8



