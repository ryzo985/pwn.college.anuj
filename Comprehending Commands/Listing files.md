# Listing files

Here we were asked to use the ``ls`` command, which lists the files in the directory mentioned or in the current directory, to find the flag which was renamed to a random name.

## My solve
**Flag: 'pwn.college{k9eOvtoHV3lUEU67-eBRVj_0OYV.QX4IDO0wyN4ETMzEzW}'**

``/challenge/run`` has been renamed to something random, and is within */challenge*. To find it, we must list the files within */challenge* using the ``ls`` command.  ``cd``ing to */challenge*, and then running ``ls``, lists the files within */challenge* as that is now the current working directory and no argument was given to ``ls``. Besides for the challenge description, one file was present named *"16900-renamed-run-15752"*. Running this program using its absolute path ``/challenge/16900-renamed-run-15752`` provides us with the flag.

```bash
Connected!
hacker@commands~listing-files:~$ cd /challenge
hacker@commands~listing-files:/challenge$ ls
16900-renamed-run-15752  DESCRIPTION.md
hacker@commands~listing-files:/challenge$ cd
hacker@commands~listing-files:~$ /challenge/16900-renamed-run-15752
Yahaha, you found me! Here is your flag:
pwn.college{k9eOvtoHV3lUEU67-eBRVj_0OYV.QX4IDO0wyN4ETMzEzW}
```

## What I learned
I learned that the ``ls`` command lists the files in all the directories provided to it as arguments, and if no argument is provided it lists the files in the current working directory.
