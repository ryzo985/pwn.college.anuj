# Implicit relative path

We were asked to invoke the run program from within the challenge directory itself, using "." to receive the flag.

## My solve
**Flag: 'pwn.college{0xFYa4Q9Hb_3-tKPCMgDtwrwVDY.QXxUTN0wyN4ETMzEzW}'**

I need to run the "run" program from the /challenge directory. Since a naked path wouldn't work, which would just be inputting ``run``, I need to use an implicit relative path and to do that I have to start it with "./". After using ``cd`` to change into the /challenge directory, running ``./run`` gives me the flag.

```bash
Connected!
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{0xFYa4Q9Hb_3-tKPCMgDtwrwVDY.QXxUTN0wyN4ETMzEzW}
```

## What I learned

I learned that you can't execute programs within the current working directory (cwd) using a naked path. This is a safety measure on Linux's side in case the program has the same name as a core system utility, and returns an error message. 
Instead, you need to refer to it by preceding it with a "./" (ex: "./run")
