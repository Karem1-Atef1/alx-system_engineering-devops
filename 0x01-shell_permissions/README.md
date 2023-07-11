Permissions
The Unix-like operating systems, such as Linux differ from other computing systems in that they are not only multitasking but also multi-user.

What exactly does this mean? It means that more than one user can be operating the computer at the same time. While a desktop or laptop computer only has one keyboard and monitor, it can still be used by more than one user. For example, if the computer is attached to a network, or the Internet, remote users can log in via ssh (secure shell) and operate the computer. In fact, remote users can execute graphical applications and have the output displayed on a remote computer. The X Window system supports this.

The multi-user capability of Unix-like systems is a feature that is deeply ingrained into the design of the operating system. If we remember the environment in which Unix was created, this makes perfect sense. Years ago before computers were "personal," they were large, expensive, and centralized. A typical university computer system consisted of a large mainframe computer located in some building on campus and terminals were located throughout the campus, each connected to the large central computer. The computer would support many users at the same time.

In order to make this practical, a method had to be devised to protect the users from each other. After all, we wouldn't want the actions of one user to crash the computer, nor would we allow one user to interfere with the files belonging to another user.

This lesson will cover the following commands:

chmod - modify file access rights
su - temporarily become the superuser
sudo - temporarily become the superuser
chown - change file ownership
chgrp - change a file's group ownership
File Permissions
On a Linux system, each file and directory is assigned access rights for the owner of the file, the members of a group of related users, and everybody else. Rights can be assigned to read a file, to write a file, and to execute a file (i.e., run the file as a program).

To see the permission settings for a file, we can use the ls command. As an example, we will look at the bash program which is located in the /bin directory:

[me@linuxbox me]$ ls -l /bin/bash
-rwxr-xr-x 1 root root 1113504 Jun  6  2019 /bin/bash
Here we can see:

The file "/bin/bash" is owned by user "root"
The superuser has the right to read, write, and execute this file
The file is owned by the group "root"
Members of the group "root" can also read and execute this file
Everybody else can read and execute this file
In the diagram below, we see how the first portion of the listing is interpreted. It consists of a character indicating the file type, followed by three sets of three characters that convey the reading, writing and execution permission for the owner, group, and everybody else.
