# Searching manuals

We were told to search through the manual page for ``challenge`` for the argument that gives us the flag. To do this we must open the manual page using ``man challenge`` and then use "/" to search any keywords. 

## My solve

I ran ``man challenge`` to open the manual page for the command ``challenge``. Here, under the DESCRIPTION, there were countless arguments with their purpose listed. I then ran ``/flag`` to search for the keyword flag. You move through these instances using "n". On line 779  we found the word flag highlighted within the description of the argument "--ab". So running ``/challenge/challenge --ab`` gave me the flag.

```bash
Connected!
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --ab
Initializing...
Correct usage! Your flag: pwn.college{MV16w_RSrJJbkwDKRir4MqQH8VR.QX1EDO0wyN4ETMzEzW}
hacker@man~searching-manuals:~$ 
```

![Manual page](/.images/SearchingManuals.png)

## What I learned
I learned that you can use "/" to search for any keywords within the manual pages for commands. You can then move across the instances where the keyword has been found by pressing "n" to go next and press "N" to go to the previous result. Instead of "/", we can use "?" to search backwards.
