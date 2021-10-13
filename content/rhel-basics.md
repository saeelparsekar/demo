---
title: Red Hat Enterprise Linux (RHEL) fundamentals.
description: Learn basic commands and fundamentals of linux operating system.
---

### Introduction

Linux is an open-source operating system modelled on UNIX. A Linux distribution is an installable operating system constructed from a Linux kernel and supporting user programs and libraries.

Red Hat Enterprise Linux is Red Hat's enterprise-ready, commercially supported Linux distribution. Red Hat Enterprise Linux is extensively tested with a large supporting ecosystem of partners, hardware and software certifications, consulting services, training, and multi-year support and maintenance guarantees.

When you develop your applications on Red Hat Enterprise Linux, it means that they are developed on the same platform on which they’ll be tested and deployed on - making it easier for development teams. As a developer, you’ll have the same stable and trusted platform, plus the extra agility to utilize the latest tools and technologies that you need for application development.

This section will provide you with a basic introduction to Linux using Red Hat Enterprise Linux 7.

### Command Line Basics

\*Listing of Files and Directories\*\*

All data in Linux is organized into files and all files are organized into directories. The filesystem has directories organized in a tree like structure.

To list the files and directories, you can use the command ‘ls’

The Usage of ls command is --> ls \[OPTION]... \[FILE]...
We can give various \[OPTIONS] to view various types of files, in different sorting orders and from multiple directories \[FILES].

The three dots ‘…’ after OPTION AND FILE specify that you can specify multiple values here.

We are currently at the Student user’s home directory. Execution of the following command will list files and directories under the current directory.

```execute
ls
```

Output of the above command will be similar to the following:

> Desktop Downloads Music Public Videos
>
> Documents Pictures Templates

If we want to list all the files present in the directories and subdirectories as well, then we need to use the recursive option ‘-R’

To get the details of all the files from a directory we need to use the -l option:

```execute
ls -l
```

On execution of the above command you should be able to see the details as below:

> drwxr-xr-x. 2 student student 4096 Mar 7 01:25 Desktop
>
> drwxr-xr-x. 2 student student 4096 Mar 7 01:25 Documents
>
> drwxr-xr-x. 2 student student 4096 Mar 7 01:25 Downloads
>
> drwxrwxr-x. 2 student student 4096 Jun 18 05:14 Music
>
> drwxr-xr-x. 2 student student 4096 Mar 7 01:25 Pictures
>
> drwxr-xr-x. 2 student student 4096 Mar 7 01:25 Public
>
> drwxr-xr-x. 2 student student 4096 Mar 7 01:25 Templates
>
> drwxr-xr-x. 2 student student 4096 Mar 7 01:25 Videos

Let us have a look in detail of the above output:

-   First Column − Represents the file type and the permission given on the file.
-   Second Column − Represents the number of memory blocks taken by the file or directory.
-   Third Column − Represents the owner of the file. This is the Unix user who created this file.
-   Fourth Column − Represents the group of the owner. Every Unix user will have an associated group.
-   Fifth Column − Represents the file size in bytes.
-   Sixth Column − Represents the date and the time when this file was created or modified for the last time.
-   Seventh Column − Represents the file or the directory name.

Until now we have seen listing of files from current directory. How can we list files from another directory from the current directory? If we know the relative path of that directory, our goal can be easily achieved.

#_The following command helps us view the contents of the usr directory present in the root (/)_

```execute
ls ../../usr
```

It prints the output similar to following:

> bin games java lib64 local share tmp
>
> etc include lib libexec sbin src

Hidden items in Linux begin with ‘.’ (dot) at the start of the file or directory. With the normal ls command these hidden files are not listed. Hence to list the same we need to use the option ‘-a’

```execute
ls -a
```

It prints the output similar to following:

> . .bashrc Documents .local Pictures Videos
>
> .. .cache Downloads ls-workspace .pki .viminfo
>
> .bash_history .config .esd_auth .m2 Public .vnc
>
> .bash_logout .dbus .gitconfig .mozilla .ssh .Xauthority
>
> .bash_profile Desktop .ICEauthority Music Templates

**Note:**To view the usage details of any command in Linux , you can type ‘commandName –-help’ in the prompt e.g.

```execute
ls --help
```

Next, we can see how to clear the console. There are two options to do the same:
Press Ctrl+L or Type ‘clear’ in the prompt, and your terminal screen should be cleared of old command outputs.

### Managing Linux Users and Groups

**Users**

Every process (running program) on the system is run by a user and every file is owned by a user. Like other operating systems, processes and files has user access permissions. The user associated with a running process determines the files and directories accessible to that process.

The execution below command lets us know who the current logged-in user is.

```execute
whoami
```

It prints the output similar to following:

> student

The id command is used to show information about the current logged-in user. Basic information about another user can also be requested by passing in the username of that user as the first argument to the id command.

On execution of the following command, you will be able to see the user id (), the primary and secondary group the user belongs to.

```execute
id
```

It prints the output similar to following:

> uid=1000(student) gid=1000(student) groups=1000(student),10(wheel),1001(docker) context=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023

**Groups**

Like users, groups are mapped using GID. To list all the groups for the currently logged in user, run the following command.

```execute
groups
```

It prints the output similar to following:

> student wheel docker

Below are different types of groups.

**Primary Group:**

-   Each user has one primary group
-   The primary group owns the new files created by the user.

**Supplementary Group:**

-   Each user can be a member of zero or more supplementary groups.
-   These group ensures users have access permissions to files and other resources of the system.

**Example:** When a user creates a file, the primary group owns and gets access to the file, while the supplementary group of the same user may not have access to it. The user can grant access to the supplementary group to access the file.

**Access as Superuser**

Providing admin privileges to the user makes him/her gain the superuser access. It is a very critical aspect in terms of security and must be provided responsibly.

Every operating system has a superuser who has unlimited powers i.e. who contains access to everything in the system. In RHEL, the user is called “root”.

Here are some of the features of a root user:

1. It can manage files and directories and override privileges on the file system.

2. It can manage and administer the system.

3. It can install/remove software packages.

4. It can control access to most devices on the system.

There are 2 ways to gain superuser access:

-   Switching the user to superuser using su command.

-   Run the command using the prefix sudo.

**Switching users using “su” command**:

There are 2 ways of switching users when using the command line:

1. `su - <username>`

    It starts a login shell where the password of the user is prompted, and access is gained only after successful authentication. After the access is gained, the environment settings changes as if a new user has logged in. To return to the previous state, press “Ctrl + D” (shortcut for logout or exit).

    Syntax for the same:
    `su – root`

2. `su <username>`
   Note the difference of “-“ from the command above is that the current environment settings are maintained.

    Syntax for the same:
    `su root`

**The “Sudo” command**:

This command allows the user to run commands as another user and requires users to enter their own password for authentication. The administrator can provide limited access to specific users without sharing root account password or shell access.

`sudo <command>`

### Managing Files and Directories

All files on a Linux system are stored on file systems which are organized into a single inverted tree of directories, known as a file system hierarchy. This tree is inverted because the root of the tree is said to be at the top of the hierarchy, and the branches of directories and subdirectories stretch below the root.

![Linux folder structure](../_images/rhel_folder_structure.png 'Linux folder structure')

The directory / is the root directory at the top of the file system hierarchy. The / character is also used as a directory separator in file names. For example, if dev is a subdirectory of the / directory, we could call that directory /dev.

Below are the commands to create, edit, copy, merge and delete directories and files from command line,

![Basic Linux commands](../_images/rhel_commands.png 'Basic Linux commands')

### Lab - Directories

**Managing Directories**

We will see how to manage the directories in Linux under this section

**Path of current directory**
To know the location of the current directory, execute the following command

```execute
pwd
```

The output of the above command will be printed as

> /home/student

**Create Directory**

The user can start the demo, with creating a RHEL_Demo directory. To create a directory, we make use of the mkdir command.
USAGE: mkdir \[OPTION]... DIRECTORY...

_#The below command will create a directory with name ‘RHEL_Demo’ in the current directory_

```execute
mkdir RHEL_Demo
```

To check if the directory is created, we can run the ls command to check if RHEL_Demo is present.

```execute
ls
```

This command will show the output similar to following:

```
spera-fasp-stream   Downloads   labs   Pictures    Templates
Desktop             go          log    Public     Videos
Documents           hf-default  Music  RHEL_Demo
```

_To open the newly created directory to Directory (RHEL_Demo), run the following command_

```execute
cd RHEL_Demo
```

_Let us create another directory under RHEL_Demo_

```execute
mkdir directory1
```

```execute
cd directory1
```

_Execute below command to print current working directory_

```execute
pwd
```

We should get the current path as below

> /home/student/RHEL_Demo/directory1

_# To go back to the RHEL_Demo directory, that is to navigate to one level up to parent directory run the following command_

```execute
cd ..
```

**Rename Directory**

_#To rename directory1, we make use of the mv command. We can use mv as follows:
USAGE: mv \[OPTION]... SOURCE... DIRECTORY.
Run the following to rename directory1 to newdirectory1_

```execute
mv directory1 newdirectory1
```

_Now, let us open the renamed directory (newdirectory1) by running the following command_

```execute
cd newdirectory1
```

_To navigate back to the user’s home (student) directory, we can execute the following command_

```execute
cd
```

_To navigate to the RHEL_Demo directory run the following command_

```execute
cd RHEL_Demo
```

**Delete Directory**

\*# We have successfully learned to create, navigate and rename a directory. Now let us see how we can delete the directory (newdirectory1). We will use the command ‘rmdir’ for the same.

USAGE: rmdir \[OPTION]... DIRECTORY...\*

```execute
rmdir newdirectory1
```

_#Let's run the ls command and see if the directory 'newdirectory1' has been deleted (It should not be listed in the output)._

```execute
ls
```

### Lab - Files

Now that we have played around with the various commands to manage directories, let's have a look at how files are managed in Linux! Let’s start with creation of a file.

**Create a File**

\*#Navigate to RHEL_Demo directory

```execute
cd && cd RHEL_Demo
```

_#To create a file we make use of the cat command. Execution of the following command will create a new file, File1, in the current directory. The file opens in the prompt and user can enter some data into it. _

```execute
cat >  File1
```

> This is file 1

_# To exit the file, Press Ctrl+D._

_#To make sure that our file, File1, is created, we can run the ls command. The file should be listed out there!!_

```execute
ls
```

**Edit and View a File**

Next, we can proceed with editing content to the file that we just created. To edit the file we require a text editor. Just like in windows we have notepad as the text editor, in Linux we have vim.

_#Run the below command and follow the steps below to edit the file._

```execute
vim File1
```

1. Type “i” for vim to go in insert mode. You can now add/modify contents.

2. To save and exit the file, Press ESC and type “:wq!” and press Enter.

3. To exit without saving, Press ESC and type “:q!” and press Enter.

This command will show the output similar to following after pressing i:

> This is edited file 1
>
> ~
>
> ~
>
> ~
>
> ~
>
> -- INSERT --

If you want to search for any value in the file, type “/”, to search for the next same value type “n”.

_#After you close the file, you can view the file using the cat command as below. cat only allows you to view the file. It does not allow you to make changes to the file._

```execute
cat File1
```

> This is edited file 1

**Copy a File**

Let us now see how to make a copy of the file. We can use the cp command to accomplish this
cp \[OPTION] Source Destination

\*#First create a directory `temp` where we will copy the file

```execute
mkdir temp
```

_#A copy of File1 will be created under /home/student/RHEL_Demo/temp directory after running the following command._

```execute
cp File1 temp/
```

_# To verify if the copy is created, let us list the files under temp directory and check if File1 has been created there._

```execute
ls temp
```

> File1

**Rename a File**

_#We can now try renaming the file by running the following command_

```execute
mv File1 Newfilename1
```

_# The file should be renamed to Newfilename1 on listing the files using the ls command_

```execute
ls
```

**Delete a File**

_#We have now gone through all the file operations and hence we can now delete the file that we have created by running the following command using rm_

```execute
rm temp/File1
```

We can List and see that File1 is not present in the temp directory any more .

```execute
ls temp/
```

### Lab - Permissions

The access to files by users is controlled by file permissions. Let us have a look at the various ownerships and access levels available.

**Owner’s Permissions**

Every file and directory on your Linux system can have 3 types of owners, as given below.

1. User permissions − The user/owner permissions determine what actions the owner of the file can perform on the file.

2. Group permissions − The group's permissions determine the actions a user, who is a member of the group, to which the file belongs to, can perform on the file.

3. Other permissions − The permissions for others indicate the actions that all other users can perform on the file.

**Access Modes**

Every file can have the following access levels.

1. **Read (r):** This permission gives you the authority to open and read a file. Read permission on a directory gives you the ability to lists its content.

2. **Write (w):** The write permission gives you the authority to modify the contents of a file. The write permission on a directory gives you the authority to add, remove and rename files stored in the directory.

3. **Execute (x):** In Linux, you cannot run a program unless the execute permission is set. If the execute permission is not set, you might still be able to see/modify the program code (provided read & write permissions are set), but not run it.

The most specific permissions apply. So, user permissions override group permissions, which override other permissions.

**Permission Indicators**

\*#Navigate to RHEL_Demo directory

```execute
cd && cd RHEL_Demo
```

_On listing the files, the first column shows the file type and the permission given on the file_

```execute
ls -l
```

This command will show the output similar to following

> -rw-rw-r--. 1 student student 22 Jun 26 06:23 Newfilename1

Let us have a closer look at -rw-rw-r--

-   \*# First Character :
    If the first character is ‘-‘, it indicates that it’s a file,
    If it’s a ‘d’ then it indicates that it’s a directory.

The Following characters specify the permission levels:
r = read permission
w = write permission
x = execute permission

-= no permission

-   The first group (next 3 characters) of the code suggests permissions granted to the owner.
-   The second part (next 3 characters) for the user group and group-members.
-   The third part (last 3 letters) is for any other user.

**Change Permissions**
The command used to change permissions from the command line is chmod. The permission instruction can be issued either symbolically (the symbolic method) or numerically (the numeric method). Let us have a look at the Symbolic method below.

**Symbolic Method:**

Usage: chmod WhoWhatWhich file|directory
Who is u, g, o, a (for user, group, other, all)

What is +, -, = (for add, remove, set exactly)

Which is r, w, x (for read, write, execute)

**Examples:**

**1) Remove read and write permission for group and other on file1:**

If we check the permissions on file --> File1, by executing the below command, we see that it has -rw-rw-r—access. So the group has Read and write access, while the other user has read access. If we want to restrict the access to group and other user, we can execute the below command.

```execute
chmod go-rw Newfilename1
```

After execution of the above command the Permissions on the File1 is -rw-------. Which means that the group and other user cannot read, write or execute it.

```execute
ls -l
```

The output of the above command will be as follows:

> -rw-------. 1 student student 22 Jun 26 06:23 Newfilename1

**2) To Add execute permission for everyone on file1**
Let us run the below command and see the file permission change.

```execute
chmod a+x Newfilename1
```

```execute
ls -l
```

The output of the above command will be as follows:

> -rwx--x--x. 1 student student 22 Jun 26 06:23 Newfilename1

**Changing File/Directory User or Group Ownership**

File ownership can be changed with the chown command (change owner).

Usage: chown \[OPTION]... \[OWNER]\[:\[GROUP]] FILE...

Examples:

1. Command to Grant ownership of foofile to user student
   `chown student foofile`

2. chown can be used with the -R option to recursively change the ownership of an entire directory tree.
   `chown -R student foodir`

3. To change group ownership of a file we need to precede the group name with a colon (:). For example, the following command will change the group foodir to admins:
   `chown : admins foodir`

Only root can change the ownership of a file. Group ownership, however, can be set by root or the file's owner. root can grant ownership to any group, while non-root users can grant ownership only to groups they belong to. Please note that: chgrp command can also be used instead of chown.

### Summary

This course provided a refresher on the basics of RHEL and Git, including:

1. How to log in to the system and execute simple commands using the shell

2. How to manage directories, files and permissions

3. How to manage processes

![rhel_summary](../_images/rhel_summary.PNG 'rhel_summary')
