# Making directories

Here we were told to use the ``mkdir`` command, which creates new directories, to make a pwn directory inside /tmp, and then create a file named college using the ``touch`` command. Then finally we must run /challenge/run to receive the flag.

## My solve
**Flag: 'pwn.college{c-cXyU0EB1YuPkKdzpcVOJ6u2JT.QXxMDO0wyN4ETMzEzW}'**

They asked us to create a */tmp/pwn* directory, so first I switch to the */tmp* directory using ``cd``, and then create the "pwn" directory by running ``mkdir pwn``. Now to create the college file, i move into the pwn directory by running ``cd pwn``, and then run ``touch college`` to create the file.
Then, I run ``/challenge/run`` to receive the flag.

```bash
Connected!
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ cd pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ cd
hacker@commands~making-directories:~$ /challenge/run
Success! Here is your flag:
pwn.college{c-cXyU0EB1YuPkKdzpcVOJ6u2JT.QXxMDO0wyN4ETMzEzW}
hacker@commands~making-directories:~$ 
```

## What I learned
I learnt about the ``mkdir`` command, which allows you to create new directories. You pass the name of the directory to the command as an argument, and it creates the new directory within the current working directory.
