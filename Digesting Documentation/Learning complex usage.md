# Learning complex usage

Here we were told about arguments within arguments. Upon connecting to the terminal, we were told to invoke ``/challenge/challenge`` and that when this is given the "--printfile" argument it prints the file name that is listed after the -"-printfile" argument. So after doing this with ``/flag``, we receive the flag.

## My solve
**Flag: 'pwn.college{M5Jx8f4_lmSoXZGFW9D8HFEI3Do.QX1ITO0wyN4ETMzEzW}'**

I followed the documentation, and ran ``/challenge/challenge`` with the argument "--printfile" and the location of the flag as another argument, which is "/flag". This I found by running ``ls /``. So running ``/challenge/challenge --printfile /flag`` gave me the flag.

```bash
Connected!
hacker@man~learning-complex-usage:~$ ls
Desktop  a  not-the-flag
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /not-the-flag
Correct argument! Here is the /not-the-flag file:
cat: /not-the-flag: No such file or directory
hacker@man~learning-complex-usage:~$ ls /
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{M5Jx8f4_lmSoXZGFW9D8HFEI3Do.QX1ITO0wyN4ETMzEzW}
hacker@man~learning-complex-usage:~$ 
```

## What I learned
There exists complex usage of some commands, where you are required to pass arguments to arguments.
