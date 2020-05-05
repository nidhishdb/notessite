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
the output of a program so that it can be both displayed and saved in a file. It
does both the tasks simultaneosly,copies the result into the specified files or
variables and also display the result.

pipes: A pipe is used by the shell to connect the output of one command directlt
to the input of another command.
syntax: command1 [arguements] | command2 [arguements]

ll: long list

cut -c1 filename     - to get the first line of characters
cut -c1-4 filename - to get character lines from 1-4 range

awk:separates each column in a file
awk '{print $1}'    - gives the first column in a file

grep:searches for patterns in each file.

sort- sort filename         -sorts alphabetically
sort -r filename            -sort reverse alphabetically

uniq- removes repeated lines in a file (have to `sort` it before piping it to uniq)

wc - count the number of lines,words,bytes of file

tar cvf out.tar files/directory   -create tarball
tar xvf file.tar                  -extract tarball

gzip file   -compress file
gzip -d or gunzip compressed-filename  -decompress file

xz filename -compress
xz -d filename -decompress

truncate - shrink or extend the size of a file to the specified size (it causes data to be deleted in order to shrink the size of the file and adds junk values to extend the file size)
truncate -s filesize_in_bytes filename

combining files:
cat file1 file2 file3 > file4

spliting files:
split -l 2 file4 new
This above command splits file4 into 2 lines per file and output newaa,newab,newac

sed:
`sed -i 's/oldstring/newstring/'`  - replace all occurances of oldstring with newstring (-i  option is to write changes to the disk)

`sed '3!s/oldstring/newstring/' filename`  -replace oldstring with newstring except the 3rd line

`sed '/string-to-delete/d' filename` - find and delete lines matching the string

`sed '/^$/d' filename` -remove empty lines from a file

`sed '1d' filename` - remove first line from the file (1 is the line number, replace it with the line you want to delete)

`sed '1,4d' filename` -remove first 4 lines

`sed 's/\t/ /' filename` - replace tabs with spaces

`sed 's/ /\t/' filename` - replace spaces with tabs

`sed -n 5,9p filename` - shows lines from 5 to 9

`sed 5,9d filename` - show lines except 5 to 9

`sed G filename` - adds empty line after each line