# Helpful programs

We were told to use ``--help`` as the manual page was unavailable for the program in this challenge. This told us what value to run with what command, to give us the flag. 

## My solve
**Flag: 'pwn.college{8PAH9zlS0Utd1M0I5BmPXZt4Ufy.QX3IDO0wyN4ETMzEzW}'**

I ran ``/challenge/challenge --help`` to get information on the program so we know what argument to pass to it to receive the flag. I see "-g" which gives the flag if its followed by the correct value. Then there is "-p" which prints the correct value which causes "-g" to give us the flag. So i run ``/challenge/challenge -p``, which lets me know that the secret value is **890**. Running ``/challenge/challenge -g 890`` gives me the flag.

```bash
Connected!
hacker@man~helpful-programs:~$ --help challenge
bash: --help: command not found
hacker@man~helpful-programs:~$ -h challenge
bash: -h: command not found
hacker@man~helpful-programs:~$ --help /challenge/challenge
bash: --help: command not found
hacker@man~helpful-programs:~$ /challenge/challenge --help  
usage: a challenge to make you ask for help [-h] [--fortune] [-v]
                                            [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give
                        you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -g
usage: a challenge to make you ask for help [-h] [--fortune] [-v]
                                            [-g GIVE_THE_FLAG] [-p]
a challenge to make you ask for help: error: argument -g/--give-the-flag: expected one argument
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 890
hacker@man~helpful-programs:~$ /challenge/challenge -g 890
Correct usage! Your flag: pwn.college{8PAH9zlS0Utd1M0I5BmPXZt4Ufy.QX3IDO0wyN4ETMzEzW}
```

## What I learned
I learned that some programs dont have a manpage, and so for these we can pass the argument "--help" to the command to receive some information or documentation on its working.