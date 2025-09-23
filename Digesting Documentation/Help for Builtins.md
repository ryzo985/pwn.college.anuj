# Help for builtins

Since builtins are handled internally by the shell instead of launching other programs, they dont have man pages. Here, the challenge command is a builtin instead of a program, and to find the related information such as the secret value to be printed along with the print command, we must check its help page using the ``help`` builtin which gives information on builtins or specific builtins.

## My solve
**Flag: 'pwn.college{kONGar_UG85RAO5oPpSM_uayWtZ.QX0ETO0wyN4ETMzEzW}'**

Since ``challenge`` is a builtin, we run ``help challenge``, which displays its information. One of the arguments is "--secret VALUE" which says it prints the flag if the VALUE is correct. Below this, it's states that the VALUE is "kONGar_U". So running ``challenge --secret kONGar_U`` gives us the flag.

```bash
Connected!
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune		display a fortune
      --version		display the version
      --secret VALUE	prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "kONGar_U".
hacker@man~help-for-builtins:~$ challenge --secret kONGar_U
Correct! Here is your flag!
pwn.college{kONGar_UG85RAO5oPpSM_uayWtZ.QX0ETO0wyN4ETMzEzW}

hacker@man~help-for-builtins:~$ 
```

## What I learned
I learned that some commands are not programs with manpages and help options, and instead are built into the shell itself and are called "builtins". They're invoked like commands, but are handled internally by the shell instead of launching other programs.

Running the builtin ``help`` gives you a list of shell builtins, and you can get help on a specific builtin by passing it as an argument to ``help``.
