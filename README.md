# Name
	fbak - Linux config backup tool with repository backend
# Synopsis
	fbak <command> [<args>]
	fbak save [<args>] filename
	fbak restore [<args>] filename
	fbak history [<args>] filename
	fbak diff filename version number
# Description
	This tool provides a way to track configuration changes in the linux file system. Aside from doing regular backups, or making a temp copy of a file before making changes, this tool use git as a backend to store file changes. In breif, it copies the file to a folder /fbak/path/to/file/filename and /fbak is under git control. 

# Usage

```
 # save the file 
$ fbak save -m 'saved default' /etc/apache/apache.conf 

 # make a change 
$ vim /etc/apache/apache.conf

 # oops! changes messed things up
$ fbak history /etc/apache/apache.conf
Version comment
07a45fa		saved default

$ fbak restore 07a45fa /etc/apache/apache.conf
You have unsaved changes, are you sure you want to overwrite (yes/NO)?
> yes
/etc/apache/apache.conf Restored!



