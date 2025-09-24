# Tab completion on commands

In this challenge, there exists a command ``pwncollege`` which gives you the flag. We must type "pwncollege" and hit tab to autocomplete it to receive the flag.

## My solve
**Flag: 'pwn.college{A9DdtLw9b63vumqi1c8nCZjy9Nb.0VN0EzNxwyN4ETMzEzW}'**

I typed ``pwncollege`` and then hit *TAB* to which it autocompleted the command to ``pwncollege-4778``. Hitting enter resulted in it outputting the flag.

```bash
Connected!
hacker@globbing~tab-completion-on-commands:~$ pwncollege-4778 
Correct! Here is your flag:
pwn.college{A9DdtLw9b63vumqi1c8nCZjy9Nb.0VN0EzNxwyN4ETMzEzW}
hacker@globbing~tab-completion-on-commands:~$ 
```

## What I learned
I learned that you can use tab-completion not only on files, but also on commands.