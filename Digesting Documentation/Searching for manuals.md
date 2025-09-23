# Searching for manuals

The argument to run with ``/challenge/challenge`` is under a randomly named manual page, and we must find it.
We were told to read the manual page for the man command by running ``man man`` and look for something to help us find it. We were told we still actually use ``/challenge/challenge`` to obtain the flag, and that we must go through the manual page for ``man`` to find something that lets us search the man page database.

## My solve
**Flag: 'pwn.college{gNugbG0IuvugJa5eFpnJGbGJeEV.QX2EDO0wyN4ETMzEzW}'**

Unfortunately, there is no manual page for ``challenge``. Instead, we run ``man man``. Here, we find the description of an argument that can be run with man to search for keywords in all the manual pages (the man page database). This is ``man -k`` and to this you pass the keyword as an argument **"man -k keyword"**. So after running ``man -k flag``, I look through the results. I spot "gugbuvugae" as it says "print the flag!". I then run ``man gugbuvugae`` to find that if you pass the argument "--gugbuv NUM" where NUM is 052 to ``/challenge/challenge``, it prints the flag. So after running ``/challenge/challenge --gugbuv 052``, I receive the flag.

```bash
Connected!
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man challenge
No manual entry for challenge
hacker@man~searching-for-manuals:~$ /challenge/challenge
Incorrect usage! Please read the hidden challenge man page!
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k flag
dpkg-buildflags (1)  - returns build flags to use during package build
Dpkg::BuildFlags (3perl) - query build flags
fegetexceptflag (3)  - floating-point rounding and exception handling
fesetexceptflag (3)  - floating-point rounding and exception handling
gugbuvugae (1)       - print the flag!
i386 (8)             - change reported architecture in new program environmen...
ioctl_iflags (2)     - ioctl() operations for inode flags
linux32 (1)          - change reported architecture in new program environmen...
linux64 (1)          - change reported architecture in new program environmen...
pcap-config (1)      - write libpcap compiler and linker flags to standard ou...
security_compute_av_flags (3) - query the SELinux policy database in the kernel
security_compute_av_flags_raw (3) - query the SELinux policy database in the ...
set_matchpathcon_flags (3) - set flags controlling the operation of matchpath...
set_matchpathcon_invalidcon (3) - set flags controlling the operation of matc...
set_matchpathcon_printf (3) - set flags controlling the operation of matchpat...
setarch (1)          - change reported architecture in new program environmen...
setarch (8)          - change reported architecture in new program environmen...
x86_64 (8)           - change reported architecture in new program environmen...
hacker@man~searching-for-manuals:~$ man gugbuvugae
hacker@man~searching-for-manuals:~$ /challenge/challenge --gugbuv 052
Correct usage! Your flag: pwn.college{gNugbG0IuvugJa5eFpnJGbGJeEV.QX2EDO0wyN4ETMzEzW}
hacker@man~searching-for-manuals:~$ 
```

![Manual page for gugbuvugae](/.images/SearchingForManuals.png)

## What I learned

I learned of the usage of ``man -k``, which lets us search through the manpages for keywords, letting us look for commands specifically. The syntax for this is **man -k keyword**, where the keyword is your search criteria.