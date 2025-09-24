# Matching with []

In this challenge, they have placed a bunch of files in */challenge/files*. We must change our directory to */challenge/files* and run ``/challenge/run`` with a single argument that bracket globs into "file_b", "file_a", "file_s" and "file_h". 

## My solve
**Flag: 'pwn.college{ch2g3Dkc0L-GLeCR2Cw3-TUtYxZ.QXzIDO0wyN4ETMzEzW}'**

I ran ``cd/challenge/files`` to change directory to the one we were required to be in by the challenge description. Since we were tasked with running ``/challenge/run`` with a single argument that globbed all 4 files (file_b, file_a, file_s, and file_h), it made sense to use the square brackets with the letters "b,a,s,h" inside to glob all 4 in one argument. So running ``/challenge/run file_[b,a,s,h]`` gave us the flag.

```bash
Connected!
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[b,a,s,h]
You got it! Here is your flag!
pwn.college{ch2g3Dkc0L-GLeCR2Cw3-TUtYxZ.QXzIDO0wyN4ETMzEzW}
hacker@globbing~matching-with-:/challenge/files$ 
```

## What I learned

The "[]" in globbing matches exactly one character from the characters that you specified within the square brackets. Acting as a limited "?".