# Grepping live output

In this challenge, ``/challenge/run`` outputs a hundred thousand lines of text, including the flag. We must ``grep`` for the flag, using the pipe operator.

## My solve
**Flag: 'pwn.college{YhtZCfK0YQfI10vHBNoA_TpEJC_.QX5EDO0wyN4ETMzEzW}'**

Since we were asked to make use of the ``grep`` command to find the flag from the hundred thousand lines of text that running ``/challenge/run`` outputs, utilising the pipe operator so that we don't have to redirect the output into a file before ``grep``ping for it. Running ``/challenge/run | grep pwn.college`` outputs the flag. The "/challenge/run" on the left of the pipe causes its standard output to be piped into the standard input of the ``grep pwn.college`` on the right of the pipe operator. I provided "pwn.college" as an argument for the search string to the ``grep`` command as that is what all the flags begin with. 

```bash
Connected!
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{YhtZCfK0YQfI10vHBNoA_TpEJC_.QX5EDO0wyN4ETMzEzW}
hacker@piping~grepping-live-output:~$ 
```

## What I learned

The "pipe" operator ``|`` lets you avoid the need to store results in a file. Standard output from the command to the left of the pipe will be connected to (piped into) the standard input of the command to the right of the pipe.