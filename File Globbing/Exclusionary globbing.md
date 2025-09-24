# Exclusionary globbing

Here, we are tasked with ``cd``ing to */challenge/files* and running ``/challenge/run`` with all the files that don't start with "p", "w", or "n".

## My solve
**Flag: 'pwn.college{4aJ5AkkttyZu7DS_H1y1SfosYMt.QX2IDO0wyN4ETMzEzW}'**

I ran ``cd /challenge/files`` to change directory to the specified one. I then ran ``/challenge/run [!pwn]*`` to receive the flag. The argument ``[!pwn]*`` makes sense here as it excludes all the files that start with p,w, or n, using the ``[]`` glob and inverting it with "!", followed by a ``*`` for the rest of the filename.

```bash
Connected!
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{4aJ5AkkttyZu7DS_H1y1SfosYMt.QX2IDO0wyN4ETMzEzW}
hacker@globbing~exclusionary-globbing:/challenge/files$ 
```

## What I learned

I learned that when you want to exclude or filter out files in a glob, you can invert the ``[]`` wildcard by having the first character as "!" or "^". This inverts the glob and that bracket instance matches the characters that aren't listed. Note: The "!" character has a different special meaning when not used as the first character in a ``[]`` glob.