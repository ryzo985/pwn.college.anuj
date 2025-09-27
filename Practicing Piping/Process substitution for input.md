# Process substituion for input

In this challenge, we msut use the ``diff`` command to diff to sets of command outputs: ``/challenge/print_decoys``,  which will print a bunch of decoy flags, and ``/challenge/print_decoys_and_flag`` which prints those same decoys plus the real flag. Use process substitution with ``diff`` to compare the outputs of these two programs and find the flag.

## My solve
**Flag: '> pwn.college{wkJ6_z5D9894XPbvFwu9l-rK4S7.0lNwMDOxwyN4ETMzEzW}'**

I ran ``diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)`` which outputted "55a56" and the flag. Here, using process substituion, we hooked up the output of both commands to temporary files, and with these files we ran ``diff`` to find the difference. "55a56" tells us that in the 2nd file, a line has been added after line 55, which here is the flag.

```bash
Connected!
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
55a56
> pwn.college{wkJ6_z5D9894XPbvFwu9l-rK4S7.0lNwMDOxwyN4ETMzEzW}
hacker@piping~process-substitution-for-input:~$ 
```

## What I learned
I learned that Linux provides file-like access to most resources, including the input and output of running programs.

"Process substitution" allows you to hook input and output of programs to arguments of commands.

For reading from a command (input process substitution) use "<(command)". When you do this, bash runs the command and hooks up its output to a temporary file that it will create. This isn't a real file, and is what's called a **Named pipe** (because it has a file name).