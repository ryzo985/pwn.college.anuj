# Redirecting input

Here, we were asked to run ``/challenge/run``, but it will require us to redirect the "PWN" file to it, and the "PWN" file must contain the value "COLLEGE". To write that value, we must make use of the ``echo`` command.

## My solve
**Flag: 'pwn.college{Ycv6Bmn8d10b-r_PPthS4Y76JbW.QXwcTN0wyN4ETMzEzW}'**

To write the value "COLLEGE" to filename "PWN", I used the ``echo`` command, and redirected the output to "PWN". This was done by running ``echo COLLEGE > PWN``. After writing the value to the file, I ran ``/challenge/run < PWN``. We were asked to run ``/challenge/run``, but giving redirecting input from filename "PWN", so "< PWN" achieved this. This gave us the flag.

```bash
Connected!
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{Ycv6Bmn8d10b-r_PPthS4Y76JbW.QXwcTN0wyN4ETMzEzW}
hacker@piping~redirecting-input:~$ 
```

## What I learned

I learned that you can redirect input using the character "<", as opposed to the character ">" for errors and output. This allows us to use the content in files as input for commands. 