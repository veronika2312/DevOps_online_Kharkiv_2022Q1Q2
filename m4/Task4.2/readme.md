Task2 <br /> 
Task assignment. <br />
1) Analyze the structure of the /etc/passwd and /etc/group file, what fields are present in it, what users exist on the system? Specify several pseudo-users, how to define them? <br />
![1](1.png) <br />
The /etc/passwd contains one entry per line for each user (user account) of the system. <br />

All fields are separated by a colon (:) symbol. File consists of seven fields: <br />

Username: It is used when user logs in. It should be between 1 and 32 characters in length. <br />

Password: An x character indicates that encrypted password is stored in /etc/shadow file. <br />

User ID (UID): Each user must be assigned a user ID (UID). UID 0 (zero) is reserved for root and UIDs 1-99 are reserved for other predefined accounts. Further UID 100-999 are reserved by system for administrative and system accounts/groups. <br />

Group ID (GID): The primary group ID (stored in /etc/group file) <br />

User ID Info (GECOS): The comment field. It allow you to add extra information about the users such as user’s full name, phone number etc. This field use by finger command. <br />

Home directory: The absolute path to the directory the user will be in when they log in. If this directory does not exists then users directory becomes / <br />

Command/shell: The absolute path of a command or shell (/bin/bash). Typically, this is a shell. <br />

![group](group.png) <br />
File consists of four fields: <br />
group_name: It is the name of group.  <br />
Password: Generally password is not used, hence it is empty/blank. It can store encrypted password. <br />
Group ID (GID): Each user must be assigned a group ID. You can see this number in your /etc/passwd file.  <br />
Group List: It is a list of user names of users who are members of the group. The user names, must be separated by commas.  <br /> 



2) What are the uid ranges? What is UID? How to define it? <br /> 
Distributions generally split the available UID range in two: <br /> 

1…999 → System users. These are users that do not map to actual “human” users, but are used as security identities for system daemons, to implement privilege separation and run system daemons with minimal privileges.  <br /> 

1000…65533 and 65536…4294967294 → Everything else, i.e. regular (human) users.  <br /> 

3) What is GID? How to define it? <br /> 
Groups in Linux are defined by GIDs (group IDs). Just like with UIDs, the first 100 GIDs are usually reserved for system use.  <br />
The GID of 0 corresponds to the root group and the GID of 100 usually represents the users group. GIDs are stored in the /etc/groups file. <br />
 New groups are usually assigned GIDs starting from 1000.  <br />

4) How to determine belonging of user to the specific group? <br />
Just using the groups command by itself like that shows you the groups to which the currently logged in user belongs. <br />

You can also add a username after the groups command if you’re investigating group membership for a different account.   <br />
 ![groupdefine](groupd.png) <br />
5) What are the commands for adding a user to the system? What are the basicparameters required to create a user? <br /> 

6) How do I change the name (account name) of an existing user? <br /> 
usermod -l login-name old-name = use the usermod command in Linux to rename user account. The name of the user will be changed from the old-name to login_name. Nothing else is changed. The user’s home directory name should probably be changed to reflect the new login name. <br /> 

7) What is skell_dir? What is its structure? <br />
Directory /etc/skel/ (skel is derived from the “skeleton”) is used to initiate home directory when a user is first created.
 ![skel](skel.png) <br />

8) How to remove a user from the system (including his mailbox)? <br /> 
 Use the -r (--remove) option to force userdel to remove the user’s home directory and mail spool  <br /> 
 ![del](del.png) <br />

9) What commands and keys should be used to lock and unlock a user account? <br /> 
- To lock a user with the passwd command, you can use the option -l or –lock in this manner: <br /> 
 ![lock](lock.png) <br />

- To unlock the user with passwd command, you can use the option -u or –unlock: <br />
 ![unlock](unlock.png) <br />

10) How to remove a user's password and provide him with a password-freelogin for subsequent password change? <br /> 

   - sudo passwd -d [username] - deletes a user's password (make it empty). This is a quick way to disable a password for an account. It will set the named account passwordless.  <br />
   - sudo passwd -e [username] - immediately expires an account's password. This in effect can force a user to change their password at the user's next login.  <br />



11) Display the extended format of information about the directory, tell about the information columns displayed on the terminal. <br />
The information we get from stat: <br />

File: The name of the provided file. If the provided file is a symlink, then the name will be different.  <br />
Size: The size of a given file in Bytes. <br />
Blocks: Total number of allocated blocks to the file to store on the hard disk. <br />
IO Block: The size of every allocated block in bytes. <br />
File type: The file may be of the following types: Regular files, special files, directories, or symbolic links. <br />
Device: Device number in hexadecimal format. <br />
Inode: Inode number of the file. <br />
Links: Number of hard links of the file. <br />
Access: Access permissions in the numeric and symbolic methods. <br />
Context: The field stores SELinux security context. <br />
Access: The last time at which the file was accessed. <br />
Modify: The last time at which file was modified. <br />
Change: The last time the at which file’s attribute or content was changed. <br />
Birth: The time at which the file was created. <br />
![stat](stat.png) <br />

12) What access rights exist and for whom (i. e., describe the main roles)? <br /> 
- Standart permissions for: user:group:other is "chmod 640" 
![perm](perm.png) <br />
Briefly describe the acronym for access rights. <br /> 
The command chown /ˈtʃoʊn/, an abbreviation of change owner, is used on Unix and Unix-like operating systems to change the owner of file system files, directories.  <br /> 

13) What is the sequence of defining the relationship between the file and the user? <br /> 

This information is kept in inode, you can find the inode number by using ls -i [name of the file] command. <br /> 
 You can find more information by using the command stat [path of the file or dir.] <br /> 
 ![inode](inode.png) <br />

14) What commands are used to change the owner of a file (directory), as well as the mode of access to the file? Give examples, demonstrate on the terminal. <br /> 
![ch](ch.png) <br />

15) What is an example of octal representation of access rights? Describe the umask command. <br />

0 [---] No permissions  <br />
1 [--x] Execute permission only  <br />
2 [-w-] Write permission only  <br />
3 [-wx] Write and execute permissions <br />
4 [r--] Read permission only   <br />
5 [r-x] Read and execute permissions  <br />
6 [rw-] Read and write permissions <br />
7 [rwx] Read, write, and execute permissions  <br />

- umask command is used to assign the default file permission sets for newly created folders and files.  <br />

16) Give definitions of sticky bits and mechanism of identifier substitution. Givean example of files and directories with these attributes. <br />
A Sticky bit is a permission bit that is set on a file or a directory that lets only the owner of the file/directory or the root user to delete or rename the file. No other user is given privileges to delete the file created by some other user. <br />

![sb](sb.png) <br />


17) What file attributes should be present in the command script? - Execution attribute (x).<br />
