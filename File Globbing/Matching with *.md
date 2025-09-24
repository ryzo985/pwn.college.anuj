# Matching with *

Here, we start from the home directory, and need to ``cd`` to */challenge*, but use globbing to keep the argument given to ``cd`` to at most 4 characters. Once we are there we must run ``/challenge/run`` to receive the flag.

## My solve
**Flag: 'pwn.college{cSkvVI4jTVSY3M4pvUsLMbfp1HS.QXxIDO0wyN4ETMzEzW}'**

Since I cannot use more than 4 characters in the argument given to ``cd``, i ran ``cd /ch*``. This worked to change my directory to */challenge*, where I then ran ``/challenge/run`` to receive the flag.

```bash
Connected!
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{cSkvVI4jTVSY3M4pvUsLMbfp1HS.QXxIDO0wyN4ETMzEzW}
hacker@globbing~matching-with-:/challenge$ 
```

## What I learned

I learnt about the existence of "globbing", which lets you reference files without typing them all out, or typing their full paths. Before executing commands, the shell first performs expansions on them (one of which is globbing).

Here, I learnt about my first glob, which was "*". Whenever the shell encounters the asterisk character in any argument, it treats it as a wildcard and will try to replace that argument with any files that match the pattern. If zero files are matched, the shell leaves the glob unchanged. 

The "*" matches any part of the filename except "/" or a leading "." character.