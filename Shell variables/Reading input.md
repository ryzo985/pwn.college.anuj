# Reading input

In this challenge, we must use ``read`` to set the "PWN" variable to the value "COLLEGE" to receive the flag.

## My solve
**Flag: 'pwn.college{4kaokeplYpxgK_fXzv5yWDT1rKU.QX4cTN0wyN4ETMzEzW}'**

I ran ``read -p "INPUT: " PWN`` which prompted me to input a value to be stored into the variable "PWN". I added "-p "INPUT: "" for increased readability. After inputting the value "COLLEGE", i received the flag.

```bash
Connected!
hacker@variables~reading-input:~$ read -p "INPUT: " PWN
INPUT: COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{4kaokeplYpxgK_fXzv5yWDT1rKU.QX4cTN0wyN4ETMzEzW}
hacker@variables~reading-input:~$ 
```

## What I learned
Reading input from the user is done using the ``read`` builtin, which reads input into a variable. Using the "-p" argument allows you to specify a prompt. For example, ``read -p "INPUT: " MY_VARIABLE`` where *"Input: "* is the prompt outputted, and *MY_VARIABLE* is where the input is stored. ``read`` reads data from your standard input.