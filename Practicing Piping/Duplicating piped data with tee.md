# Duplicating piped data with tee

In this challenge, we must pipe ``/challenge/pwn`` into ``/challenge/college``, but we will need to intercept the data to see what "pwn" needs from us.

## My solve
**Flag: 'pwn.college{Yuof9dLYFuBWo9tXoFJGrECd2R4.QXxITO0wyN4ETMzEzW}'**

I ran ``/challenge/pwn | tee intercept | /challenge/college``. This intercepts the data from "/challenge/pwn" and passes it to "/challenge/college", but also duplicates and stores it in filename "intercept". I then run ``cat intercept`` to read the file, which tells me that passing ``/challenge/pwn`` the argument "--secret [SECRET_ARG]" where SECRET_ARG = "Yuof9dLY" is the proper usage of the command. So running ``/challenge/pwn --secret Yuof9dLY | /challenge/college`` returns the flag.

```bash
Connected!
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee intercept | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat intercept
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "Yuof9dLY"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --Yuof9dLY | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn Yuof9dLY | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret Yuof9dLY | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{Yuof9dLYFuBWo9tXoFJGrECd2R4.QXxITO0wyN4ETMzEzW}
hacker@piping~duplicating-piped-data-with-tee:~$ 
```

## What I learned
I learned that the ``tee`` command can be used to duplicate data flowing through the pipes to any number of files provided on the command line. You can use multiple pipe operators in this case. It copies the data to the files mentioned, and to stdout. If there is another pipe operator after the ``tee`` command, then the stdout will not be printed to the terminal and will be piped into this command instead. If there isn't, then it is outputted to the terminal as well. This is useful when it comes to debugging. 