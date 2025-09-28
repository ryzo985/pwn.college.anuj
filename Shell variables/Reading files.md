# Reading files

In this challenge, we must read ``/challenge/read_me`` into the "PWN" environment variable, and we'll receive the flag. The ``/challenge/read_me`` will keep changing, so we'll need to read it right into the "PWN" variable with one command!

## My solve
**Flag: 'pwn.college{M9ALHEJUl95QTr1s6nxpbdQ1hrG.QXwIDO0wyN4ETMzEzW}'**

I ran ``read PWN < /challenge/read_me`` which returned the flag. Here, the command redirects */challenge/read_me* into the standard input of ``read``, so when it reads into "PWN", it reads from "/challenge/read_me".

```bash
Connected!
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{M9ALHEJUl95QTr1s6nxpbdQ1hrG.QXwIDO0wyN4ETMzEzW}
hacker@variables~reading-files:~$ 
```

## What I learned
I learned that you can use ``read`` to read files or programs with the shell into a variable. This can be done with ``VAR=$(cat some_file)``, but this is known as "Useless use of cat", and the ""right"" way to do it is ``read VAR < some_file``, by redirecting stdin with the "<" character.