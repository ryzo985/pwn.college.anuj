# Program and absolute paths

We were asked to invoke the ``run`` program within the challenge directory which was in the / directory to recieve the flag.

## My solve
**Flag:** 'pwn.college{04fdt_9FSNOHU20LvcqA6P1Yh54.QX1QTN0wyN4ETMzEzW}'

The challenge program is named "run" and is within the challenge directory which ultimately comes under the root directory. So, the absolute path to run the "run" program would be ``/challenge/run``.

```bash
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{04fdt_9FSNOHU20LvcqA6P1Yh54.QX1QTN0wyN4ETMzEzW}
hacker@paths~program-and-absolute-paths:~$ 
```

## What I learned

I learned that other directories that lie under the root directory can be accessed by adding them after the root "/", and programs under these inner directories can be invoked this way through their absolute paths.
