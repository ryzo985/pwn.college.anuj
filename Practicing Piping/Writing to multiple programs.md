# Writing to multiple programs

In this challenge, we have ``/challenge/hack``, ``/challenge/the``, and ``/challenge/planet``. Run the ``/challenge/hack`` command, and duplicate its output as input to both the ``/challenge/the`` and the ``/challenge/planet`` commands to receive the flag.

## My solve
**Flag: 'pwn.college{w-eVS5Vybh_mTw888zBdxCLLRQ6.QXwgDN1wyN4ETMzEzW}'**

I ran ``/challenge/hack | tee >(/challenge/planet) >(/challenge/the)`` which outputted the flag. On the left side of the pipe operation, I ran the ``/challenge/hack`` command. On the right side, I duplicated its output as input to both the ``/challenge/the`` and the ``/challenge/planet`` commands. This satisfied the criteria, and returned me the flag.

```bash
Connected!
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/planet) >(/challenge/the)
This secret data must directly and simultaneously make it to /challenge/the and 
/challenge/planet. Don't try to copy-paste it; it changes too fast.
2780419572769222320
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{w-eVS5Vybh_mTw888zBdxCLLRQ6.QXwgDN1wyN4ETMzEzW}
```

## What I learned

I learned that we can also use process substitution to write to commands. I learned that if you want to duplicate data into 2 files using ``tee`` but don't want to output to terminal as well, you can do for example ``tee THE > PLANET`` where both "TEE" and "PLANET" are files. This duplicates the data to both files, while leaving the terminal empty. This is because we redirected stdout to "PLANET".

To write to a command (output process substitution), use ">(command)". This hooks up the command's input to a temporary named pipe file. When commands write to this file, the data goes to the standard input of the command.