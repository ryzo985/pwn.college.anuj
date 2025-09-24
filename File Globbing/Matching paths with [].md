# Matching paths with []

Here, they've again placed a bunch of files in */challenge/files*. Starting from our home directory, we must run ``/challenge/run`` with a single argument that bracket globs into the absolute paths to the "file_b", "file_a", "file_s" and "file_h" files.

## My solve
**Flag: 'pwn.college{8H1pJ1_mxql3URWihJnhjuF_o7y.QX0IDO0wyN4ETMzEzW}'**

No need to change directory, since we were asked to run the program from the home directory. I ran ``/challenge/run /challenge/files/file_[b,a,s,h]``, where the argument was the absolute path to all 4 files, using globbing with the square brackets. This satsified the criteria, and provided me with the flag.

```bash
Connected!
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[b,a,s,h]
You got it! Here is your flag!
pwn.college{8H1pJ1_mxql3URWihJnhjuF_o7y.QX0IDO0wyN4ETMzEzW}
hacker@globbing~matching-paths-with-:~$ 
```

## What I learned
I learned that globbing happens on a *path* basis, and that you can expand entire paths with globbed arguments.