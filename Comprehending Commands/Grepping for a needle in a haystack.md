# Grepping for a needle in a haystack

Here we were asked to use the grep command to search for the flag in a text file with a hundred thousand lines of text. We were told that the flag always starts with "pwn.college" and the path to the text file is "/challenge/data.txt".

## My solve
**Flag: 'pwn.college{IM5gR8UroH8jSekC_ldRrYPVkiy.QX3EDO0wyN4ETMzEzW}'**

We've been tasked with searching for the flag within the text file with the path */challenge/data.txt*. Since the flag always starts with "pwn.college", it makes sense to provide that as the search string for the ``grep`` command. So running ``grep pwn.college /challenge/data.txt`` returns the flag.

```bash
Connected!
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{IM5gR8UroH8jSekC_ldRrYPVkiy.QX3EDO0wyN4ETMzEzW}
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ 
```

## What I learned

I learned that when the files we mean to use ``cat`` on are too big, the ``grep`` command can be used to effectively search for the content we need.
The ``grep`` command prints all the lines of text in a file that include the string you are searching for. The ``grep`` command requires 2 arguments, with the first one being the string of data you're searching for, and the second argument being the path to the file. *Ex: grep string /path/to/file*

