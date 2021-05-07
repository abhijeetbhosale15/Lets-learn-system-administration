# Lets-learn-system-administration
##### This tutorial contains collapsible section to access particular topic, hover over the topic and click on it to deep dive into it.  

 ## Topics covered:
<details>
  <summary><h3>Linux file system</h3></summary>
  
  #### In Linux, all the files or directories are part of a single root directory. The main file in the linux is referred as the *root (/)* file.  
  
  ![Linux file System](https://computingforgeeks.com/wp-content/uploads/2020/02/linux-file-system-hierarchy-1-1024x339.png?ezimgfmt=ng:webp/ngcb18)
  
  #### Now let's see it one by one,  
  Directory type  | Types of files stored
------------- | -------------
Binary directories  | Contains binary or compiled source code files, eg, /bin, /sbin, etc.
Configuration directories  | 	Contains configuration files of the system, eg, /etc, /boot.
Data directories  | 	Stores data files, eg, /home, /root, etc.
Memory directories  | 	Stores device files which doesn't take up actual hard disk space, eg, /dev, /proc, /sys.
Usr (Unix System Resources)  | 	Contains sharable, read only data, eg, /usr/bin, /usr/lib, etc.
var (variable directory)  | 	Contains larger size data, eg, /var/log, /var/cache, etc.
Non-standard directories  |	Directories which do not come under standard FHS, eg, lost+found, /run, etc.

#### Now you know the file structure of the linux, now let's see the basic commands that are used in linux to perform basic operations

Command  |  Description  |  Example
------------- | ------------- | -------------
pwd   | 	Returns current working directory  |  *pwd*
ls    |	List the contents of a particular path  |  *ls*
mkdir  | 	Make a directory at a current directory  |  *mkdir folder*
touch *file-name*  |  to create file  |  *touch abc.txt*
vi *filename*  |  Text editor ,press i to insert then press ESC to return & wq to save and exit  |  *vi abc.txt*
cat *filename*  |  To display content of the given file  |  *cat abc.txt*
rmdir *empty-folder*  |  used to remove an empty directory  |  *rmdir folder* 
cd    |	 Move to a particular path or change directory  |  *cd Desktop, cd ~, cd /*
~     |  Indicates the home directory  |  *~*
cp *src* *dest* |  To copy all files recursively  |  *cp abc.txt xyz.txt*
mv    |  To move one or more files or directories from one place to anothe   |  *mv abc.txt xyz.txt*
rm    |  To remove file   |  *rm xyz.txt*
uname |  To check current version of Linux  |  *uname*
df    |  It is used to display disk space used in the filesystem  | *df*
man *command* |  This command used to display description of the command specified | *man touch*
head *filename*  |  To get info about first part from mentioned file  |  *head abc.txt*
tail *filename* |  To get info about last part from mentioned file   |  *tail abc.txt*
ping *ip/url* |   to check whether a network is available  |  *ping google.com*
clear |  Clears all text from terminal window  |  *clear*

- - - -
#### Hard links and soft links  
To know what are they plz [click here](https://www.geeksforgeeks.org/soft-hard-links-unixlinux/)  

Now let's do one exercise to understand what we have learnt so far  
> Example:  
> * Create an empty directory called `test`.
> * Change to the `test` directory.
> * Create a new file named ‘source.txt’ and add content to the file - `Hello World`.
> * View the contents of the file.
> * Create a hard link to the file named `hardlink.txt` and compare the inode with the file `softlink.txt`.
> * Now create a softlink of the the file named `softlink.txt` and compare the inode with file `source.txt`

Try this out by your own :smile: and after completing please verify from below :point_down: <details>
 <summary><b>Answer</b></summary>
 
![commands](https://user-images.githubusercontent.com/43695392/117485099-9d547080-af85-11eb-8e35-1b491d6d1d88.JPG)

 
</details>


</details>

<details>
  <summary><h3>Users & Groups</h3></summary>
 
 #### Linux is a multi-user system, which means that more than one person can interact with the same system at the same time. As a system administrator, you have the responsibility to manage the system’s users and groups by creating and removing users and assign them to different groups. 
 
 #### To understand **Users and Groups** in linux first we need to understand the columns of `/etc/passwd` file 
 
 ![Users and groups](https://devconnected.com/wp-content/uploads/2019/09/list-users-linux-768x415.png)
 
 #### Now we will understand each columns of `/etc/passwd` one by one.
 
 Column name                   |  Description
-------------                  |  -------------
User name                      |  It is used when user logs in.
Encrypted password             |  An x character indicates that encrypted password is stored in /etc/shadow file.
User ID number (UID)           |  Each user must be assigned a user ID 
User's group ID number (GID)   |  The primary group ID (stored in /etc/group file)
User home directory            |  The absolute path to the directory the user will be in when they log in.
Login shell                    |  The absolute path of a command or shell (/bin/bash)

- - - -

#### Users
- Users are accounts ,used to login into a system. 
- Each user identified with unique identification number.
- The information of users in a system are stored in /etc/passwd file. 
- The hashed passwords for users are stored in /etc/shadow file.

#### Groups
- A group is a collection of users. 
- To define a set of privileges like read, write, or execute permission for a given resource that can be shared among the users within the group.

1. Primary Group( default group)
   1. You can find a user’s primary group ID by viewing the contents of the your system’s `/etc/passwd` file.  
   > cat  /etc/passwd
   2. You can also find a user’s primary group information by using the id command.  
   > id username

2. Secondary Group-
   1. Once the user is created with the primary group it can be added to the other groups.  >groups username
   2. Linux system users can have a maximum of 15 secondary groups.  
   3. A Linux system’s groups are stored in the /etc/group file.
   4. A user can belong to zero or more secondary groups.

 Command                      |   Use                                       |  Example
-------------                 |  -------------                              | -------------
whoami                        |  To display the username of the current use.  | *-*
su *username*                 |  To substitute user without changing the cwd  | *su Abhijeet*
useradd *username*            | To add a user to the system. | *useradd Abhijeet*
userdel *username*            | To delete a user account and related files.  | *userdel Abhijeet*
groupadd *groupname*          | To add a group to the system.| *groupadd cse*
delgroup/groupdel *groupname* | To remove a group from the system.  | *delgroup cse*
usermod *username* | To modify or change any attributes of a already created user account via command line  | *usermod Abhijeet*
usermod -a -G *grpname* *username* |  To append user to the secondary group.  | *usermod -a -G cse Abhijeet*
cat /etc/passwd | To check addition of the user | *cat /etc/passwd*
passwd  |  To assign the password to user  | *-*
id  |  To get data about user and its group   | *-*
chage  |   To change user password expiry information.  | *chage -l Abhijeet*
sudo  |  To run one or more commands as another user typically with superuser permissions.  | *-*

</details>

<details>
  <summary>Accessing Files</summary>
  
  ## Heading
  1. A numbered
  2. list
     * With some
     * Sub bullets
</details>

<details>
  <summary>SELinux Security</summary>
  
  ## Heading
  1. A numbered
  2. list
     * With some
     * Sub bullets
</details>
