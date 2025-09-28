# Setting variables

In this level, we must set the "PWN" variable to the value "COLLEGE" to receive the flag.

## My solve
**Flag: 'pwn.college{kugNFd8ix1YY2E21NdbBZhksk5G.QX5UTN0wyN4ETMzEzW}'**

I ran ``PWN=COLLEGE`` to set the value "COLLEGE" to the variable "PWN". This returned the flag.

```bash
Connected!
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{kugNFd8ix1YY2E21NdbBZhksk5G.QX5UTN0wyN4ETMzEzW}
hacker@variables~setting-variables:~$
```

## What I learned

We can use "=" to write to variables. For example, ``VAR=1337`` assigns the value "1337" to the variable "VAR" (No spaces in between though). The names and values of variables are case sensitive.


I learned that the $ is only prepended to access variables. In shell terms, this prepending of $ triggers what is called variable expansion. 