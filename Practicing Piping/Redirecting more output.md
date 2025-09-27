# Redirecting more output

In this challenge, we were asked to run ``/challenge/run``, but redirect its output to the file "myflag" to receive the flag.

## My solve
**Flag: 'pwn.college{YertOAHneZPaorwcGO6VEEhR-N4.QX1YTN0wyN4ETMzEzW}'**

I ran ``/challenge/run > myflag``, as we were asked to run the program ``/challenge/run``, but only while redirecting the output of this to the file "myflag". So to achieve this, I added "> my flag" so that the output was redirected to the file "myflag". After this, the terminal displayed that i performed this correctly. To read the flag from the "myflag" file, I ran ``cat myflag``, receiving the flag.

```bash
Connected!
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{YertOAHneZPaorwcGO6VEEhR-N4.QX1YTN0wyN4ETMzEzW}

hacker@piping~redirecting-more-output:~$ 
```

## What I learned
I learned that you can redirect the output of any command using ">". 