# Position yet elsewhere

We were asked to run the program /challenge/run within another directory, where we were supposed to change to that directory using cd (/usr/include) to recieve  the flag.

## My solve
**Flag: 'pwn.college{0Np59MpVRaT0nmd8e6DrCWjvhN7.QX4QTN0wyN4ETMzEzW}'** 

This was the same as the previous 2 challenges, but with a different path to change to. I ran ``/challenge/run``, to which i got an error message with the correct directory that i must change into using ``cd`` ("/usr/include"). I changed into this directory and then ran ``/challenge/run``, to get the flag.

```bash
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/include directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /usr/include
hacker@paths~position-yet-elsewhere:/usr/include$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{0Np59MpVRaT0nmd8e6DrCWjvhN7.QX4QTN0wyN4ETMzEzW}
hacker@paths~position-yet-elsewhere:/usr/include$ 
```

## What I learned

I did not learn anything new, as this was the same as the two previous challenges.