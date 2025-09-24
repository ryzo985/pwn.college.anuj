# Tab completion

Here, we are asked to ``cat`` the file ``/challenge/pwncollege``, but we can't type the filename. We must tab-complete it and read it to receive the flag.

## My solve
**Flag: 'pwn.college{8ceeeQg-OuCjiUZsUbXrfuaAi1Q.0FN0EzNxwyN4ETMzEzW}'**

I ran ``cat /challenge/pwncollege``, and as required by the challenge i hit the tab key after typing "cat /challenge/pwn" to use tab-completion. This returned the flag.

```bash
Connected!
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​ 
pwn.college{8ceeeQg-OuCjiUZsUbXrfuaAi1Q.0FN0EzNxwyN4ETMzEzW}
hacker@globbing~tab-completion:~$ 
```

## What I learned
I learned that when you hit *TAB* on the keyboard while typing on the shell, it will try to figure out what you're typing and automatically complete it. This is called *tab completion* and helps to avoid with mistakes made with file globbing.