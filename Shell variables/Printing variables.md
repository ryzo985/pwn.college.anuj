# Printing variables

In this challenge, ``/challenge/run`` will not and can not give you the flag. The flag has been put into a variable called "FLAG". We can have the shell print it out, using ``echo``.

## My solve
**Flag: 'pwn.college{8vtMJyUsXzqaFqEjroxS22RpgRF.QX3UTN0wyN4ETMzEzW}'**

I ran ``echo $FLAG`` to receive the flag. The flag was written to the variable "FLAG", and to use ``echo`` to print this flag, we must pass the name of it as an argument, prepending the variable name with a "$". 

```bash
Connected!
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{8vtMJyUsXzqaFqEjroxS22RpgRF.QX3UTN0wyN4ETMzEzW}
hacker@variables~printing-variables:~$ 
```


## What I learned
I learned that the command line interface is colloquially referred to as a "shell", programs written in this language are referred to as "shell scripts". The shell supports variables.


I learned that you can also print out variables with echo, by prepending the variable name with a $. I also learned that there's a variable named "PWD", which always holds the cwd of the current shell.