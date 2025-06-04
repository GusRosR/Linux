
# Description

This file will contain the explanation of two core concepts on Linux; pipes and redirection. These lay the foundation that explains why is this operating systemis mostly known for it's efficiency as well as many other features:

# Pipes

Pipes on Linux are nothing more than something like this:

```
program1 | program2
```

Now, at first this might not be too informative but it's simple. What we are
saying on this line of command is, run program1, every program on Linux receives
an input and generates an output, after program1 finishes running, the pipe 
symbol or "|" indicates that the output generated from program1 will be sent
as the input for program2. This is something really useful because it allows
us to run different commands chained to each other expecting a specific result
reducing the amount of commands to be typed after the completition of another
and also in order to obtain information or a behavior from a program or set
of programs.

# Redirection

Now, this concept is sometimes linked to the pipes or pipelining. On Linux,
when we execute a process, there are three main channels involved in it's 
execution. The first one is standard input, by default this is the keyboard 
from our computer, we have also the standard output which is the terminal shell
and finally we have the error output. These three channels have a specific
number that goes from 0 to 2 (respectively). However, there are times when we
may need the output of a program to be saved on a document and maintaining
screenshots is not practical. For this reason, we can tell the system to write
down the output from a program into a file. To do this we can do the following:

```
echo "Hello World" > foo.txt
```

Now, when we use this command, we will have anything we write afterwards
overwritten with just one > sign, in order for us to append different outputs 
to a file that already contains something or we want to print periodical logs
for example we use >>. Whenever we want to redirect the error output we just 
need to follow the same methodology but writing just before the greater than
the file descriptor number (in this case 2).

For input redirection instead of using the > sign we'll use the < sign.
