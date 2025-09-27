# Named pipes

In this challenge, we must create a */tmp/flag_fifo* file and redirect the stdout of "/challenge/run" to it. If successful, ``/challenge/run`` will write a flag to the FIFO.

## My solve
**Flag: 'pwn.college{QyDbhujIa_1afjep5u2QbSkaEKu.01MzMDOxwyN4ETMzEzW}'**

I ran ``mkfifo /tmp/flag_fifo`` to create the FIFO that was asked of us. I then ran ``/challenge/run > /tmp/flag_fifo`` to redirect the stdout of "/challenge/run" to the FIFO. This opened the FIFO for writing, but was blocked until it was also opened for reading. I then opened a second terminal and connected. I then ran ``cat /tmp/flag_fifo``, opening the FIFO for reading as well, which outputted the flag.

Console 1:
```bash
Connected!
hacker@piping~named-pipes:~$ mkfifo /tmp/flag_fifo
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo! 
Bash will now try to open the FIFO for writing, to pass it as the stdout of 
/challenge/run. Recall that operations on FIFOs will *block* until both the 
read side and the write side is open, so /challenge/run will not actually be 
launched until you start reading from the FIFO!
```

Console 2:
```bash
Connected!
hacker@piping~named-pipes:~$ cat /tmp/flag_fifo
You've correctly redirected /challenge/run's stdout to a FIFO at 
/tmp/flag_fifo! Here is your flag:
pwn.college{QyDbhujIa_1afjep5u2QbSkaEKu.01MzMDOxwyN4ETMzEzW}
hacker@piping~named-pipes:~$ 
```

## What I learned
I learned that you can create persistent named pipes that stick around on the filesystem called "FIFOs", which stands for "First (byte) In, First (byte) Out. You can create a FIFO using ``mkfifo ``. 

I learned that running ``ls -l "filename"`` lists the properties of that file, and if it starts with "p", it's a FIFO (pipe). Normal files begin with "-". For FIFOs, we control where they're created, they persist until we delete them, any process can write to them by path, and you can see them with ``ls`` and examine them like files. One problem with FIFOs is that they'll "block" any operations on them until both the read side of the pipe and the write side of the pipe are ready. As in, when one command opens the FIFO in write mode, the operation will hang until something also opens it in read mode, completing the pipe.


Why use a FIFO instead? Here are key differences:

1. No disk storage: FIFOs pass data directly between processes in memory - nothing is saved to disk
2. Ephemeral data: Once data is read from a FIFO, it's gone (unlike files where data persists)
3. Automatic synchronization: Writers block until the readers are ready, and vice-versa. This is actually useful! It provides automatic synchronization. Consider the example above: with a FIFO, it doesn't matter if ``cat myfifo`` or ``echo pwn > myfifo`` is executed first; each would just wait for the other. With files, you need to make sure to execute the writer before the reader.
4. Complex data flows: FIFOs are useful for facilitating complex data flows, merging and splitting data in flexible ways, and so on. For example, FIFOs support multiple readers and writers.
