
Everything in Linux is an object, which at the same time have owners. Typically
we own the objects we create, as we have seen we have an admin account, the so
called super user called root and he is the owner of everything inside the 
system.

An important thing to know is that when we start a process (which is the same
as a program), for example Firefox, that process will possibly start other 
processes but the process in execution won't have any more permissions than the 
user who started it has. 

This might look like a basic concept, nevertheless it's important that we note 
this because is one of the main premises of system administration and even 
security, because this means that every process running on the system as well as
files, directories and even links have an owner and a group, and every one of
them have different levels of permissions, on the big picture this leads us to
understand that one of the main goals of a sysadmin is keeping a clear and
thought structure of a system as well as keeping different levels of clearances
to provide security to the different groups of a company using it.
