## Linux
<img src="https://upload.wikimedia.org/wikipedia/commons/3/35/Tux.svg" alt="javascript logo" width=300 style="border-radius:4px">

>“I don't think that you have any insight whatsoever into your capacity for good until you have some well-developed insight into your capacity for evil.” - *Jordan B. Peterson*
- - - -
<style>a{color:#997;background-color:black;padding:4px;border-radius:3px;}
/* body{background-color:darkgray} */
</style>

ls -ltr   --shows last modified in reverse order

find and locate command:
find / -name "yeet.txt"
locate yeet.txt

locate command uses a cache/db to keep track of files.update the db using the
command :updatedb

soft and hard links
soft links can be created using ln -s command
hard links can be created using ln command (Hard links only work within the same
partition)

Soft links:when the source link is deleted the contents of the destination link is also
deleted
Hard links:when the source link is deleted the contents of the destination link
remains untouched

Hards links point to the same inode
Soft links point to different inode

Types of files in linux:
- Regular file
d Directory
l link
c special file or device file
p named pipe
s socket
b block device

Linux Wildcards:
*
?
[] -  matches any occurrence of character 
{} - suited for numbers (? incomplete)


chown: to change the owner of the file or directory
chgrp: to change the group of the file or directory

chown parserite:parserite changes the owner and group of the file or directory

whatis: shows a small description of a command
command --help:shows a smaller help page
man command:shows the manual for a command

tee: is used to store and view (both at the same time) the output of any command

The command is named after the T-splitter used in plumbing. It basically breaks
the output of a program so that it can be both displayed and saved in a file.It
does both the tasks simultaneosly,copies the result into the specified files or
variables and also display the result.

pipes: A pipe is used by the shell to connect the output of one command directlt
to the input of another command.
syntax: command1 [arguements] | command2 [arguements]

ll: long list
