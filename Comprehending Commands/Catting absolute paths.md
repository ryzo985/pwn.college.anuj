# Catting absolute paths

Here we were asked to read the flag using cat using its absolute path "/flag" to receive the flag.

## My solve
**Flag: 'pwn.college{kWEEHUWDST-WphZp_mbkxe_tV9Q.QX5ETO0wyN4ETMzEzW}'**

The flag is not copied to the home directory, but it is readable through ``cat``. The absolute path is given, and is */flag*. Running ``cat /flag`` gives us the flag.

```bash
Connected!
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{kWEEHUWDST-WphZp_mbkxe_tV9Q.QX5ETO0wyN4ETMzEzW}
hacker@commands~catting-absolute-paths:~$ 
```

## What I learned

I learned that you can specify ``cat``'s arguments as absolute paths. This lets you read from files using their absolute paths. 


