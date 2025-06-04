
# Description

On this file we will discuss details and important concepts about File
Permissions.

When we type the command *ls -l*, we get to see many attributes of the items
that are stored in the location we are working at. In Linux we have 12 bits 
that correspond to the mode, these are stored together with 4 bits of file type
information. In this specific file we will talk about the 9 permission bits. 
Typically, when typing the mentioned command we would get an output like this:
    *drwxr-xr-x*

The first bit (that in this case all bits are represented by letters to make
it easier to understand) corresponds to the file type, if it's a link, 
a directory or a normal file. The three next letters correspond respectivelly
to; read, write and execute. The next three spaces correspond to the same
actions BUT, they are the actions that the group where our user is located can 
perform, on this case, it can read and execute but it can't write. The final 
three letters refer to what anyone else on the system can do with that file,
in this case they can read and execute but not write.

Now, there might be cases where we don't want a specific user, group or someone
on the same system to have some or any kind of access to a file or directory 
inside it. As a sysadmin, something we can do is change the mode of the file or
directory using the *chmod* command. With this command we have 3 bits. Before
let's describe what each number on each bit means:

- 7: Read, write and execute
- 6: Read and write
- 5: Read and execute
- 4: Read only
- 3: Write and execute
- 2: Write only
- 1: Execute only
- 0: No permissions

The reason why we have 3 bits is as we've mentioned on the explanation above;
permissions for the owner, permissions for the group and permissions for 
everyone else. In some manner, we can change the behavior of the permissions 
when someone inside our system creates a file, we may need to make the files
created by a user non-readable or editable by another user. In order for us 
to do it, we can edit the file located in ***/etc/login.defs*** (on Debian)
based systems. Once inside the file we need to search for the word *umask*.
Once in there we will find that umask is followed by three numbers, which in 
this case represent the so called permission bits. This property follows the 
same chmod number permissions but they are reversed. By default, on many systems
the umask has a value of 022. When we say that it works reversed, we mean that
the numbers represent what is being taken away to each entity on our system. In 
this case, the owner get's taken away nothing, that's why it's 0. The group and
everyone else is being taken away the write permission. 

Finally, we might need at some point change the owner of a file or directory.
In order to do so, we need to use the *chown* or change owner command. The 
syntax is: *chown owner:group resource*. It's obvious to note that the 
previous user (if not on the newly declared owner) or users from a group will 
not be able to access the resource until they are granted with the appropriate 
permissions. 
