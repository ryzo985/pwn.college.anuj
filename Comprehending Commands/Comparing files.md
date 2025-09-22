# Comparing files

Here we were asked to find the difference between 2 text files, one with 100 fake flags and one with those 100 fake flags plus the one real flag. You had to cd to the /challenge directory and then run the diff command to receive the flag.

## My solve
**Flag: 'pwn.college{AV0B9RCTd2OCwjG3ebEJqxK-vKW.01MwMDOxwyN4ETMzEzW}'**

The file at */challenge/decoys_only.txt* contains 100 fake flags, and the file at */challenge/decoys_and_real.txt* contains 100 fake flags plus one real flag. After ``cd``ing to /challenge, running ``diff decoys_only.txt decoys_and_real.txt`` outputs ```64a65``` and then the flag. This 64a65 means that after the 64th line of the first file, a line 65 has been added to the second file, which is the real flag.

```bash
Connected!
hacker@commands~comparing-files:~$ cd /challenge
hacker@commands~comparing-files:/challenge$ diff decoys_only.txt decoys_and_real.txt
64a65
> pwn.college{AV0B9RCTd2OCwjG3ebEJqxK-vKW.01MwMDOxwyN4ETMzEzW}
hacker@commands~comparing-files:/challenge$ 
```

## What I learned

I learned that the ``diff`` command compares two files line by line and shows you what's different between them. For the ``diff`` command, we must provide it with 2 arguments which are both the files we wish to compare. *For example, when the ``diff`` command outputs 2c2, this means that line 2 of the first file and second file changed. Or if it outputs 1a2, this means after line 1 of file 1, theres been a line 2 added to file 2.* 
