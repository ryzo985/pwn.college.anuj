# Reading manuals

We were told to find the flag by checkign the manual page for the challenge command, which tells you about an argument you can use with the command to print the flag.

## My solve
**Flag: 'pwn.college{sbDozQIeh-u96Xreohwv6Bs_zBV.QX0EDO0wyN4ETMzEzW}'**

I ran ``man challenge``, which opened the manual page for the ``challenge`` command. In the description of this manpage, I spotted "--sbozeh NUM" under the DESCRIPTION section. This stated that it reads the flag if NUM is 966 when passed as an argument to ``challenge``. So running ``/challenge/challenge --sbozeh 966`` returned the flag.

```bash
Connected!
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ challenge -sbozeh 966
bash: challenge: command not found
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ challenge --sbozeh 966
bash: challenge: command not found
hacker@man~reading-manuals:~$ /challenge --sbozeh 966
bash: /challenge: Is a directory
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --sbozeh 966
Correct usage! Your flag: pwn.college{sbDozQIeh-u96Xreohwv6Bs_zBV.QX0EDO0wyN4ETMzEzW}
hacker@man~reading-manuals:~$ 
```

## What I learned
I learned that the ``man`` command (short for manual) displays the manual of the command you pass to it as an argument. You can scroll around the manual page using the up and down arrowkeys, and you hit "q" to quit. Manual pages are stored in a centralized database, located at */usr/share/man*