# Exporting variables

In this challenge, we must invoke ``/challenge/run`` with the "PWN" variable exported and set to the value "COLLEGE", and the "COLLEGE" variable set to the value "PWN" but not exported (e.g., not inherited by /challenge/run). 

## My solve
**Flag: 'pwn.college{8iF-hIHdAPI-STU5t4b4emRs6OV.QXyYTN0wyN4ETMzEzW}'**

I ran ``PWN=COLLEGE COLLEGE=PWN`` to set both variables "PWN" and "COLLEGE" to their respective values as requested by the challenge. I then received confirmation that I did this correctly. Then, I ran ``export PWN`` to export the "PWN" variable. I did not do this for the "COLLEGE" variable as well as the challenge mentioned not to. Finally, I ran ``/challenge/run`` to receive the flag.

```bash
Connected!
hacker@variables~exporting-variables:~$ PWN=COLLEGE COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ export PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{8iF-hIHdAPI-STU5t4b4emRs6OV.QXyYTN0wyN4ETMzEzW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ 
```

## What I learned

I learned that the variables that you set in a shell session are local to that shell process. As in, other commands you run won't inherit them. I also learned that ``sh`` is a minimal shell implementation that is invoked as a child of the main shell process, and its prompt is "$".


You export your variables when you want to mark that they should be leaked into other programs you run. When you export your variables, they are passed into the environment variables of child processes. You can achieve this by running ``export VAR`` where VAR is the variable name.