# Grepping errors

In this level, running ``/challenge/run`` overwhelms you with output, but on standard error not standard output. We must ``grep`` through the ouput to find the flag.

## My solve
**Flag: 'pwn.college{omQcn9h1xpMpOxwShvF3WerBrH7.QX1ATO0wyN4ETMzEzW}'**

Running ``/challenge/run 2>& 1 | grep pwn.college`` returns the flag. Here, on the left side "/challenge/run 2>& 1", redirects stderr to stdout. On the right, "grep pwn.college" takes the stdout of the left side as stdin (input) and ``grep``s through it for the string "pwn.college", which is what all the flags begin with. This returns the flag.


```bash
Connected!
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
 
[FAIL] You did not satisfy all the execution requirements.
[FAIL] Specifically, you must fix the following issue:
[FAIL]   stderr of this process does not appear to be a pipe!
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{omQcn9h1xpMpOxwShvF3WerBrH7.QX1ATO0wyN4ETMzEzW}
hacker@piping~grepping-errors:~$ 
```


## What I learned

I learned that the pipe operator only redirects standard output to another program, and there is no "2|" form of the pipe operator. It can't redirect errors.

Instead, the shell has an ">&" operator which redirects a file descriptor to another file descriptor. This means that we can have a 2 step process to grep through errors: first, we redirect standard error to standard output using "2>& 1". We then pipe the now combined stderr and stdout as normal using the pipe operator.