# Explicit relative paths, from /

We were asked to run ``/challenge/run`` using a relative path that involved "." to receive the flag.

## My solve
**Flag: 'pwn.college{MfLTu5t8RuDz-8l4gur8hNkdjW8.QXwUTN0wyN4ETMzEzW}'** 

I used ``cd`` to change into the root directory, and then ran ``./challenge/run`` (explicit relative path) which is the same as ``challenge/run`` (implicit relative path) to receive the flag. 

```bash
Connected!
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{MfLTu5t8RuDz-8l4gur8hNkdjW8.QXwUTN0wyN4ETMzEzW}
```

# What I learned

Every directory has two implicit entries you can reference in paths which are "." and ".." . "." refers to the same directory. 
