# Home sweet home

We were asked to run /challenge/run and include an absolute path as an argument to it, so that it could write a copy of the flag there. The argument had to be an absolute path, inside the home directory, and before expansion three characters or less.

## My solve
**Flag: 'pwn.college{c42T6oU3tHd7IVffXGUXbSvBZ-S.QXzMDO0wyN4ETMzEzW}'**

``/challenge/run`` is the command to write a copy of the flag, and we must provide the command with the path to write the copy of the flag to as an argument. Since it must be less than 3 characters or less, we can utilitize the *~* shorthand, which extends to "/home/hacker" which fulfills the criterias. This leaves us with one letter to name the file to which we copy the flag to (can be any random letter). So running ``/challenge/run ~/a`` will write a copy of the flag to ``/home/hacker/a``.

```bash
Connected!
hacker@paths~home-sweet-home:~$ /challenge/run
You must provide an argument to /challenge/run when you invoke it!
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{c42T6oU3tHd7IVffXGUXbSvBZ-S.QXzMDO0wyN4ETMzEzW}
```

## What I learned

Every user has a home directory that is typically under "/home" in the filesystem. (In the dojo, this is "/home/hacker")

In the prompt *hacker@dojo:~$*, the "~" is the current working directory, and is short for "/home/hacker". (Only the leading ~ is expanded)
``cd`` uses home directory as default destination.
