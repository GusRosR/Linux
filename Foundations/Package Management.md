
# Description

On this file we will review oneof the first tasks a sysadmin performs, this is
installing software and security updates. 

# apt-get

Advanced Package Tool or apt is the package manager for most of the Debian 
family Linux distros. It takes care of dependencies between aplications and the
Linux kernel itself. To use this command we have to use super user powers, this
is important because we need to be inside the sudoers file to be able to 
obtain those powers, if we're not in it we can write sudo and the password 100
times and we won't get the root permissions. Here are some commands that are
useful using apt-get.

- sudo apt-get update: This visits every repository that contains software that
our system uses in order to work properly and downloads the latest versions or
patches.
- sudo apt-get upgrade: Applies the changes and manages the removal and install
of the new software.
- sudo apt-get install software|packageName: It installs the software specified
on the argument of the command.
- sudo apt-cache search software|packageName: This command searches for software
available to download from apt-get and if any, different versions of a 
software or tool.
- sudo apt-get remove: This uninstalls tools or programs that we specify on the
command's arguments.
