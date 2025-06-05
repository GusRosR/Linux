
# Description

This file will contain important concepts and commands used for user 
administration in Linux.

# The */etc/passwd* file 

There are three main files where we will find information about what makes up a user on the filesystem. The first one is */etc/passwd*. If we were to tail that file and see each one of the users registered on the system at that moment, each
one of them will have seven fields. The first field is the username, then we
will see the password of that user. Generally we will see an X, this is because
the password has been moved to */etc/shadow/* to which we will need sudo 
permissions if we want to tail it and this is where the hashed password of
every user lives. Now, keeping up with what we see on the */etc/passwd* file, 
the third field is the user id, then the default group id, then the next three
fields would contain human readable information such as name, surname, phone 
and so on. Next, we have the home directory of the user and the last field 
correspond to the shell the user is using. 

Now, something important to say is that if we look at the whole contents of this
file, we can see that there are about 30 or more users created by the system. 
Practically speaking, this users are in fact names of services which may or may 
not be running on the system. However, technologies like containerization with
docker or similars, tend to use a machine (in Linux) and then push it online. 
However, this is not a good practice as many of this users, as they might not 
be configured to move and break things on our system, it doesn't mean they can't
be manipulated to behave that way, that's why when rolling something online,
specially if it's something used by people with serious foundations on IT, needs
to be trimmed so it has less security flaws.

# The */etc/shadow* file

Speaking once again about the file in */etc/shadow*, we see again the username,
next we find it's password hashed, then we find the date when the password was 
created, the date in which expires, and then the time after expiration that it's
still valid. 

# The */etc/group* file

On this file we find information about the groups, just as with the other 
files, here we find the name of the group, then the group id and finally, the
members of that group. 

One thing important to note is that we can disable a user that does have a 
password to enter the system, to do this we only need to write the "!" symbol.
This indicates that although a user has a password, it's not allowed to login.

# Commands

- useradd nameOfUser: Adds a new user. For this command we can use some 
                      arguments, the most common are; -m create the home
                      directory, -d define the where directory e.g. 
                      */home/someUser*, -u define the user id, -g define the 
                      group id, -s define the default shell, the most common
                      are */bin/bash* and */bin/zsh*. 
- userdel nameOfUser: Deletes an existing user.
- passwd nameOfuser: Creates a password for an existing user. When this happens
                     the system will prompt us for a password two times to 
                     ensure we're writing it properly.
- usermod -L nameOfUser: This locks a user from being able to log in to the 
                         system. 
- usermod -U nameOfUser: This removes the lock for a user so it can log in to
                         the system again.


# Important things when creating a user

When we first create a user, for example:

```
sudo useradd -m -d /home/testuser -s /bin/zsh testuser
```

The user is created with it's home directory and with the default shell as zsh.
However, if we perform the command *ls -la /home/*, we find that our newly 
created user only has absolute permissions for itself, it doesn't have 
permissions for his group or everyone else. In some cases the user created may 
need to be changed as it might not be owned by itself. Remember that to do this
we need to use the command chown and set the owner to the user created, on this
case testuser. Then, the other thing it must be done is changing it's
permissions, again, remember that to do this we need to use the command chmod, 
in this case, we need to assign the numbers 755, so only the user has absolute
permissions and the group and everyone else can only read and execute. To do 
this we need to use the command:

```
sudo chmod 755 /home/testuser
```

Finally, when removing a user, we will get it's records deleted from the files
mentioned on this section, however, the home directory corresponding to that
user will still remain active, it won't belong to any user or group yet, for 
this reason, we'll need to remove it. 


