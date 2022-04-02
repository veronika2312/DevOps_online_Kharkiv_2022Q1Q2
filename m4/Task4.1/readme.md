Task1.Part  <br /> 
1) Log in to the system as root (or sudo-er).  <br /> 
![login](1.png) <br />

2) Use the passwd command to change the password. Examine the basic parameters
of the command. What system file does it change *? <br />
 - Passwd command changes file: /etc/passwd
 ![passwd](2.png) <br />

3) Determine the users registered in the system, as well as what commands they
execute. What additional information can be gleaned from the command execution?  <br />
- Login, Name, Tty, Idle, Login Time, Office, Office Phone, Host. <br />
![finger](3.png) <br /> 

4) Change personal information about yourself. <br />
![4](4.png) <br /> 

5) Become familiar with the Linux help system and the man and info commands.
Get help on the previously discussed commands, define and describe any two keys
for these commands. Give examples. <br />
![5](5.png) <br /> 

6) Explore the more and less commands using the help system. View the contents of
files .bash* using commands. <br />
![6](6.png) <br /> 


7) * Determine  the  last  logon  time  for  all  users.Tip:  You  should  read  the documentation for the finger command. <br />
![7](7.png) <br /> 

8) * List the contents of the home directory using the ls command, define its files
and directories. Hint: Use the help system to familiarize yourself with the ls
command. <br />
![8](8.png) <br /> 


Task1.Part <br />

1) Examine the tree command. Master the technique of applying a template, for
example, display all files that contain a character c, or files that contain a specific
sequence of characters. List subdirectories of the root directory up to and including
the second nesting level. <br />
 ![2.1](2.1.png) <br />

2) What command can be used to determine the type of file (for example, text or
binary)? - the "file" command. Give an example.  <br />
 ![2.2](2.2.png) <br />

3) Master the skills of navigating the file system using relative and absolute paths.
How can you go back to your home directory from anywhere in the filesystem? ("cd ~ ") <br />

4) Become familiar with the various options for the ls command. Give examples of
listing directories using different keys. Explain the information displayed on the
terminal using the -l and -a switches.  <br />
    -a, --all = do not ignore entries starting with . <br />
    -l = use a long listing format <br />
![2.4](2.4.png) <br />


5) Perform the following sequence of operations:  <br />

- create a subdirectory (subdir) in the home directory;  <br />

- in this subdirectory create a file containing information about directories located in
the root directory (using I/O redirection operations);  <br />
![2.5](2.5.png) <br />
- view the created file;  <br />

- copy the created file to your home directory using relative and absolute addressing.  <br />
![2.6](2.6.png) <br />
- delete the previously created subdirectory with the file requesting removal;  <br />
- delete the file copied to the home directory.  <br />
![del](del.png) <br />

6) Perform the following sequence of operations:  <br />

- create a subdirectory test in the home directory;  <br />
![6t](6t.png) <br />

- copy the .bash_history file to this directory while changing its name to
labwork2;  <br />
![6t2](6t2.png) <br />

- create a hard and soft link to the labwork2 file in the test subdirectory;  <br />

- how to define soft and hard link, what do these concepts; <br />
The difference between hard links and soft (or symbolic) links comes down to what they reference. <br />
Hard links point, or reference, to a specific space on the hard drive. You can have multiple files hard linked to the same place in the hard drive, but if you change the data on one of those files, the other files will also reflect that change. <br />
Symbolic links work a bit differently. A symbolic link still points to a specific point on the hard drive, but if you create a second file, this second file does not point to the harddrive, but instead, to the first file.<br />


- change the data by opening a symbolic link. What changes will happen and why  <br />
If i make changes in the link file, the original file is also changed.<br />

- rename the hard link file to hard_lnk_labwork2;  <br />
- rename the soft link file to symb_lnk_labwork2 file;  <br />
- then delete the labwork2. What changes have occurred and why?  <br />
![6t3](6t3.png) <br />

7) Using the locate utility, find all files that contain the squid and traceroute
sequence.  <br />

![7t](7t.png) <br />

8) Determine which partitions are mounted in the system, as well as the types of
these partitions.  <br />
![8t](8t.png) <br />

9) Count the number of lines containing a given sequence of characters in a given
file.  <br />
![9t](9t.png) <br />

10) Using the find command, find all files in the /etc directory containing the host
character sequence.  <br />
![10t](10t.png) <br />

11) List all objects in /etc that contain the ss character sequence. <br /> 
![11t](11t.png) <br />
How can I duplicate a similar command using a bunch of grep?  <br />
![111t](111t.png) <br />
12) Organize a screen-by-screen print of the contents of the /etc directory. Hint: You
must use stream redirection operations.  <br />
![12t](12t.png) <br />

13) What are the types of devices and how to determine the type of device? Give
examples.  <br />

![13t](13t.png) <br />

14) How to determine the type of file in the system, what types of files are there?  <br />
- Linux supports seven different types of files. These file types are the Regular file, Directory file, Link file, Character special file, Block special file, Socket file, and Named pipe file. <br />
1. The simplest file command is as follows where you just provide a file whose type you want to find out. ($ file etc)<br />
2. You can also pass the names of the files to be examined from a file (one per line), which you can specify using the -f flag as shown. ($ file -f files.list
) <br />
![14t](14t.png) <br />

15) * List the first 5 directory files that were recently accessed in the /etc directory.  <br />
![15t](15t.png) <br />

