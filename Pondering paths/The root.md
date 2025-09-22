# The root
We were asked to invoke the "pwn" program using its absolute path through the terminal to recieve the flag.

## My solve
**Flag:'pwn.college{IhNLpqT8yeK5G6J8Ptm_neC-1Z0.QX4cTO0wyN4ETMzEzW}'** 

I invoked the pwn program using its absolute path which was given in the challenge description, ``/pwn``. 

```bash
/hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{IhNLpqT8yeK5G6J8Ptm_neC-1Z0.QX4cTO0wyN4ETMzEzW}
hacker@paths~the-root:~$ 
```

## What I learned

I learned that the filesystem starts at /, and that this is called the root directory. Any path that starts with the root directory is reffered to as the "absolute path".
