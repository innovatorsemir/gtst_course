# Advanced User Management

## Some Advanced User Commands

### Change the Password of a User

```bash
sudo passwd username
```

### Change User ID and Group ID

#### Change User ID (UID)

```bash
sudo usermod -u new_id username
```

#### Change Group ID (GID)

```bash
sudo groupmod -g new_id groupname
```

### Delete a User

```bash
sudo userdel -r username
```

### Change Users on the Terminal

```bash
su - username
```

### Create a Home Directory for a User

```bash
sudo mkhomedir_helper your_username
```

- This is used to create a home directory for a specified user in Linux, typically when the user is being added to the system without an existing home directory.

### Change the Default Login Shell

```bash
sudo usermod your_username -s /bin/shell
```

- This changes the default login shell for the specified user.
- Examples:
  - `/bin/bash`
  - `/bin/zsh`

---

# Advanced Group Commands

### Create a New Group

If the group is not already created:

```bash
sudo groupadd groupname
```

### Add Users to the Group

```bash
sudo usermod -aG groupname username
```

### Verify the User's Group Membership

```bash
groups username
```

### Remove User from the Group

```bash
sudo gpasswd -d username groupname
```

### Verify the User's Group Membership

```bash
groups username
```

---

# Sudoers File

- The **sudoers file** is a file Linux and Unix administrators use to allocate system rights to system users.
- The user you created doesn't have power to use **sudo** as the original user.
- This is because the user is not added to the **sudoers file**.

## Accessing the Sudoers File

```bash
sudo visudo
```

Example:

```text
(geeztech@HunterMachine)-[~]
$ sudo visudo
[sudo] password for geeztech:
geeztech is not in the sudoers file. This incident will be reported.
```

---

## The First Appearance of the Sudoers File

When you first open the sudoers file, you may see:

```text
# This file MUST be edited with the 'visudo' command as root.
#
# Please consider adding local content in /etc/sudoers.d/ instead of
# directly modifying this file.
#
# See the man page for details on how to write a sudoers file.

Defaults        env_reset
Defaults        mail_badpass
Defaults        secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

# Host alias specification

# User alias specification

# Cmnd alias specification

# User privilege specification
root    ALL=(ALL:ALL) ALL

# Allow members of group sudo to execute any command
%sudo   ALL=(ALL:ALL) ALL

# See sudoers(5) for more information on "@include" directives:

@includedir /etc/sudoers.d
```

### Important

The sudoers file should be edited using:

```bash
sudo visudo
```

rather than directly modifying the file.

---

## Adding a User to the Sudoers File

You can add the user you need to the sudoers file so they can use the `sudo` command.

Example:

```text
username ALL=(ALL:ALL) ALL
```

After the user has the required permission, they can use:

```bash
sudo command
```

---

## Linux File Permission

- Every file on Linux has its own ownership and permissions.
- We can see file information using the command:

```bash
ls -l
```

- There are 5 main parts in the listing:
  - Permission
  - Owners
  - Date
  - Size
  - Filename

### Ownership

- Ownership is the owner of a file.
- There are 2 kinds of ownership:
  - User
  - Group

- To change the owner of a file, you can use the command:

```bash
chown user:group filename
```

- Example:

```bash
chown root:semir awk.txt
```

Example:

```text
USER       GROUP
rexder     rexder
```

```bash
(rexder@HunterMachine)-[~]
$ sudo chown root Day4.md

(rexder@HunterMachine)-[~]
$ ls -l
```

### Permission

- There are 3 types of permissions:
  - Read (`r`)
  - Write (`w`)
  - Execute (`x`)

- Files and folders are different based on the first character of the permission.

```text
-rw-r--r--
drwxr-xr-x
```

- If it starts with `-`, it is a file.
- If it starts with `d`, it is a directory.

Example:

```text
-rw-r--r-- 1 rexder rexder ...
drwxr-xr-x 2 rexder rexder ...
```

### Permission Categories

There are three main permission categories:

- **User (`u`)**
  - The permissions of the user defined as the owner.

- **Group (`g`)**
  - The permissions of the group defined in the ownership.

- **Other (`o`)**
  - The permissions of other users.

- **All (`a`)**
  - Represents all users, groups, and others.

The permission structure is:

```text
user - group - other
```

Example:

```text
drwxr-xr-x
```

## Changing File Permissions

The command used to change file permissions is:

```bash
chmod option filename
```

Example:

```bash
(rexder@HunterMachine)-[~]
$ ls -l day4

-rw-r--r-- 1 rexder rexder 0 Dec 19 12:19 day4
```

Add execute permission:

```bash
(rexder@HunterMachine)-[~]
$ chmod +x day4
```

Check the permission again:

```bash
(rexder@HunterMachine)-[~]
$ ls -l day4

-rwxr-xr-x 1 rexder rexder 0 Dec 19 12:19 day4
```

## CHMOD Command

- The `chmod` command helps to change file permissions.
- File permissions include:
  - Read
  - Write
  - Execute

- Each permission has a number representation:

```text
Read    = 4
Write   = 2
Execute = 1
```

- The parameters can be represented using:
  - Symbols
  - Numbers

```text
+  = Giving/adding permission
-  = Taking/removing permission
```

### A) Parameters Using Symbols

- Add execute permission for all:

```bash
chmod a+x filename
```

or:

```bash
chmod +x filename
```

- Add execute permission for user:

```bash
chmod u+x filename
```

- Add execute permission for group:

```bash
chmod g+x filename
```

- Add execute permission for other:

```bash
chmod o+x filename
```

- Remove execute permission:

```bash
chmod -x filename
```

- Example of multiple permissions:

```bash
chmod a+rwx,u-rw,g-x,o-xw filename
```

### B) Parameters Using Numbers

Example:

```bash
chmod 621 filename
```

- `6` for user = `4 + 2` = `rw`
- `2` for group = `w`
- `1` for other = `x`

Another example:

```bash
chmod 777 filename
```

```text
7 = 4 + 2 + 1 = rwx
```

Therefore:

```text
User  = rwx
Group = rwx
Other = rwx
```

## Special File Permissions

- There are another 3 special permissions that you may encounter on your pentesting journey.

They are:

- **SUID bit (`s`)** — Set User ID
- **SGID bit (`s`)** — Set Group ID
- **Sticky bit (`t`)**

Numeric representation:

```text
SUID   = 4000
SGID   = 2000
Sticky = 1000
```

- These permissions are related to executable files and programs.
- They can allow a program to run with the privileges associated with the file owner or group.

### SUID Example

If a user adds an SUID bit to a program, another user can execute the program with the permission of the file owner.

For example:

- If `root` owns a program.
- If `root` sets the SUID bit on that program.
- Other users can execute the program with the file owner's privileges.

Set the SUID permission:

```bash
chmod +s myprogram
```

Example permission:

```text
-rwsr-sr-x
```

### SUID Example Program

This is a computer program written in C.

The program tries to open:

```text
/etc/shadow
```

If the permission is correct, it responds:

```text
Successfully opened /etc/shadow file!
```

Otherwise:

```text
Unable to open /etc/shadow
```

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *fp = fopen("/etc/shadow", "r");

    if (fp == NULL) {
        perror("Unable to open /etc/shadow");
        return EXIT_FAILURE;
    }

    printf("Successfully opened /etc/shadow file!\n");
    fclose(fp);

    return EXIT_SUCCESS;
}
```

Check the program:

```bash
~/GTSTv1 > $ ls -la readergtst

-rwxrwxr-x 1 rexder rexder 16112 Nov 8 11:44 readergtst
```

Run the program:

```bash
~/GTSTv1 > $ ./readergtst

Unable to open /etc/shadow: Permission denied
```

### Why?

The normal user does not have permission to read:

```text
/etc/shadow
```

### Changing the Owner

Change the owner of the binary/program to `root`:

```bash
~/GTSTv1 > $ sudo chown root:root readergtst
```

Check the file:

```bash
~/GTSTv1 > $ ls -la readergtst

-rwxrwxr-x 1 root root 16112 Nov 8 11:44 readergtst
```

Run the program again:

```bash
~/GTSTv1 > $ ./readergtst

Unable to open /etc/shadow: Permission denied
```

- After changing the owner of the binary/program, it still does not run with root permission.

### Setting the SUID Bit

Set the SUID bit:

```bash
~/GTSTv1 > $ sudo chmod u+s readergtst
```

Check the permission:

```bash
~/GTSTv1 > $ ls -la readergtst

-rwsrwxr-x 1 root root 16112 Nov 8 11:44 readergtst
```

Run the program:

```bash
~/GTSTv1 > $ ./readergtst

Successfully opened /etc/shadow file!
```

- Here comes the interesting part.
- The owner of the file is `root`.
- If the root user sets an SUID bit on the program, the program can run with the file owner's privilege and permission.

---

## Package Installation on Linux

- On Linux, to install software, you use **package managers**.

Examples:

- `apt`
- `pacman`
- `pkg`

- We will use the Debian package manager.
- On Debian, the package manager is called **APT**.
- There is also another package manager called `dpkg`.

Package managers are:

> Free-software user interfaces that work with an online server to handle the installation and removal of software on Debian and Debian-based Linux distributions.

### Package Management Structure

```text
LINUX SYSTEM <----- PACKAGE MANAGER -----> REPOSITORY
      |
      |
PACKAGE METADATA       PACKAGES -----> PACKAGE DEPENDENCIES
```

## The Repository

- A repository is the site/server used to store and provide packages.
- Kali Linux uses repositories to upload and download packages.

Example:

```text
Apache 2.4.10 (Debian) Server at http.kali.org
```

## Advanced Package Tool — APT

- APT is a free-software user interface that works with an online server to handle the installation and removal of software on Debian and Debian-based Linux distributions.
- It can be used for package management.
- The older command commonly used is:

```bash
apt-get
```

### Common APT Commands

Update package information:

```bash
sudo apt update
```

Search for software:

```bash
sudo apt search softwarename
```

Install software:

```bash
sudo apt install softwarename
```

Remove software:

```bash
sudo apt remove softwarename
```

Upgrade packages:

```bash
sudo apt upgrade
```

Remove software and its configuration files:

```bash
sudo apt purge softwarename
```

You can also view the manual page:

```bash
man apt
```

### APT Package Dependencies

- A software program can be built based on another program or module.
- For a program to work properly, its dependencies may need to be installed.
- Package managers install the software together with its required dependencies.

Example:

```bash
sudo apt-get install coffee
```

Example illustration:

```text
santi $> apt-get install wife

The following dependencies will be installed:

wife-house
wife-car
wife-friends
wife-dog
wife-mother_in_law
wife-no_more_TV_sports
wife-kid
wife-kidlibs
wife-bricomanialibs

The following packages will be upgraded:

ego-restrainer
freedom-throttler

Estimated installation time: 47 years

Do you want to continue? (Y/n)
```

---

## Common Linux Repository Errors

### 1. Could not get lock

Example:

```text
Could not get lock /var/lib/apt/lists/lock
```

- This occurs when you run two different APT processes or another APT process is running in the background.
- You can solve it by waiting for the other process to finish, closing the other APT process, or restarting the system if necessary.

Example:

```bash
~/GTSTv1 > $ sudo apt install evolution

[sudo] password for rexder:

Waiting for cache lock:
Could not get lock /var/lib/dpkg/lock-frontend.
It is held by process 799328 (apt)
```

### 2. Could not open lock

Example:

```text
Could not open lock /var/lib/dpkg/lock-frontend
```

- This occurs when you forget to run APT with the root user or `sudo`.

Example:

```bash
~/GTSTv1 > $ apt install evolution

Error: Could not open lock file /var/lib/dpkg/lock-frontend - open (13: Permission denied)

Error: Unable to acquire the dpkg frontend lock
(/var/lib/dpkg/lock-frontend), are you root?
```

Use:

```bash
sudo apt install evolution
```

### 3. Unable to Locate Package

Example:

```bash
~/GTSTv1 > $ sudo apt install dex2jr

Error: Unable to locate package dex2jr
```

- This can occur when you misspell the program name.

Correct example:

```bash
~/GTSTv1 > $ sudo apt install dex2jar

dex2jar is already the newest version.
```

### 4. Repository Does Not Have a Release File

Example:

```text
The repository 'http://http.kali.org/kali kali-rolling Release'
does not have a Release file.
```

- This occurs when there is a problem with the repository configuration.
- Sometimes the repository link might be broken.

The repository configuration can be found in:

```text
/etc/apt/sources.list
```

Example:

```text
deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware
```

- You need to use the correct repository link for your Linux distribution.
- Repository links may differ depending on the Linux distribution.

### More Notes About APT

- Do not close APT while installation is running.
- If repository errors happen, you can check or edit the package sources using:

```bash
sudo apt edit-sources
```

---

## DPKG — Debian Package Manager

- `dpkg` is an offline package management program.
- Packages on Debian commonly have the extension:

```text
.deb
```

### DPKG Syntax

Install a package:

```bash
sudo dpkg -i packagename
```

Remove a package:

```bash
sudo dpkg -r packagename
```

Purge a package:

```bash
sudo dpkg -P packagename
```

---

## Flatpak

- Flatpak is a universal software packaging and distribution system for Linux desktop applications.
- It aims to simplify the process of developing, distributing, and installing applications across different Linux distributions.

### How to Use Flatpak

#### Install Flatpak

```bash
sudo apt install flatpak
```

#### Install an Application

```bash
flatpak install flathub com.spotify.Client
```

#### Run an Application

```bash
flatpak run com.spotify.Client
```

#### Search for Applications

```bash
flatpak search spotify
```

#### Uninstall an Application

```bash
flatpak uninstall com.spotify.Client
```

#### Update All Flatpak Applications

```bash
flatpak update
```

#### List Installed Flatpak Applications

```bash
flatpak list
```

#### Check the Flatpak Version

```bash
flatpak --version
```

# Summary

## User Management Commands

| Command | Purpose |
|---|---|
| `sudo passwd username` | Change a user's password |
| `sudo usermod -u new_id username` | Change a user's UID |
| `sudo groupmod -g new_id groupname` | Change a group's GID |
| `sudo userdel -r username` | Delete a user |
| `su - username` | Switch to another user |
| `sudo mkhomedir_helper username` | Create a user's home directory |
| `sudo usermod username -s /bin/bash` | Change the user's login shell |

## Group Management Commands

| Command | Purpose |
|---|---|
| `sudo groupadd groupname` | Create a new group |
| `sudo usermod -aG groupname username` | Add a user to a group |
| `groups username` | Check a user's group membership |
| `sudo gpasswd -d username groupname` | Remove a user from a group |

## Sudo Commands

| Command | Purpose |
|---|---|
| `sudo visudo` | Edit the sudoers configuration |
| `sudo command` | Execute a command with elevated privileges |

---

@innovatorsemir