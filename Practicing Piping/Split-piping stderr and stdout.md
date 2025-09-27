# Split-piping stderr and stdout

In this challenge, we must redirect stdout to one program and stderr to another program. We have: 

``/challenge/hack``: this produces data on stdout and stderr

``/challenge/the``: you must redirect hack's stderr to this program

``/challenge/planet``: you must redirect hack's stdout to this program

We must combine our knowledge of ">()", "2>", and "|".

## My solve
**Flag: 'pwn.college{8N_kX4iS_m3tvqKyKgmYlwlrgo_.QXxQDM2wyN4ETMzEzW}'**

We're supposed to redirect stdout (standard output) from ``/challenge/hack`` such that it goes to ``/challenge/planet`` and stderr (standard error) goes to ``/challenge/the``, while keeping them separate. We cannot use the pipe operation "|" here as that would end up mixing them both up. Running ``/challenge/hack > >(/challenge/planet) 2> >(/challenge/the)`` outputs the flag as it achieves this correctly. ``/challenge/hack`` runs the program, and "> >(/challenge/planet)" redirects the stdout to a temporary named pipe connected to the stdin of "/challenge/planet" using Process substitution. Then, "2> >(/challenge/the)" redirects the stderr to a temporary named pipe connected to the stdin of "/challenge/the".

```bash
Connected!
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack > >(/challenge/planet) 2> >(/challenge/the)
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{8N_kX4iS_m3tvqKyKgmYlwlrgo_.QXxQDM2wyN4ETMzEzW}
hacker@piping~split-piping-stderr-and-stdout:~$ 
```

## What I learned

I gained practice with redirecting channels and using these functions.