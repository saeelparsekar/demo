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

### Managing Linux Users and Groups

### Managing Files and Directories

### Lab - Directories

### Lab - Files

### Lab - Permissions

### Lab - Linux Processes

### Conclusion

We are able to access MariaDB Database and created table "Population" inside a new database "testdb".
