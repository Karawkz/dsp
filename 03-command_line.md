# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

> > 'ls' - looks at the folder you are in, and then "lists" the files and folders inside it  
'pwd' - outputs the name of the directory you are currently in, called the working directory  
'cd' - changes the working directory  
'cd ..' - to move up one directory; cd ../etc - to move back and change  
'mkdir' - make directory  
'touch try.txt' - creates a new file inside the working directory  
'cp' - copies; note that cannot copy into current directory; cp * satire/; cp m*.txt scifi/ - all files starting with 'm'    
'mv' - moves to directory; can rename  
'rm' - removes files
'rm -r' - removes directory
'cat' - view contents of a text file
'sort' - sorts in alphabetical order
'uniq' - only words
'grep' - "global regular expression print"; searches lines matching a pattern
'grep -i' - case sensitive
'sed' - stream editor; find and replace

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

> > 'ls' - looks at the folder you are in, and then "lists" the files and fold\
ers inside it  
'ls -a' - also lists the files and directories starting with a dot  
'ls -l' - lists all contents of a directory in long format  
'ls -t' - orders files and directories by the time they were last modified
'ls -lh' - lists long format with readable file size
'ls -lah' - lists long format including hidden files with readable file size
'ls -Glp' - lists in long format enabling colorised output with '/' after each filename if the file is a directory
'man ls' - where to find out everything

---
### Q3.  More List Files in Unix  

'Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

> > 'ls -q', 'ls -r', 'ls -S', 'ls -A', 'ls -h'
I don't find this particularly exhilarating but okay...

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > It reads data from stdin and executes a command that is supplied to it as an argument based on the input read.
Echos stdin.
xargs find -name
oHai, world!