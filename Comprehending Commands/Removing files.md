# Removing files

Here we were asked to use the rm command, which deletes files, to delete the "delete_me" file in the home directory and then to run /challenge/check to receive the flag.

## My solve
**Flag: 'pwn.college{o_DUExRVQv2KdMeyiqc4Ll8K9A9.QX2kDM1wyN4ETMzEzW}'**

A *delete_me* file has been created in the home directory, and we must delete it before running ``/challenge/check`` to receive the flag. So first I verify the presence of the file by running ``ls``. Running ``rm delete_me`` deletes the file, and then running ``/challenge/check`` provides us with the flag.

```bash
Connected!
hacker@commands~removing-files:~$ ls
Desktop  a  delete_me
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/run
bash: /challenge/run: No such file or directory
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{o_DUExRVQv2KdMeyiqc4Ll8K9A9.QX2kDM1wyN4ETMzEzW}
hacker@commands~removing-files:~$ 
```

## What I learned
Using the ``rm`` command, we can delete files. You provide the ``rm`` command with the name of the file in the cwd that you wish to delete as an argument.