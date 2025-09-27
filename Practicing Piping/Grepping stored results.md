# Grepping stored results

In this challenge, we were asked to: 

1. Redirect the output of /challenge/run to /tmp/data.txt.
2. This will result in a hundred thousand lines of text, with one of them being the flag, in /tmp/data.txt. 
3. ``grep`` that for the flag!


## My solve
**Flag: 'pwn.college{4bP3ozbQoojkV8EjuaAMZkzU6Bp.QX4EDO0wyN4ETMzEzW}**

I redirected the output of ``/challenge/run`` to */tmp/data.txt* by running ``/challenge/run > /tmp/data.txt``. I then ``grep``ped for the flag from this flag by running ``grep pwn.college /tmp/data.txt``. Here, the search string was "pwn.college" which is what all the flags begin with, and the path to the file was "/tmp/data.txt". This returned the flag.

```bash
Connected!
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep pwncollege /tmp/data.txt
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{4bP3ozbQoojkV8EjuaAMZkzU6Bp.QX4EDO0wyN4ETMzEzW}
hacker@piping~grepping-stored-results:~$ 
```

## What I learned
I gained practice with the ``grep`` command and redirecting output.