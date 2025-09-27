# Redirecting errors

In this challenge, we were asked to redirect the output of ``/challenge/run`` to "myflag", and the "errors" to filename "instructions". Nothing will be outputted to the terminal as we are redirecting everything. We were told that we would find the instructions in "instructions" and the flag in "myflag" if done correctly.

## My solve
**Flag: 'pwn.college{Eqenp4AHI14jIgFUke0o7AfPOpJ.QX3YTN0wyN4ETMzEzW}'**

We were asked to redirect the output of ``/challenge/run`` to "myflag" and redirect the error channel to filename "instructions", this can be done by a single command ``/challenge/run > myflag 2> instructions``. The "2>" refers to redirecting error output specifically, while ">" implicitly refers to stdout. This satisfies all the execution requirements, and so running ``cat myflag`` gives us the flag.

```bash
Connected!
hacker@piping~redirecting-errors:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[TEST] You should have redirected my stderr to instructions. Checking...

[FAIL] You did not satisfy all the execution requirements.
[FAIL] Specifically, you must fix the following issue:
[FAIL]   You have not redirected anything for this process' stderr.
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat instructions
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[TEST] You should have redirected my stderr to instructions. Checking...

[PASS] The file at the other end of my stderr looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{Eqenp4AHI14jIgFUke0o7AfPOpJ.QX3YTN0wyN4ETMzEzW}

hacker@piping~redirecting-errors:~$ 
```

## What I learned

I gained experience with redirecting the error channel of commands as well. I learnt about "File descriptor numbers". A File Descriptor (FD) is a number that describes a communication channel in Linux. 3 FDs are:

    FD 0: Standard Input
    FD 1: Standard Output
    FD 2: Standard Error

When you redirect process communication, you do it by FD number, though some FD numbers are implicit. For example, a > without a number implies 1>, which redirects FD 1 (Standard Output). Now, to redirect error outputs, you simply add 2 in front, like "2>" or "2>>". This is useful if you maybe want to create an error log.

I learned that you can redirect multiple channels in a single command, like both output and error redirection in one command just one after another.