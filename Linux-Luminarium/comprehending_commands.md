# Comprehending Commands

**Date:** 23 Sep 2025
**Author:** Vedant Lohan

# cat: not the pet, but the command!
The challenge asks us to read a file named flag using the cat command.

## My solve
**Flag:** `pwn.college{8DA7mced_kv-dziFu7DZVrdldeX.QXxcTN0wSM3kjNzEzW}`

To read the file named flag we used the cat command with the argument flag. The file was present in the home directory hence the relative path was just flag.

```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{8DA7mced_kv-dziFu7DZVrdldeX.QXxcTN0wSM3kjNzEzW}
```

## What I learned
I learned that we can read files in linux using the cat command. The cat command can also concatenate multiple files.

## References 
none

# catting absolute paths
The challenge asks us to read a file named flag using the cat command.

## My solve
**Flag:** `pwn.college{MzNFU0y_oiz49U4ks1XodMshZJI.QX5ETO0wSM3kjNzEzW}`

To read the file named flag we used the cat command with the argument /flag. The file was present in /flag.

```bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{MzNFU0y_oiz49U4ks1XodMshZJI.QX5ETO0wSM3kjNzEzW}
```

## What I learned
I learned that /flag is where the flag always lives in pwn.college, but in other challenges you cannot access that file directly.

## References 
none

# more catting practice
The challenge asks us to read a file named flag using the cat command with an absolute path as an argument.

## My solve
**Flag:** `pwn.college{8K3jse62VZzpK_vpo8lQyIB3uAq.QXwITO0wSM3kjNzEzW}`

First we try cd, we get a message which provides us the path of the flag. Then we use the cat command and that path to read the flag.
```bash
hacker@commands~more-catting-practice:~$ cd
You used 'cd'! In this level, I don't allow you to change the working directory
--- you MUST chase pass 'cat' the absolute path of where I put it on the
filesystem (which is /usr/share/zoneinfo/flag).
hacker@commands~more-catting-practice:~$ cat /usr/share/zoneinfo/flag
pwn.college{8K3jse62VZzpK_vpo8lQyIB3uAq.QXwITO0wSM3kjNzEzW}
```

## What I learned
I learned that we can read files in linux using the cat command.

## References 
none

# grepping for a needle in a haystack
This challenge asks us to find the flag using the grep command in a large txt file.

## My solve
**Flag:** `pwn.college{cGkxV_RNi0m38e6kQ6oWJ-qQfvv.QX3EDO0wSM3kjNzEzW}`

To use the grep command, we type in grep followed by pwn.college because every flag contains that, and then the path of that file which was /challenge/data.txt
```bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{cGkxV_RNi0m38e6kQ6oWJ-qQfvv.QX3EDO0wSM3kjNzEzW}
```

## What I learned
I learned that we can search for a text in a big file using the grep command

## References 
none

# comparing files
This challenge asks us to find the flag using the diff command by comparing to txt files.

## My solve
**Flag:** `pwn.college{0buF1NItKP8hrNRHTN1lQtlt4w_.01MwMDOxwSM3kjNzEzW}`

There are two files in this challenge, the first one contains 100 fake flag and the second one contains the real flag along with the 100 fake ones. We use the grip command to find the difference that is the real flag.
```bash
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
4a5
> pwn.college{0buF1NItKP8hrNRHTN1lQtlt4w_.01MwMDOxwSM3kjNzEzW}
```

## What I learned
I learned that we can use the diff command to compare two files. 2c2 means that the second line in first file was changed in the second file. 1a2 means that after the first line of the first file there was an addition of second line in second file.

## References 
none

# listing files
In this challenge we had to use the ls command to list the files and find the flag.

## My solve
**Flag:** `pwn.college{sadlLcro8mEYiPGGv54QWRMI6Q5.QX4IDO0wSM3kjNzEzW}`

The flag was inside /challenge but had been renamed to something else. We change the directory to /challenge and then use ls to list all the files inside of it. Then we just had to run that program to find the flag.
```bash
hacker@commands~listing-files:~$ cd /challenge
hacker@commands~listing-files:/challenge$ ls
25967-renamed-run-27309  DESCRIPTION.md
hacker@commands~listing-files:/challenge$ /challenge/25967-renamed-run-27309
Yahaha, you found me! Here is your flag:
pwn.college{sadlLcro8mEYiPGGv54QWRMI6Q5.QX4IDO0wSM3kjNzEzW}
```

## What I learned
I learned that we can list all the files in a directory using the ls command. The argument decides which directory's files to list, if there is no argument then ls lists the files of the current working directory.

## References 
none

# touching files
In this challenge we had to create two empty files and then run the program run to find the flag

## My solve
**Flag:** `pwn.college{4hZRQpgA9b776Pj6v0lrC5r7dY_.QXwMDO0wSM3kjNzEzW}`

We start by changing the directory to /tmp, then we create two empty files named pwn and college using the command touch. Then we run /challenge/run to fing the flag.
```bash
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn college
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{4hZRQpgA9b776Pj6v0lrC5r7dY_.QXwMDO0wSM3kjNzEzW}
```

## What I learned
I learned that we can create files using the touch command

## References 
none

# removing files
In this challenge we had to create and then delete that file to get the flag.

## My solve
**Flag:** `pwn.college{Eh95FP_5YC_GAc3I2z0RbjC72xz.QX2kDM1wSM3kjNzEzW}`

First we create a file named delete_me in ~ using touch, then we delete that using the rm command. Then we just had to run /challenge/check to get the flag.
```bash
hacker@commands~removing-files:~$ touch delete_me
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{Eh95FP_5YC_GAc3I2z0RbjC72xz.QX2kDM1wSM3kjNzEzW}
```

## What I learned
I learned that we can delete files using the rm command

## References 
none

# moving files
In this challenge we had to move /flag to /tmp/hack-the-planet, and then run /challenge/check to get the flag.

## My solve
**Flag:** `pwn.college{8XwI-iXqPc3SjeMegwaVc6pXH9N.0VOxEzNxwSM3kjNzEzW}`

We use the command mv to move /flag to /tmp/hack-the-planet and then run /challenge/check to get the flag. The first argument is the file to be moved and the second one is the path where it has to be moved
```bash
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{8XwI-iXqPc3SjeMegwaVc6pXH9N.0VOxEzNxwSM3kjNzEzW}
```

## What I learned
I learned that we can move files using the mv command. The first argument is the file to be moved and the second one is the path where it has to be moved

## References 
none

# hidden files
In this challenge we had to list the hidden files and find the flag.

## My solve
**Flag:** `pwn.college{EcLUP0d_fp2rHOlhnRw6hh7GYWw.QXwUDO0wSM3kjNzEzW}`

We move to / using cd, then we list all the files along with the hidden ones using the command ls -a, we then use cat to read the flag file.
```bash
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.   .dockerenv            bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-90241942628369  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:/$ cat .flag-90241942628369
pwn.college{EcLUP0d_fp2rHOlhnRw6hh7GYWw.QXwUDO0wSM3kjNzEzW}
hacker@commands~hidden-files:/$ .flag-90241942628369
```

## What I learned
I learned that we can list the hidden files in a directory using the command ls -a

## References 
none

# An Epic Filesystem Quest
In this challenge the flag was hidden somewhere, we had to use the clues to reach to the flag.

## My solve
**Flag:** ` pwn.college{YuxNhigow_KSrTbtGuGbDzt_1Nz.QX5IDO0wSM3kjNzEzW}`

We used cd to change the directory's, used ls -a to list the them and cat to read out the files to find the clues and eventually the flag.
```bash
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls -a
.   .dockerenv  bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
..  SECRET      boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@commands~an-epic-filesystem-quest:/$ cat SECRET
Lucky listing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/sympy/sets/tests

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd  /usr/local/lib/python3.8/dist-packages/sympy/sets/tests
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/sympy/sets/tests$ ls -a
.   ALERT        __pycache__           test_contains.py   test_ordinals.py  test_setexpr.py
..  __init__.py  test_conditionset.py  test_fancysets.py  test_powerset.py  test_sets.py
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/sympy/sets/tests$ cat ALERT
Lucky listing!
The next clue is in: /opt/busybox/busybox-1.33.2/include/config/feature/ntpd
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/sympy/sets/tests$ cd /opt/busybox/busybox-1.33.2/include/config/feature/ntpd
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/include/config/feature/ntpd$ ls -a
.  ..  EVIDENCE  conf.h  server.h
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/include/config/feature/ntpd$ cat EVIDENCE
Congratulations, you found the clue!
The next clue is in: /opt/busybox/busybox-1.33.2/examples/bootfloppy/etc/init.d

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/include/config/feature/ntpd$ cd /opt/busybox/busybox-1.33.2/examples/bootfloppy/etc/init.d
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/examples/bootfloppy/etc/init.d$ ls -a
.  ..  SPOILER  rcS
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/examples/bootfloppy/etc/init.d$ cat SPOILER
Great sleuthing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/angr/engines/soot/statements

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/examples/bootfloppy/etc/init.d$ cd /usr/local/lib/python3.8/dist-packages/angr/engines/soot/statements
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/engines/soot/statements$ ls -a
.   .MESSAGE     __pycache__  base.py  identity.py  invoke.py   switch.py
..  __init__.py  assign.py    goto.py  if_.py       return_.py  throw.py
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/engines/soot/statements$ cat .MESSAGE
Great sleuthing!
The next clue is in: /usr/lib/python3/dist-packages/sage/symbolic/integration

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/engines/soot/statements$ cd /usr/lib/python3/dist-packages/sage/symbolic/integration
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sage/symbolic/integration$ ls -a
.  ..  DISPATCH  __init__.py  __pycache__  external.py  integral.py
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sage/symbolic/integration$ cat DISPATCH
Tubular find!
The next clue is in: /usr/share/doc/bison/examples/c/lexcalc

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sage/symbolic/integration$ cd /usr/share/doc/bison/examples/c/lexcalc
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/bison/examples/c/lexcalc$ ls -a
.  ..  .NOTE  Makefile  README.md  parse.y  scan.l
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/bison/examples/c/lexcalc$ cat .NOTE
Great sleuthing!
The next clue is in: /usr/share/javascript/mathjax/localization/ia

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/bison/examples/c/lexcalc$ cat /usr/share/javascript/mathjax/localization/ia
cat: /usr/share/javascript/mathjax/localization/ia: Is a directory
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/bison/examples/c/lexcalc$ ls -a  /usr/share/javascript/mathjax/local
ization/ia
.  ..  FontWarnings.js  HTML-CSS.js  HelpDialog.js  INFO-TRAPPED  MathML.js  MathMenu.js  TeX.js  ia.js
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/bison/examples/c/lexcalc$ cat /usr/share/javascript/mathjax/localization/ia/INFO-TRAPPED
Great sleuthing!
The next clue is in: /usr/share/nvim/runtime/compiler

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/bison/examples/c/lexcalc$ ls -a /usr/share/nvim/runtime/compiler
.                csslint.vim        fortran_lf95.vim  icc.vim          mipspro_cpp.vim    pylint.vim    splint.vim
..               cucumber.vim       fpc.vim           ifort.vim        modelsim_vcom.vim  pyunit.vim    stack.vim
POINTER-TRAPPED  decada.vim         g95.vim           intel.vim        msbuild.vim        rake.vim      tcl.vim
ant.vim          dot.vim            gcc.vim           irix5_c.vim      msvc.vim           rspec.vim     tex.vim
bcc.vim          erlang.vim         gfortran.vim      irix5_cpp.vim    neato.vim          rst.vim       tidy.vim
bdf.vim          eruby.vim          ghc.vim           javac.vim        ocaml.vim          ruby.vim      xbuild.vim
cargo.vim        fortran_F.vim      gnat.vim          jikes.vim        onsgmls.vim        rubyunit.vim  xmllint.vim
checkstyle.vim   fortran_cv.vim     go.vim            mcs.vim          pbx.vim            rustc.vim     xmlwf.vim
context.vim      fortran_elf90.vim  haml.vim          mips_c.vim       perl.vim           sass.vim
cs.vim           fortran_g77.vim    hp_acc.vim        mipspro_c89.vim  php.vim            se.vim
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/bison/examples/c/lexcalc$ cat /usr/share/nvim/runtime/compiler/POINTER-TRAPPED
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{YuxNhigow_KSrTbtGuGbDzt_1Nz.QX5IDO0wSM3kjNzEzW}
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/bison/examples/c/lexcalc$
```

## What I learned
I learned that sometimes you need to be patient to find the flag.

## References 
none

# making directories
In this challenge we had to create a directory /tmp/pwn and then a file named college inside pwn to get the flag.

## My solve
**Flag:** `pwn.college{ksJQ5-j-pLyacl3f8MntYpOLLX9.QXxMDO0wSM3kjNzEzW}`

We create the directory using mkdir /tmp/pwn and then the file college using touch /tmp/pwn/college. After this we run /challenge/run to get the flag.
```bash
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ touch /tmp/pwn/college
hacker@commands~making-directories:~$ /challenge/run
Success! Here is your flag:
pwn.college{ksJQ5-j-pLyacl3f8MntYpOLLX9.QXxMDO0wSM3kjNzEzW}
```

## What I learned
I learned that we can create directories using mkdir command.
## References 
none

# finding files
In this challenge we had to find the flag using the find command. Flag is not present in the files which say permission denied.

## My solve
**Flag:** `pwn.college{YSDXbYW0Qll4birJe8iU7k9Cq64.QXyMDO0wSM3kjNzEzW}`

We use find / -name flag to find files named flag. This gives us all the files named flag but some of them include permission denied. The ques says that flag is not present in the files which say permission denied. So we copy paths of all the files which don't say permission denied, and the use grep pwn.college to find the flag.
```bash
hacker@commands~finding-files:~$ find / -name flag
find: ‘/root’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/tmp/tmp.TpSOPGOVKK’: Permission denied
/usr/local/lib/python3.8/dist-packages/future/moves/tkinter/__pycache__/flag
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
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
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ grep pwn.college /usr/local/lib/python3.8/dist-packages/future/moves/tkinter/__pycache__/flag
/usr/local/lib/python3.8/dist-packages/pwnlib/flag /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
pwn.college{YSDXbYW0Qll4birJe8iU7k9Cq64.QXyMDO0wSM3kjNzEzW}
bash: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
bash: /nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag: Is a directory
bash: /nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag: Is a directory
bash: /nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag: Is a directory
bash: /nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag: Is a directory
bash: /nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag: Is a directory
bash: /nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag: Is a directory
bash: /nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag: Is a directory
bash: /nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag: Is a directory
```

## What I learned
I learned that we can find files using the find command. We can also specify the path to find at and criterias such as name. If no path is provided find searchs in the current directory and if you don't specify a search criteria, find matches every file.
## References 
none

# linking files
In this challenge we have to use link to find out the flag. /challenge/catflag reads out /home/hacker/not-the-flag instead of /flag.

## My solve
**Flag:** `pwn.college{sj0kClLCGgUVV3n1gbo5471ilqC.QX5ETN1wSM3kjNzEzW}`

We would just link /flag to /home/hacker/not-the-flag and run /challenge/catflag. Because /flag is now linked to /home/hacker/not-the-flag /challenge/catflag will read out /flag giving us  instead of /home/hacker/not-the-flag
```bash
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{sj0kClLCGgUVV3n1gbo5471ilqC.QX5ETN1wSM3kjNzEzW}
```

## What I learned
A link basically contains the address of the linked file. There are two types of links soft or symbolic links and hard links. Soft links store the path of the file whereas hard links directly point towards the linked file. Hard links are like a different address to the file and soft links contains the orginal address.
## References 
https://www.youtube.com/watch?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&v=m55AtwjBXpE&embeds_referring_euri=https%3A%2F%2Fpwn.college%2F
