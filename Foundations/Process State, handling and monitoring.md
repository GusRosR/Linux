
# Description

On this file we will cover the remaining concepts needed to understand and being
able to manage processes.

# Why processes have different states?

On Linux, the kernel is responsible for scheduling the different processes 
running as all of them want CPU time, for this reason, the kernel needs to 
decide what process is going to get that processing time and when is it gonna
receive it. For example, if some process is waiting for a signal from the 
keyboard, it may not need too much CPU time, same thing happens if a process
is waiting for information that will be read from the ROM, a drive or so, it 
doesn't require the CPU to mainstream it to get processing time. However, there
might be processes which already have what they need to execute and they 
need to get that CPU time to get an answer for what they are resolving.

# Which states can a process have?

- Runnable: This refers to a process that is ready to be scheduled for CPU time.
- Sleeping: This is when a process as said before is waiting for something.
- Zombie: This state refers when a process has already got CPU time but its
          waiting to give back the result from being on the CPU so it can be
          killed by the kernel (or maybe another process).
- Stopped: This refers to a process thay may have been doing something and on 
           the middle of it's execution or preparation for processing time, it
           got a signal to stop and it's waiting for the signal to continue 
           where it left off.

This is where what was mentioned on the process overview section is important, 
because if at a determined moment we get too many processes on a zombie state,
it might be wise to check for the parent process that is creating them so we
can terminate it with killall for example. 

# Tools for monitoring processes

The most common used tool for keeping track of the different processes running 
on the system in real-time is *top*. This tool not only gives information about
the processes, it also shows the amount of processes on the different mentioned
states, the amoount of memory, storage and CPU usage. 

However, a tool that is oftenly used in real life is *htop*. It follows the 
same idea as top, the main differences are that it doesn't show the amount
of processes depending on their state, however, htop provides an interface 
where we can modify the niceness and even kill a process on the same screen. 
Also, it can search for a pattern so we can find easier a process and some more
features. 

Another command used to look for process executions with less information is ps.
This command shows the running processes only with their PID, the time they
were launched and the command or action that it's being performed.
