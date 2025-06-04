

# Description

On this file we'll take a dive into the commands used to filter the output 
that a program generates when is executed, this comes in handy when we're
dealing with enormous amounts of information and we need to get a specific
portion of information from it, this will help us to obtain that information
and reduce the time it takes us.

# The && operator

The use of this operator is as follows:

```
program1 && program2
```

What we are saying here basically is, program1 will execute, if the program 
execution is correct (which will be the same as the program returning true),
then program2 will run. This is very useful in situations when a program needs
to write for example, it's output on a file, but if the program didn't execute
correctly, it mught lead to unexpected errors when executing the second program.

## The cut command

The cut command is useful when we're looking into the contents of a file or
even the output on the terminal and we need to show information whether it's in
the terminal or in a file like this:

```
cat fileName | cut -dDelimitationorCharacterWhereItWillStartSlicing 
-fFieldsToShow
```

On this example, this will show only the second field of the content of the file
after the specified delimiter. 

# The sort command

This command is also used to format the output from a file or command, however,
this one only changes the order of the content displayed instead of hiding
a part of it. Check *man sort* for more information about this command.

# The uniq command

The uniq command is used when we want to check for the contents of a file but
said item has many repeated lines, we would use this command to only show the 
unique lines with different information.

# wc

Word count is also useful as it shows the amount of lines, words and characters
from a file.

# The grep command

This is one of the most useful commands as it contains different features such 
as pattern matching, printing by lines, and many more. As well, more information
about this command can be found using *man grep*.


