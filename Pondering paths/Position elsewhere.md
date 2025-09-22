# Position elsewhere

We were asked to invoke the /challenge/run program in yet another directory (/usr/bin) using the cd commmand to recieve the flag. 

## My solve
**Flag:** 'pwn.college{UEJ5eXCyUq5LWnRgN7Tq-aMsysP.QX3QTN0wyN4ETMzEzW}'

This was the same as the previous challenge, just with a different path to ``cd`` to. I tried to run ``/challenge/run``, to which it told me that i was not in the correct directory. The correct directory was "/usr/bin", to which i used the ``cd`` command to change into. From there, i ran ``/challenge/run`` again where it worked as i invoked it from the right directory.

```bash
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/bin directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /usr/bin
hacker@paths~position-elsewhere:/usr/bin$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{UEJ5eXCyUq5LWnRgN7Tq-aMsysP.QX3QTN0wyN4ETMzEzW}
hacker@paths~position-elsewhere:/usr/bin$ 
```

## What I learned

I did not learn anything new this challenge as it was the same as the previous. It served as practice with the ``cd`` command.
