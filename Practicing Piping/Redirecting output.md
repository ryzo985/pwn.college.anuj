# Redirecting output

Here, we were asked to use output redirection to write the word "PWN" to the filename "COLLEGE" to receive the flag.

## My solve
**Flag: 'pwn.college{kY2VvughGHRnc3LBGnTIfOcde3e.QX0YTN0wyN4ETMzEzW}'**

Since I needed "PWN" to be outputted by the terminal, I used the ``echo`` command. I then redirected the output of this to the filename "COLLEGE" using the ">" character. So, running ``echo PWN > COLLEGE`` wrote "PWN" to the file "COLLEGE" using output redirection of stdout, giving me the flag.

```bash
Connected!
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
pwn.college{kY2VvughGHRnc3LBGnTIfOcde3e.QX0YTN0wyN4ETMzEzW}
hacker@piping~redirecting-output:~$ 
```


## What I learned
I learned that every process in Linux has three initial, standard channels of communication:
    Standard Input is the channel through which the process takes input. For example, your shell uses Standard Input to read the commands that you input.
    Standard Output is the channel through which processes output normal data, such as the flag when it is printed to you in previous challenges or the output of utilities such as ls.
    Standard Error is the channel through which processes output error details. For example, if you mistype a command, the shell will output, over standard error, that this command does not exist.


I learned that you can redirect stdout to files, using the ">" character.