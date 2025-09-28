# Printing exported variables

In this challenge, we must run ``env``, and look through the output to find the "FLAG" variable.

## My solve
**Flag: 'pwn.college{0qEiePxbq8iBIubgcuUHyQQaGVZ.QX4UTN0wyN4ETMzEzW}'**

I ran ``env`` which outputted a list of all every exported variable set in the shell. In this list, I found the "FLAG" variable, which had the value of the flag. 

```bash
Connected!
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=409850578be16be996fce5c651cac8ddd6c724082848921064d40f882e7a2f22
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{0qEiePxbq8iBIubgcuUHyQQaGVZ.QX4UTN0wyN4ETMzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
hacker@variables~printing-exported-variables:~$ 
```

## What I learned
I learned about the ``env`` command, which prints out every exported variable set in your shell.