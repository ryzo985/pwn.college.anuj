# Filtering with grep -v

In this challenge, ``/challenge/run`` outputs the flag to stdout, along with over 1000 other decoy flags (containing the word "DECOY" somewhere in the flag) mixed in with the real flag. We must filter out the decoy flags while keeping the real flag using the ``grep`` command and it's invert match option ("grep -v").

## My solve
**Flag: 'pwn.college{wetZPNk8BW_33HuBn_0iy21wSfA.0FOxEzNxwyN4ETMzEzW}'**

I ran ``/challenge/run | grep -v DECOY`` which returned the flag. In this command, the stdout of "/challenge/run" is piped into the command "grep -v DECOY", which means it searches through the text for all the lines that do NOT have "DECOY" in them.

```bash
Connected!
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{wetZPNk8BW_33HuBn_0iy21wSfA.0FOxEzNxwyN4ETMzEzW}
hacker@piping~filtering-with-grep-v:~$ 
```

## What I learned
I learned that the ``grep`` command has an option "-v" which causes it to "invert match", meaning it'll show you lines that do NOT match the search criteria given to the command.