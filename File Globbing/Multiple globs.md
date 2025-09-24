# Multiple globs

In this challenge, they have put a few diversely named files in */challenge/files*. We must ``cd`` there and run ``/challenge/run`` providing a single argument: a short (3 characters or less) globbed word with two "*" globs in it that covers every word that contains the letter "p". 

## My solve
**Flag: 'pwn.college{4CJ5ET38olGn9WxNMK7Nk0q3SQb.0lM3kjNxwyN4ETMzEzW}'**

I ran ``cd /challenge/files`` to change into that directory. I then ran ``/challenge/run *p*`` to receive the flag. The argument ``*p*`` makes sense here because it satisfied the criteria where it covers every word that contains the letter p, as anything can come before or after the p, or even nothing at all.

```bash
Connected!
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{4CJ5ET38olGn9WxNMK7Nk0q3SQb.0lM3kjNxwyN4ETMzEzW}
hacker@globbing~multiple-globs:/challenge/files$ 
```

## What I learned

I learned that bash supports the expansion of multiple globs in a single word. I also learned that "*" can be treated as nothing as well by bash.