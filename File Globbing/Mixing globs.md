# Mixing globs

In this challenge, there are a few diversely named files within */challenge/files*. We must ``cd`` there and make use of all the globbing we've learnt so far. We must write a single, short (6 characters or less) glob that when passed as an argument to ``/challenge/run`` will match the files "challenging", "educational", and "pwning".

## My solve
**Flag: 'pwn.college{U7XT7dYlrtfy_1XZaBBQPb8gYYY.QX1IDO0wyN4ETMzEzW}'**

I ran ``cd /challenge/files`` to change directory. I then ran ``ls`` to view the files in the directory. I noticed that the files we needed to match were the only ones that started with c,e, or p. So, running ``/challenge/run [cep]*`` returned the flag. The argument ``[cep]*`` makes sense as this is exactly 6 characters, specified the first letter for the 3 files using the ``[]`` wildcard, and is then followed by the ``*`` wildcard, for the rest of the filename.

```bash
Connected!
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run *i*n*[g,l]
Error: your argument is too long! It must be 6 characters or less.
hacker@globbing~mixing-globs:/challenge/files$ ls
amazing      fantastic   kind        pwning     uplifting   zesty
beautiful    great       laughing    queenly    victorious
challenging  happy       magical     radiant    wonderful
delightful   incredible  nice        splendid   xenial
educational  jovial      optimistic  thrilling  youthful
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [c,e,p]*
Error: your argument is too long! It must be 6 characters or less.
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{U7XT7dYlrtfy_1XZaBBQPb8gYYY.QX1IDO0wyN4ETMzEzW}
hacker@globbing~mixing-globs:/challenge/files$ 
```


## What I learned

I learned that when using square brackets, you dont have to seperate the characters specified with a comma.