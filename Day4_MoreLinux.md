# Further on Linux

## Topics

- Linux File Hierarchy
- VIM
- NANO
- Linux User Management

---

## Linux File Hierarchy

- LINUX/UNIX have a special file system than windows.
- File system is a directory structure that the OS uses.

#### System Files

- System Files are files used by the sys software (OS).
- **Windows:** System files appear under the *local disk C:*
- **Linux:** System files appear under the *root directory (/)*

You can check it in the terminal and also in the file manager.

#### File structure in detail

### 1) `/` — Root

- Every single file and directory starts from the root directory.
- The only root user has the right to write under this directory.
- `/root` is the root user's home directory, which is not the same as `/`.

---

### 2) `/bin` — Binary Executables

- Essential command binaries that need to be available in single-user mode; for all users.
- Examples:

```text
cat
ls
cp
pwd
```

---

### 3) `/boot` — Boot Loader Files

- Kernel, initrd, vmlinux, and grub files are located under `/boot`.

Examples:

```text
initrd.img-2.6.32-24-generic
vmlinuz-2.6.32-24-generic
```

---

### 4) `/dev` — Essential Device Files

- These include terminal devices, USB, or any device attached to the system.

Examples:

```text
/dev/tty1
/dev/usbmon0
```

---

### 5) `/etc` — Et Cetera

- Contains configuration files required by all programs.
- This also contains startup and shutdown shell scripts used to start/stop individual programs.

Examples:

```text
/etc/resolv.conf
/etc/hosts
/etc/passwd
```

---

### 6) `/home` — Home Directory

- Home directories for all users to store their personal files.

Examples:

```text
/home/semir
/home/rexder
```

- Here, you can't access files of other users.

Example:

If your home is:

```text
/home/semir
```

You can't access:

```text
/home/rexder
```

- Your home directory `/home/semir` will be denoted by:

```text
~
```

---

### 7) `/lib` — Libraries Essential for the Binaries in `/bin` & `/sbin`

- Library filenames are either `ld*` or `lib*.so.*`.

Examples:

```text
ld-2.11.1.so
libncurses.so.5.7
```

---

### 8) `/media` — Mount Points for Removable Media

- Temporary mount directory for removable devices.
- Used for removable media such as CD-ROMs.

Examples:

```text
/media/cdrom
/media/floppy
/media/cd recorder
```

- `/media/cdrom` for CD-ROM
- `/media/floppy` for floppy drives
- `/media/cd recorder` for CD writer

---

### 9) `/mnt` — Temporarily Mounted File

- Temporary mount directory where system administrators can mount filesystems.

---

### 10) `/opt` — Optional Application Software Packages

- Contains add-on applications from individual vendors.
- Add-on applications should be installed under either `/opt/` or an `/opt/` sub-directory.

---

### 11) `/sbin` — Essential System Binaries

- Just like `/bin`, `/sbin` also contains binary executables.
- The Linux commands located under this directory are used typically by system administrators for system maintenance purposes.

---

### 12) `/tmp` — Temporary Files

- Directory that contains temporary files created by system and users.
- Files under this directory are **deleted** when the system is rebooted.

---

### 13) `/usr` — User Utilities

- Contains binaries, libraries, documentation, and source-code for second-level programs.

#### `/usr/bin`

- Contains binary files for user programs.
- If you can't find a user binary under `/bin`, look under `/usr/bin`.

Examples:

```text
at
awk
cc
less
scp
```

#### `/usr/sbin`

- Contains binary files for system administrators.
- If you can't find a system binary under `/sbin`, look under `/usr/sbin`.

Examples:

```text
atd
cron
sshd
useradd
userdel
```

#### `/usr/lib`

- Contains libraries for:

```text
/usr/bin
/usr/sbin
```

#### `/usr/src`

- Holds:
  - Linux kernel sources
  - Header files
  - Documentation

---

# Text Editors

- Programs that are used for text processing.

## Linux Command-Line Text Editors

- VIM
- Nano
- Emacs
- Neovim
- ...

## Linux Graphical Text Editors

- Sublime
- VS Code
- Gedit
- Pluma
- ...

---

# VIM

## History of VIM

- Before `vi`, the primary editor used on Unix was the **line editor**.
  - The user was able to see/edit only one line of the text at a time.
- Then the `vi` editor improved and developed into VIM.
- VIM means **VI iMproved**.

## What is VIM?

The VIM editor is:

- Very powerful
- But at the same time it is cryptic
- It is hard to learn, especially for Windows users

## VIM Modes

It mainly has:

- Command Mode
- Input Mode
- Visual Mode
- Normal Mode

---

## VIM Information

```text
VIM - Vi IMproved

version 8.2.2434
by Bram Moolenaar et al.
Modified by team+vim@tracker.debian.org
Vim is open source and freely distributable

    Help poor children in Uganda!
type :help iccf<Enter>   for information
type :q<Enter>           to exit
type :help<Enter> or <F1> for on-line help
type :help version8<Enter> for version info
```

---

# Opening VIM

## Syntax

```bash
vim yourfilename
```

Example:

```bash
vim Day3_MoreLinux.md
```

VIM is by default in **Normal Mode** when you open it.

To get into **Insert Mode**, you have to type:

```text
i
```

---

# Insert Mode

Press:

```text
i
```

Here you can:

- Type anything you want
- Edit your text

---

# Command Mode

To get back to Command Mode, press:

```text
Esc
```

Inside Command Mode you can:

- Save
- Save & quit
- Force Quit & Save
- Undo
- Execute bash commands

---

## Save

Type:

```vim
:w
```

Then press:

```text
Enter
```

---

## Quit

Type:

```vim
:q
```

Then press:

```text
Enter
```

---

## Force Quit & Save

Type:

```vim
:wq!
```

Then press:

```text
Enter
```

`!` means **Force**.

---

## Undo

Type:

```vim
:undo
```

Then press:

```text
Enter
```

Or:

```vim
:u
```

---

## Execute Commands

Type:

```vim
:%!yourcommand
```

> There is no space between `%!` and `yourcommand`.

---

# Visual Mode

Visual Mode in VIM allows users to select and manipulate blocks of text.

## Types of Visual Mode

### Character-wise Visual Mode

- Selects text character by character.
- Press:

```text
v
```

### Line-wise Visual Mode

- Selects entire lines of text.
- Press:

```text
Shift + V
```

### Block-wise Visual Mode

- Selects rectangular blocks of text.
- Press:

```text
Ctrl + V
```

or:

```text
Ctrl + Q
```

---

# Commands in Visual Mode

Once you select the text in Visual Mode, common commands include:

### Delete

```text
d
```

- Deletes the selected text.

### Yank

```text
y
```

- Yank/copy the selected text.

### Paste

```text
p
```

- Paste the yanked text after the cursor.

---

# NANO

## What is GNU Nano?

The GNU Nano text editor is:

- A user-friendly text editor
- Free and open-source
- Usually comes pre-installed in modern Linux systems

---

# Starting Nano

## Syntax

```bash
nano filename
```

Then start typing.

---

# Nano Hotkeys

| Shortcut | Function |
|---|---|
| `Ctrl + S` | Save |
| `Alt + U` | Undo |
| `Alt + E` | Redo |
| `Ctrl + X` | Exit |
| `Ctrl + T` | Command Execute |
| `Alt + 6` | Copy |
| `Ctrl + K` | Cut |
| `Ctrl + U` | Paste |
| `Shift + Arrow` | Select |
| `Ctrl + R` | Read/append text from another file |

> In Nano, the `^` symbol is equal to `Ctrl`.

---

# Copy, Paste & Reading Files in Nano

## Copy

```text
Alt + 6
```

## Cut

```text
Ctrl + K
```

## Paste

```text
Ctrl + U
```

## Select

```text
Shift + Arrow
```

## Append Text from Another File

You can append texts from other files with:

```text
Ctrl + R
```

Then specify the path.

---

# Linux User Management

## What is a User?

- On a computer system, a person who uses the computer is called a **user**.
- Every user has a group.
- Users have their own files and applications.
- Users have power/privileges.

---

# Finding the Current User

To know our name on Linux:

```bash
whoami
```

---

# Linux Users and Privileges

On Linux there are two kinds of users.

## Root User

```text
Root ID = 0
```

The root user has the power to do everything on Linux.

## Normal User

Normal User IDs start with:

```text
1-999
```

---

# `sudo`

If users want to have root access, they add `sudo` in front of the command.

## Syntax

```bash
sudo YourCommand
```

### What is SUDO?

**SUDO = Superuser Do**

It is used to pass permission denied restrictions.

---

# Creating Users

On Linux, to create users you can use the following commands:

- `useradd` → Simple
- `adduser` → Detailed

---

## `useradd`

### Syntax

```bash
sudo useradd username
```

---

## `adduser`

### Syntax

```bash
sudo adduser username
```

---

# Linux User Files

The user files are stored inside:

```text
/etc/passwd
```

The user passwords are stored inside:

```text
/etc/shadow
```

When you create a user, it creates a group with that name.

---

# Checking `/etc/passwd`

User account information can be checked in:

```text
/etc/passwd
```

---

# Accessing the Root User

To access the root user:

```bash
sudo su
```

---

# Linux File Hierarchy Quick Reference

| Directory | Purpose |
|---|---|
| `/` | Root directory; every file and directory starts here |
| `/bin` | Essential command binary executables |
| `/boot` | Kernel, initrd, vmlinux and GRUB files |
| `/dev` | Device files such as terminal and USB devices |
| `/etc` | Configuration files and startup/shutdown scripts |
| `/home` | Home directories for users |
| `/lib` | Libraries essential for `/bin` and `/sbin` |
| `/media` | Mount points for removable media |
| `/mnt` | Temporary mount directory |
| `/opt` | Optional/add-on application software |
| `/sbin` | Essential system binaries |
| `/tmp` | Temporary files |
| `/usr` | User utilities, binaries, libraries, documentation and source code |
| `/usr/bin` | Binary files for user programs |
| `/usr/sbin` | Binary files for system administrators |
| `/usr/lib` | Libraries for `/usr/bin` and `/usr/sbin` |
| `/usr/src` | Linux kernel sources, header files and documentation |

---

# VIM Quick Reference

| Command / Key | Function |
|---|---|
| `vim filename` | Open a file in VIM |
| `i` | Enter Insert Mode |
| `Esc` | Return to Command/Normal Mode |
| `:w` | Save |
| `:q` | Quit |
| `:wq!` | Force save and quit |
| `:undo` | Undo |
| `:u` | Short form of undo |
| `:%!yourcommand` | Execute a command |
| `v` | Character-wise Visual Mode |
| `Shift + V` | Line-wise Visual Mode |
| `Ctrl + V` | Block-wise Visual Mode |
| `Ctrl + Q` | Block-wise Visual Mode |
| `d` | Delete selected text |
| `y` | Yank/copy selected text |
| `p` | Paste yanked text |

---

# NANO Quick Reference

| Shortcut | Function |
|---|---|
| `nano filename` | Open/create a file in Nano |
| `Ctrl + S` | Save |
| `Alt + U` | Undo |
| `Alt + E` | Redo |
| `Ctrl + X` | Exit |
| `Ctrl + T` | Command Execute |
| `Alt + 6` | Copy |
| `Ctrl + K` | Cut |
| `Ctrl + U` | Paste |
| `Shift + Arrow` | Select |
| `Ctrl + R` | Read/append text from another file |

---

# Linux User Management Quick Reference

| Command | Purpose |
|---|---|
| `whoami` | Show the current username |
| `sudo YourCommand` | Execute a command with superuser privileges |
| `sudo useradd username` | Create a user using `useradd` |
| `sudo adduser username` | Create a user using `adduser` |
| `sudo su` | Access the root user |

---

@innovatorsemir