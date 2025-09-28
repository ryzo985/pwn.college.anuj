# Storing command output

In this challenge, we must read the output of ``/challenge/run`` directly into a variable called "PWN" and it will contain the flag 

## My solve
**Flag: 'pwn.college{UVuVu_vIBzS7IQs_NEbzoRt8MsC.QX1cDN1wyN4ETMzEzW}'**

I ran ``PWN=$(/challenge/run)`` which wrote the flag into the "PWN" variable. I then ran ``echo $PWN`` to print the flag from the variable.

```bash
Connected!
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{UVuVu_vIBzS7IQs_NEbzoRt8MsC.QX1cDN1wyN4ETMzEzW}
hacker@variables~storing-command-output:~$ 
```

## What I learned

You can use *Command substitution* if you want to store the output of some command into a variable. The syntax is ``[VARIABLE NAME]=$([COMMAND])``. You can also use backticks instead of "$()", but you cant nest command substitutions (like $(cat $(find / -name flag))). Avoid backticks.