# Linking files
In this challenge, ``/challenge/catflag`` reads out "/home/hacker/not-the-flag" instead.
Here we had to create a symbolic link between the not-the-flag file and /flag so that when catflag is run, it reads not-the-flag which then in turn reads /flag, giving us the actual flag.

## My solve
**Flag: 'pwn.college{QgVDGhEV3sezdt_q8zNqpvsJhxU.QX5ETN1wyN4ETMzEzW}'**

So, running catflag reads out "not-the-flag". We can use this to give us the flag from */flag* by creating a symlink between "not-the-flag" and "/flag". Running ``ln -s /flag /home/hacker/not-the-flag`` creates this symlink, with "/flag" as the original file. Then, after ``cd``ing to */challenge*, and running ``catflag`` (or ./catflag in this case), I received the flag.

```bash
Connected!
hacker@commands~linking-files:~$ cd /challenge
hacker@commands~linking-files:/challenge$ cat catflag
#!/opt/pwn.college/bash

fold -s <<< "About to read out the /home/hacker/not-the-flag file!"
cat /home/hacker/not-the-flag
hacker@commands~linking-files:/challenge$ ln -s catflag /flag
ln: failed to create symbolic link '/flag': File exists
hacker@commands~linking-files:/challenge$ ln -s /home/hacker/not-the-flag file /flag
ln: target '/flag': Not a directory
hacker@commands~linking-files:/challenge$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:/challenge$ cat catflag
#!/opt/pwn.college/bash

fold -s <<< "About to read out the /home/hacker/not-the-flag file!"
cat /home/hacker/not-the-flag
hacker@commands~linking-files:/challenge$ ln -s /flag /home/hacker/not-the-flag
ln: failed to create symbolic link '/home/hacker/not-the-flag': File exists
hacker@commands~linking-files:/challenge$ cat catflag
#!/opt/pwn.college/bash

fold -s <<< "About to read out the /home/hacker/not-the-flag file!"
cat /home/hacker/not-the-flag
hacker@commands~linking-files:/challenge$ ./catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{QgVDGhEV3sezdt_q8zNqpvsJhxU.QX5ETN1wyN4ETMzEzW}
hacker@commands~linking-files:/challenge$ 
```

## What I learned 

I learned that there are links that are used when more than one program wants to access the same data, but they expect the data to be in different places. 
Two types of links - soft/symbolic and hard links. A hard link is an alternate address that indexes the data (accesses to the hard link and to the original file are completely identical). A symbolic link contains the original file name. When you access the symlink, Linux automatically recognizes that it's a symlink, reads the original file name, and accesses that file.
Symbolic links (symlinks) are created using **"ln -s -original file- -link path-"**
The ``file`` command tells you what type of file it is and recognizes symlinks.

## References
[Video on linux linarium](https://www.youtube.com/watch?v=m55AtwjBXpE&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&t=4s)
