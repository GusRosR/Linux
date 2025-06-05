
# Description

On this file we will cover and understand process signals, which in simple
words are the way processes communicate with each other.

# What is a signal?

Signals can be sent by the kernel, for example when a process fails, when 
a child process has died and the parent process needs to be notified, notify 
that hardware is ready and about so. Now, the way we send signals to a process
is with the *kill* command, this name is given because is the most likely thing
we¿ll be using it for, however, to see all the available options from this 
command we can type *kill -l* and this will list us the different options. 

# Before killing a process

Something important to note is that when killing or stopping a process we need
to use the kill option that doesn't abruptly terminates a process, this is 
because it may happen that when a process is terminated forcefully, it lets 
behind some opened files, configurations or hanging processes. Also, to stop a
process we need to obtain its PID beforehand because that's the argument we're
gonna be giving the kill command.

# Killing all instances from a process

Sometimes we might face some process that we want to terminate but said item has
many more processes involved or running in the background. To achieve this we
need to use the command *killall*, we might have to use sudo in here because
many times we will be stopping processes that don't belong to our user. 

# Killing all processes from a user

In order for us to kill all the processes running or/and started by a specific
user we can use the command *sudo pkill -u userName*. This will stop and 
terminate all processes initialized by the specified user. 
