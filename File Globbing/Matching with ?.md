# Matching with ?

Here, we start from the home directory, and must change our directory to */challenge* using ``cd`` but we must also use "?" instead of c or l in the argument to ``cd``. Once we are here, we must run ``/challenge/run`` to receive the flag.

## My solve
**Flag: 'pwn.college{oGc4v3gO3p5_57ZVIjTMCSpRlEh.QXyIDO0wyN4ETMzEzW}'**

Since I had to replace the "c" and "l" with "?" in the argument given to ``cd``, I ran ``cd /?ha??enge`` which successfully changed my directory to */challenge*, before running ``/challenge/run`` to receive the flag.

```bash
Connected!
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{oGc4v3gO3p5_57ZVIjTMCSpRlEh.QXyIDO0wyN4ETMzEzW}
hacker@globbing~matching-with-:/challenge$ 
```

## What I learned

I learned that when the shell encounters "?" in any argument, it treats it as a single character wildcard. This works like "*", but only matches one character.