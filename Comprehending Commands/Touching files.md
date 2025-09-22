# Touching files

Here we were asked to use the ``touch`` command (which creates files in the current directory) to create 2 files (pwn and college) in the */tmp* directory, and then to invoke ``/challenge/run`` to receive the flag.

## My solve
**Flag: 'pwn.college{UQCXOP-CHDI9G-DNAdqxAGMKZPb.QXwMDO0wyN4ETMzEzW}'**

To be able to run ``/challenge/run``, first we must create 2 files: */tmp/pwn* and */tmp/college*. After ``cd``ing to */tmp*, running ``touch pwn`` creates the first file. Then, running ``touch college`` creates the second file. Now we can run ``/challenge/run`` to receive the flag.

```bash
Connected!
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ cd
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{UQCXOP-CHDI9G-DNAdqxAGMKZPb.QXwMDO0wyN4ETMzEzW}
hacker@commands~touching-files:~$ 
```

## What I learned
I learned that you can use the ``touch`` command to create a file in the current directory. You provide the ``touch`` command with the name of the file to be created as an argument.
