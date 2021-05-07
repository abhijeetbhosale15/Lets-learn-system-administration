# Lets-learn-system-administration
In this repo you will find all basics of linux. This tutorial contains collapsible section to access particular topic. Please click on bullet infrot of the topic to deep dive into it.  

 ## Topic covered
<details>
  <summary><h3>Linux file system</h3></summary>
  
  In Linux, all the files or directories are part of a single root directory. The main file in the linux is referred as the *root (/)* file.  
  
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
mkdir  | 	Make a directory at a particular path
rmdir  |  used to remove an empty directory  
touch *file-name*  |  to create file
~     |  Indicates the home directory.
echo  |  It inserts text in the given file
clear |  Clears information on the display screen to provide a blank slate.
pwd   | 	Print your working directory
ls    |	List the contents of a particular path
cd    |	 Move to a particular path or change directory
cd ~  |  Return to home directory.
cd /  |  To shift to root user 
ls -l |  shows all the links with the link column shows number of links.
cat   |  To display content of the given file
cp -r |  To copy all files recursively.
mv    |  To rename the file 
rm    |  To remove file
uname |  To check current version of Linux.
head  |  To get info about top files instead of all files.
tail  |  To get info about last files instead of all files.
ping  |  To check  working of network
vi    |  Text editor ,press i to insert then press ESC to return & wq to save and exit .
</details>

<details>
  <summary>Users & Groups</summary>
  
  ## Heading
  1. A numbered
  2. list
     * With some
     * Sub bullets
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
