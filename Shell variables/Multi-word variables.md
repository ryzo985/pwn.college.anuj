# Multi-word variables

In this challenge, we must set the variable "PWN" to "COLLEGE YEAH" to receive the flag.

## My solve
**Flag: 'pwn.college{QmdZjJcrnE0AWi4s_ZYV6OlwrVs.QXwYTN0wyN4ETMzEzW}'**

I ran ``PWN="COLLEGE YEAH`` to set the value "COLLEGE YEAH" to the variable "PWN". This was done using quoting, which allowed me to set a multi word value to the variable.

```bash
Connected!
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{QmdZjJcrnE0AWi4s_ZYV6OlwrVs.QXwYTN0wyN4ETMzEzW}
hacker@variables~multi-word-variables:~$ 
```

## What I learned
When we want to set multiple words (this means you have to use spaces between them) to a variable, we must use *quoting*, which means using the double quote character (""") so that the shell reads everything within the quotes as a single token, and sets the value to the variable. For example, ``VAR="1337 SAUCE"`` is the proper use of quoting.