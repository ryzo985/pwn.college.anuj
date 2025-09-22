# Position thyself

We were asked to execute /challenge/run from a different directory (/usr/share/doc) using cd to recieve the flag.

## My solve
**Flag:** 'pwn.college{Ml9Jgou5KlZTmm_zVsGnxd-0TQh.QX2QTN0wyN4ETMzEzW}'

I tried to execute ``/challenge/run`` but it didn't work, and instead it told me that I'm not currently in the "/usr/share/doc" directory. So i used ``cd`` to change into that directory before running ``/challenge/run`` which then worked to give me the flag.

```bash
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /usr/share/doc directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /usr/share/doc 
hacker@paths~position-thy-self:/usr/share/doc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{Ml9Jgou5KlZTmm_zVsGnxd-0TQh.QX2QTN0wyN4ETMzEzW}
hacker@paths~position-thy-self:/usr/share/doc$ 
```

## What I learned

I learned about the ``cd`` command, which allows you to change directories after passing a path to it as an argument. This affects the "current working directory". I also learned that the terminal prompt shows the current path that your shell is located at: this is shown next to the "hacker@challengename".
