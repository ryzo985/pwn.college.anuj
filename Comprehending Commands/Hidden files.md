# Hidden files

Here we were told that files that begin with a "." (dot prepended file) wont be listed when ``ls`` is ran, and to view hidden files we must run ``ls -a``. We must find the flag that is hidden as a dot-prepended file in the root directory ("/").

## My solve
**Flag: 'pwn.college{0VVtAwX2sLbQTPYnCLZy7fRf618.QXwUDO0wyN4ETMzEzW}'**

The hidden file is in the root directory, so I run ``cd /`` to change into that directory. I then run ``ls -a`` to list all the files, including the hidden dot-prepended files. This displays many files, and one hidden file that contains the word flag. I ``cat`` this file (*.flag-317202477518806*), using an explicit relative path, and this provides me with the flag.

```bash
Connected!
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.                      bin        etc    lib64   nix   run   tmp
..                     boot       home   libx32  opt   sbin  usr
.dockerenv             challenge  lib    media   proc  srv   var
.flag-317202477518806  dev        lib32  mnt     root  sys
hacker@commands~hidden-files:/$ cat ./.flag-317202477518806
pwn.college{0VVtAwX2sLbQTPYnCLZy7fRf618.QXwUDO0wyN4ETMzEzW}
hacker@commands~hidden-files:/$ 
```

## What I learned
I learned that the ``ls`` command does not list all the files, and there are "hidden" files if their names are dot-prepended (beginning with a "."), and to view these dot-prepended files with ``ls``, we must provide the command with an argument of ``-a``. So running ``ls -a`` lists all the files, including the hidden ones too.