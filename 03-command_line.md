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

> > 1. `pwd` show current working directory path
> > 2. `mkdir` create a directory
> > 3. `rm -r` deleting a directory
> > 4. `touch file.txt` creating a file using touch command
> > 5. `rm` deleting a file
> > 6. `mv name.txt > new_name.txt` renaming a file
> > 7. `ls -a` listing hidden files
> > 8. `cp -r dir1/file.txt dir2/` copy a file from one directory to another
> > 9. `cat file.txt` output contents of a file to the terminal
> > 10. `sort file.txt` sort the lines alphabetically
> > 11. `grep -i text file.txt` search for text in files
> > 12. `sed 's/search/replace/g'` substitute search string with replace globally

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

> > * `ls` lists all entries in a directory, excluding hidden entries.
> > * `ls -a` lists all entries in a directory, including hidden entries. 
> > * `ls -l` lists all contents in a table format with 7 columns.
> > * `ls -lh` just like `ls -l`, but prints file sizes in a human readable format.
> > * `ls -lah` just like `ls -lh`, but also for hidden entries.
> > * `ls -t` just like `ls`, but sorted by modification time, recent first.
> > * `ls -Glp` The `G` enables colorized outputs, making it easier to distinguish directories and certain files, `l` enables long-form table mode, and `p` puts a slash ('/') after directories.

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

> > 1. `ls -S` sort by file size, largest first
> > 2. `ls -m` displays names as a comma-separated list
> > 3. `ls -1` displays each entry on a line
> > 4. `ls -R` lists all subdirectories and their entries as well
> > 5. `ls -r` reverse sorted order, with directories first

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > `xargs` takes standard input and converts it into arguments to pass into another function, splitting it along the defined delimiter. For example,
> >
> > `find . -name "*.md" | xargs cat >> test.txt`
> >
> > will find all files with the extension ".md" in a directory (and its subdirectories) and pass them onto xargs, where we are using **cat** to read the contents and append them to a test.txt file. This way, xargs can be used to combine the contents of files that fit a particular search query. 

 

