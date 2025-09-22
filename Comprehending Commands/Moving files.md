# Moving files

Here we told to use the ``mv`` command, which moves files from one location to another, to move the "/flag" file to */tmp/hack-the-planet* adn then to run ``/challenge/check`` to receive the flag.

## My solve
**Flag: 'pwn.college{kjHmNBdUxBmETnLKlk4ZHv1aviO.0VOxEzNxwyN4ETMzEzW}'**

Running ``mv /flag /tmp/hack-the-planet`` moves the flag from */flag* to */tmp/hack-the-planet*. Then, running ``/challenge/check`` outputs the flag.

```bash
Connected!
hacker@commands~moving-files:~$ ls
Desktop  a
hacker@commands~moving-files:~$ /flag
bash: /flag: Permission denied
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{kjHmNBdUxBmETnLKlk4ZHv1aviO.0VOxEzNxwyN4ETMzEzW}

hacker@commands~moving-files:~$ 
```

## What I learned
I learned that you can move files around using the ``mv`` command, and by providing it with 2 arguments: first one is the old file name, and second is the new file name.
