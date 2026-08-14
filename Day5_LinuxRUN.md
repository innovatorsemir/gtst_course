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