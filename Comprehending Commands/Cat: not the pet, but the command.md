# Cat: not the pet, but the command!

Here we were asked to run the "cat" command (concatenate) to read from the "flag" file in the home directory to receive the flag.

## My solve
**Flag: 'pwn.college{YuC2NZB42gYZ0HPbuag3uNwQhBI.QXxcTN0wyN4ETMzEzW}'**

The flag was said to be copied to the flag file in our home directory, which is where the shell starts. Running ``cat flag`` after connection outputs the flag.

```bash
Connected!
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{YuC2NZB42gYZ0HPbuag3uNwQhBI.QXxcTN0wyN4ETMzEzW}
```

## What I learned

I learned that the ``cat`` command (concatenate) prints the text from a file to the terminal. It will print the text from multiple files as well if its given multiple arguments.

