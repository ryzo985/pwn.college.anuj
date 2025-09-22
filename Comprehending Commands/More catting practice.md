# More catting practice

Here we were asked to retrieve the flag by using the cat command and the flags absolute path, without cding to it. The path was given upon connection to the terminal.

## My solve
**Flag: 'pwn.college{sbXpdbXBlpUCsXZSaUAoCOvaPCn.QXwITO0wyN4ETMzEzW}'**

The ``cd`` comand was blocked, and we were forced to get the flag using ``cat`` with the absolute path as the argument. The flag was in a different directory, which was given to us upon connection. The path was */usr/share/qemu/flag*. So running ``cat /usr/share/qemu/flag`` gave us the flag

```bash
Connected!
You cannot use the 'cd' command in this level, and must retrieve the flag by 
absolute path. Plus, I hid the flag in a different directory! You can find it 
in the file /usr/share/qemu/flag. Go cat it out **without** cding into that 
directory!
hacker@commands~more-catting-practice:~$ cat /usr/share/qemu/flag
pwn.college{sbXpdbXBlpUCsXZSaUAoCOvaPCn.QXwITO0wyN4ETMzEzW}
hacker@commands~more-catting-practice:~$ 
```


## What I learned

I gained practice with catting absolute paths, and learned that any length of path works as long as it's the absolute path when given as an argument to ``cat``.