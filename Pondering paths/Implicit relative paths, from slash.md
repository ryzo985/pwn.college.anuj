# Implicit relative paths, from /

We were asked to run /challenge/run using a relative path while having a current working directory of / to receive the flag.

## My solve
**Flag: 'pwn.college{EM-uFsQmZ2O6Zr_VjipOpqw9E7t.QX5QTN0wyN4ETMzEzW}'** 

Since i needed to run ``/challenge/run`` using a relative path while having a cwd of /, I used ``cd`` to change into the root directory, and then used the relative path which is now ``challenge/run`` to receive the flag.

```bash
Connected!
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{EM-uFsQmZ2O6Zr_VjipOpqw9E7t.QX5QTN0wyN4ETMzEzW}
```

## What I learned

If you use absolute paths, it doesn't matter what directory you are currently in. A relative path is any path that doesn't start at the root ("/"), and is interprated relative to your current working directory (which is the directory where your prompt is currently located at).