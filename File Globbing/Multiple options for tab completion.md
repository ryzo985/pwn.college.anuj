# Multiple options for tab completion

Here, we were told that there was a directory */challenge/files* with a bunch of files in it starting with "pwncollege" and we must use tab-complete from */challenge/files/p* or so to make our way to the flag.

## My solve
**Flag: 'pwn.college{o6Q2X2PaaVSkRuzaWBWN8yh60kf.0lN0EzNxwyN4ETMzEzW}'**

I typed ``/challenge/files/p`` and hit the tab key, which expanded it to ``/challenge/files/pwn``. After hitting the *tab* key for the second time, it printed out the options. Nothing seemed to stick out so I was about to start ``cat``ing them all individually one-by-one, but when I used tab-completion on the cat line ``cat /challenge/files/pwncollege-fla`` it printed out the options, one of which was "pwncollege-flag". So i ``cat``ted this to receive the flag.

```bash
Connected!
hacker@globbing~multiple-options-for-tab-completion:~$ /challenge/files/pwn
pwn                    pwncollege-family      pwncollege-hacking
pwn-college            pwncollege-flamingo    
pwn-the-planet         pwncollege-flyswatter  
hacker@globbing~multiple-options-for-tab-completion:~$ /challenge/files/pwn
pwn                    pwncollege-family      pwncollege-hacking
pwn-college            pwncollege-flamingo    
pwn-the-planet         pwncollege-flyswatter  
hacker@globbing~multiple-options-for-tab-completion:~$ /challenge/files/pwn
pwn                    pwncollege-family      pwncollege-hacking
pwn-college            pwncollege-flamingo    
pwn-the-planet         pwncollege-flyswatter  
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-fla
pwncollege-flag      pwncollege-flamingo  
hacker@globbing~multiple-options-for-tab-completion:~$ cat /challenge/files/pwncollege-flag
pwn.college{o6Q2X2PaaVSkRuzaWBWN8yh60kf.0lN0EzNxwyN4ETMzEzW}
hacker@globbing~multiple-options-for-tab-completion:~$ 
```

## What I learned
I learnt that when there are multiple options that match with the tab completion, it auto-expands to the first point where there are multiple options, and when you hit *TAB* a second time, it'll print out those options.