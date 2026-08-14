# Kali Linux Overview & Linux Command Basics

## Overview of Kali Linux

In this course, we will demonstrate Linux using **Kali Linux** with the **GNOME Desktop Environment**. However, you are free to use other desktop environments such as **KDE Plasma**, **XFCE**, or **MATE**.

> **Previously known as:** BackTrack Linux

You can switch between different desktop environments depending on your preference.

Examples:
- GNOME
- KDE Plasma
- XFCE
- MATE

---

# Kali Linux Tool Categories

Kali Linux comes pre-installed with hundreds of penetration testing and security tools organized into categories.

---

## 1. Information Gathering

Tools used to collect information about systems, networks, domains, and hosts.

Examples:

- dmitry
- ike-scan
- legion
- maltego
- netdiscover
- nmap
- p0f
- recon-ng
- spiderfoot

---

## 2. Vulnerability Analysis

Tools used to discover vulnerabilities in systems and networks.

Examples:

- legion
- lynis
- nikto
- nmap
- unix-privesc-check

---

## 3. Web Application Analysis

Tools used to find vulnerabilities and exploits in web applications.

Examples:

- Burp Suite
- commix
- httrack
- paros
- skipfish
- sqlmap
- webscarab
- WPScan
- OWASP ZAP

---

## 4. Database Assessment

Tools used to identify vulnerabilities in databases.

Examples:

- sqlmap
- jSQL Injection

---

## 5. Password Attacks

Tools used for password auditing and password recovery.

Examples:

- CeWL
- Crunch
- Hydra
- John the Ripper
- Hashcat

---

## 6. Wireless Attacks

Tools used for testing wireless network security.

Examples:

- Aircrack-ng
- Kismet
- Wifite
- Reaver
- Bully

---

## 7. Reverse Engineering

Tools used to analyze software, mobile applications, and binary files.

Examples:

- apktool
- Ghidra
- radare2
- jadx

---

## 8. Exploitation Tools

Tools used to exploit discovered vulnerabilities.

Examples:

- Metasploit Framework
- Searchsploit
- BeEF

---

## 9. Sniffing & Spoofing

Tools used to capture and analyze network traffic.

Examples:

- Wireshark
- Ettercap
- Bettercap
- Tcpdump

---

## 10. Post Exploitation

Tools used after successfully gaining access to a target.

Examples:

- PowerSploit
- Empire
- Backdoor Factory

---

## 11. Forensics

Tools used for digital forensic investigations and evidence analysis.

Examples:

- Autopsy
- Foremost
- Binwalk
- Volatility

---

## 12. Reporting Tools

Tools used for documentation and report preparation.

Examples:

- Dradis
- CherryTree
- Maltego

---

## 13. Social Engineering Tools

Tools used to perform security awareness testing through social engineering.

Examples:

- Social Engineering Toolkit (SET)
- BeEF

---

## 14. System Services

Utilities used to start or stop Kali services.

Examples:

```bash
beef-xss start
beef-xss stop

dradis start
dradis stop
```

---

## 15. Commonly Used Applications

Applications used for everyday tasks.

Examples:

- Firefox
- Terminal
- Text Editor
- File Manager
- VS Code
- LibreOffice

---

# The Linux Shell

The **Shell** is the interface between the user and the Linux Kernel.

It accepts user commands, interprets them, and sends them to the kernel for execution.

```text
User
   │
   ▼
 Shell
   │
   ▼
 Kernel
   │
   ▼
Hardware
```

Popular Linux shells include:

- bash
- zsh
- fish
- sh

To check your current shell:

```bash
echo $SHELL
```

---

# Linux Command Basics

Linux systems use the **Shell** to execute commands.

A **command** is a small program that performs one specific task.

> "Small programs that do one task well."

---

# Parts of a Linux Terminal

A typical Linux terminal contains five parts:

```text
rexder@HunterMachine:~/Documents$
```

### 1. Username

Example:

```text
rexder
```

---

### 2. Hostname

Example:

```text
HunterMachine
```

---

### 3. Current Directory (Path)

Example:

```text
~/Documents
```

---

### 4. Privilege Symbol

```text
$
```

Means the current user is a **normal user**.

```text
#
```

Means the current user is **root (administrator)**.

---

### 5. Command Area

The place where commands are typed.

Example:

```bash
ls
pwd
cd
```

---

# Linux Command Basics

- On linux there are over 1000 commands. But we are Expected to know the main and useful only.
- Also those commands have their own **options** and **arguments**.

Command
*$ command --option argument*

## What is Command?

> **"Small programs that do one task well"**

---

# `ls` / List Directory

## `ls` / List Directory

### SYNOPSIS

```bash
ls [OPTION] [FILE]
```

### DESCRIPTION

List information about the files in the current directory by default.

### Example

```bash
ls
```

Example output:

```text
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos
```

---

# `tree`

## `tree`

### SYNOPSIS

```bash
tree [FOLDER]
```

### DESCRIPTION

List information about files and folders with a tree structure.

The current directory is used by default.

### Example

```bash
tree GTSTv1/
```

Example:

```text
GTSTv1/
├── Day1 - Introduction.md
├── Notes
│   └── Season1
└── README.md

3 directories, 2 files
```

---

# `ls` Options

## `ls -l`

```bash
ls -l
```

- `-l` = listed / long listing

Example:

```text
total 32
drwxr-xr-x 2 rexder rexder 4096 Dec 16 02:32 Desktop
drwxr-xr-x 2 rexder rexder 4096 Dec  6 03:03 Documents
drwxr-xr-x 4 rexder rexder 4096 Dec  9 08:08 Downloads
drwxr-xr-x 2 rexder rexder 4096 Dec  6 03:03 Music
drwxr-xr-x 2 rexder rexder 4096 Dec 15 02:21 Pictures
drwxr-xr-x 2 rexder rexder 4096 Dec  6 03:03 Public
drwxr-xr-x 2 rexder rexder 4096 Dec  6 03:03 Templates
drwxr-xr-x 2 rexder rexder 4096 Dec  6 03:03 Videos
```

## `ls -a`

```bash
ls -a
```

- `-a` = hidden

Shows hidden files.

Examples:

```text
.bash_logout
.bashrc
.bashrc.original
.cache
.config
.face
.face.icon
.profile
.zsh_history
.zshrc
```

> **Linux hidden files start with a dot (`.`).**

## `ls filename`

```bash
ls filename
```

Lists the specified file.

## `ls -R`

```bash
ls -R
```

- `-R` = recursive

Lists directories recursively.

## Combining Options

You can combine options.

```bash
ls -Rla
```

---

# `cd` / Change Directory

## `cd` / Change Directory

### SYNOPSIS

```bash
cd [directory]
```

### DESCRIPTION

It is used to change the current working directory.

### Example

```bash
cd Downloads
```

After changing directory:

```text
~/Downloads
```

---

# `cd` Examples

## Common `cd` Commands

### Go to root

```bash
cd /
```

Meaning:

```text
=> root
```

### Go back to user's home directory

```bash
cd
```

Meaning:

```text
=> Back to User's home directory
```

### Go back one directory

```bash
cd ..
```

Meaning:

```text
=> 1x Back
```

### Go back two directories

```bash
cd ../..
```

Meaning:

```text
=> 2x Back
```

### Go to a folder

```bash
cd foldername
```

### Folder name with spaces

If the folder name has spaces, add the name inside quotation marks.

```bash
cd "folder name"
```

---

# `pwd` / Print Working Directory

## `pwd` / Print Working Directory

### SYNOPSIS

```bash
pwd [options]
```

### DESCRIPTION

It prints the path of the working directory, starting from the root.

It prints the full filename/path of the current working directory.

### Example

Current directory:

```text
~/Documents
```

After typing:

```bash
pwd
```

Output:

```text
/home/rexder/Documents
```

### `pwd` Options

```text
-L, --logical
```

Use `PWD` from the environment, even if it contains symlinks.

```text
-P, --physical
```

Avoid all symlinks.

```text
--help
```

Display help and exit.

```text
--version
```

Output version information and exit.

---

# `echo`

## `echo`

### SYNOPSIS

```bash
echo [string]
```

### Example

```bash
echo "Hello Geeztech Security Testers."
```

Output:

```text
Hello Geeztech Security Testers.
```

### DESCRIPTION

The `echo` command in Linux is used to display a line of text/string that is passed as an argument.

---

# Output Redirecting

## Output Redirecting

You can write the output of any command into files.

This is called **Redirecting**.

To do this, we use the `>` sign.

### Write Output to a File

```bash
echo text > file.txt
```

Example:

```bash
echo "Hello Geeztech Security Testers." > geez.txt
```

### Append Text

You can add text using `>>`.

```bash
echo text >> file.txt
```

---

# `cat` / `head` / `tail` / `less`

## Commands

```bash
cat
head
tail
less
```

### SYNOPSIS

```bash
cat [FILE]...
head [FILE]...
tail [FILE]...
less [FILE]...
```

### DESCRIPTION

All are used to show the content of a file.

- `head` and `tail` will display the **10 lines** of the file.

### Example: `cat`

```bash
cat geez.txt
```

Output:

```text
Hello Geeztech Security Testers.
```

### Example: Number Lines with `cat -n`

```bash
cat VlanNote -n
```

`-n` will add number lines.

Example content:

```text
1  # Commands
2  - enable
3  - conf t
4
5  > To Create A VLAN
6  - vlan <VLAN NUM>
7  - name <VLAN NAME>
8  - exit
9
10 > Assigning Single Ports to a VLAN
11 - interface
12 - int fa0/2
13 - switchport mode access
14 - switchport access vlan <VLAN NUM>
15     # We Use access because we are using accessport for the end users.
```

### Example: `head`

```bash
head VlanNote
```

Example output:

```text
# Commands
- enable
- conf t
```

---

# `touch`

## `touch`

### SYNOPSIS

```bash
touch [FILE1] [FILE2] [FILE3]
```

### DESCRIPTION

Creates any kind of files with the name you give it, with empty content inside.

### Examples

```bash
touch geez.txt
```

```bash
touch Day3.md
```

After creating:

```text
Day3.md
geez.txt
```

---

# `mkdir` / Make Directory

## `mkdir` / Make Directory

### SYNOPSIS

```bash
mkdir [FOLDER-NAME1] [FOLDER-NAME2] [FOLDER-NAME3]
```

### DESCRIPTION

Creates a folder with the name you give it.

### Example

```bash
mkdir foldername
```

### Creating Nested Folders

```bash
mkdir -p folder1/folder2/folder3
```

### Folder Names with Spaces

Don't forget to add quotation marks when you are using folders with spaces between them.

```bash
mkdir "Geez Tech"
```

---

# `mkdir -p`

If a parent directory does not exist, creating a nested folder directly can produce an error.

Example:

```bash
mkdir Notes/Season1
```

Output:

```text
mkdir: cannot create directory 'Notes/Season1': No such file or directory
```

Use `-p`:

```bash
mkdir -p Notes/Season1
```

Then:

```bash
ls -la Notes/
```

Example:

```text
total 12
drwxrwxr-x 3 rexder rexder 4096 Oct 25 17:03 ./
drwxrwxr-x 5 rexder rexder 4096 Oct 25 17:03 ../
drwxrwxr-x 2 rexder rexder 4096 Oct 25 17:03 Season1/
```

---

# `clear`

## `clear`

### SYNOPSIS

```bash
clear
```

### DESCRIPTION

Clears your screen.

---

# `rm` / Remove

## `rm` / Remove

### SYNOPSIS

```bash
rm [FILE1] [FILE2] [FILE3]
```

### DESCRIPTION

Remove file.

### Example

```bash
rm geez.txt
```

---

# `rm` Options

## `rm -r`

```bash
rm -r
```

- `-r` = recursive
- Used for removing directories/folders recursively.

## `rm -i`

```bash
rm -i
```

- `-i` = prompt / ask
- Prompts before removing.

Example:

```text
rm: remove regular file 'geez.txt'? yes
```

## `rm -f`

```bash
rm -f
```

- `-f` = force delete

## Combining Options

You can use them in combination.

Example:

```bash
rm -rf filename
```

---

# `cp` / `mv` — Copy / Move

## `cp` / Copy

### SYNOPSIS

```bash
cp [oldFILEplace] [newfilePlace]
```

## `mv` / Move

### SYNOPSIS

```bash
mv [oldFILEplace] [newfilePlace]
```

### DESCRIPTION

Copy/move files and folders.

### Copying a Folder

If you want to copy a folder which contains files, you have to use the `-r` option.

```bash
cp -r Desktop/ /root/
```

---

# `cp` / `mv` Examples

You can use path notations with `cp`, `mv`, and `cd`.

### Copy a file using a relative path

```bash
cp "Cyber sec note.pdf" ../../tmp
```

### Move a file to Downloads

```bash
mv adb.1000.log ~/Downloads/
```

### Move everything

```bash
mv * /root
```

---

# `grep`

## `grep` — Global Search for Regular Expression

### SYNOPSIS

```bash
grep [options] pattern [files]
```

### DESCRIPTION

The `grep` filter searches a file for a particular pattern of characters and displays all lines that contain that pattern.

The pattern that is searched in the file is referred to as the **regular expression**.

`grep` stands for:

> **Global Search for Regular Expression and Print Out**

### Example

```bash
grep "my" grep_test.txt
```

Example output:

```text
hello friend name is nathan , my friend is good boy.
```

---

# `grep` Options

## Search for a Term

```bash
grep "search" file
```

### `-i` — Case Insensitive

```bash
grep -i "term" file
```

Search without considering uppercase/lowercase differences.

### `-c` — Count

```bash
grep -c "term" file
```

Count the number of matching lines.

### `-n` — Line Number

```bash
grep -n "term" file
```

Display the line number where the term is found.

### `-l` — Display Filename

```bash
grep -l "term" file
```

Display the filename.

### `-r` — Search in Folders

```bash
grep -r "search" foldername
```

Search text in folders recursively.

### `-v` — Without the Term

```bash
grep -v "term" filename
```

Display lines without this term.

### `-o` — Display Only the Matching Word

```bash
grep -o "pattern" filename
```

Display that specific word only.

---

# More `grep` Examples

## Recursive Search

```bash
grep -ran "HTB" .
```

This searches recursively and displays matching results.

Example output can include:

```text
trickster/shop/admin634ewut...
trickster/.../themes/default/...
trickster/.../metadata/Slic3r_model.config:4:
```

### `grep -rno`

```bash
grep -rno HTB
```

Example:

```text
k.json:3799: "integrity": "sha512-..."
lock.json:4616: "integrity": "sha512-..."
```

## `grep -c`

Create a file:

```bash
echo "Cyber Security is Very Fun Field" > hope.txt
```

Count the lines containing `Fun`:

```bash
grep -c "Fun" hope.txt
```

Output:

```text
1
```

---

# `wc` / Word Count

## `wc` — Word Count

### SYNOPSIS

```bash
wc [OPTION]... [FILE]...
```

### DESCRIPTION

It is used to find out:

- Number of lines
- Word count
- Byte count
- Character count

in the files specified in the file arguments.

### Example

```bash
wc grep_test.txt
```

Example output:

```text
1 13 59 grep_test.txt
```

The output represents:

```text
Line (-l)    Word (-w)    Byte (-c)
```

### Count Lines

```bash
wc -l grep_test.txt
```

Example:

```text
1 grep_test.txt
```

---

# Multiple Command Executions

## Multiple Command Executions

You can run/execute multiple commands in one line.

There are **3 methods**:

1. AND (`&&`)
2. OR (`||`)
3. Piping (`|`)

---

# AND (`&&`)

## AND (`&&`)

With an **AND operation**, all commands you enter will be executed **if the previous commands work without error**.

Example:

```bash
touch test && ls
```

If the command is typed incorrectly:

```bash
touh test && ls
```

Output:

```text
Command 'touh' not found, did you mean:
  command 'touch' from deb coreutils

Try: sudo apt install <deb name>
```

The second command is not executed because the first command failed.

---

# OR (`||`)

## OR (`||`)

With an **OR operation**, the command after `||` will be executed if the previous command has an error.

Example:

```bash
touh test || ls
```

If `touh` fails, `ls` is executed.

Example error:

```text
Command 'touh' not found, did you mean:
  command 'touch' from deb coreutils

Try: sudo apt install <deb name>
```

---

# Piping (`|`)

## Pipe (`|`)

A pipe helps you run commands by using the **output of the first command as the input for the next one**.

Example:

```bash
grep test.txt
```

Then:

```bash
grep "hello" test.txt
```

The output can be passed to another command using `|`.

Example:

```bash
cat test.txt | grep "hello"
```

Output:

```text
my friend my name is nathan , my friend is good boy.
```

---

# `sed` / Stream Editor

## `sed` / Stream Editor

`sed` is:

- A powerful command-line tool for parsing and transforming text in Linux.
- Processes files line-by-line, making it efficient for large text processing tasks.

### Common Uses

- Text substitution and replacement
- Deleting or selecting specific lines
- Efficient text manipulation for tasks like network information gathering or penetration testing logs

### Syntax

```bash
sed [options] 'command' file
```

---

## Substitute / Replace

```bash
sed 's/old/new/' file
```

You can use a `|` sign instead of `/` too.

```bash
s|old|new|
```

Use `g` at the end to replace if it finds the word more than one time in one line.

```bash
s/old/new/g
```

## Delete

```bash
sed '/pattern/d' file
```

---

## `sed` Examples

### Replace `Nathan` with `Minte`

```bash
cat temp.txt | sed 's/Nathan/Minte/'
```

### Replace `Hello` with `Hi`

```bash
cat temp.txt | sed 's/Hello/Hi/'
```

### Replace all occurrences

```bash
cat temp.txt | sed 's/Hello/Hi/g'
```

---

# `sed` Continued

## Example File

```bash
cat temp.txt
```

Example content:

```text
Hello my name is Nathan, i got this course of linux and
to learn linux. I love linux, so i said HELLO world

Hello my name is Nati, i got this course of linux and
to learn linux. I love linux, so i said HELLO world

Hello my name is Nathan, i got this course of linux and
to learn linux. I love linux, so i said HELLO world

Hello my name is Minte, i got this course of linux and
to learn linux. I love linux, so i said HELLO world
```

### Delete Lines Containing `Nathan`

```bash
cat temp.txt | sed '/Nathan/d'
```

This removes the lines containing `Nathan`.

---

# `awk`

## `awk`

- A versatile command-line text-processing tool.
- Ideal for pattern scanning and data extraction in structured text.
- Named after its creators:
  - Aho
  - Weinberger
  - Kernighan

### Features

- Processes text line-by-line.
- Supports complex pattern matching.
- Allows field-based text manipulation, making it great for column-based data such as CSV files.

### Basic Syntax

```bash
awk 'pattern { action }' file.txt
```

### Print Specific Columns

```bash
awk '{print $1, $3}' file.txt
```

Prints columns 1 and 3.

### Print Matching Lines

```bash
awk '/pattern/ {print $0}' file.txt
```

Prints lines matching `"pattern"`.

---

## Example Data

```text
ID,Name,Department,Salary,Join Date

101,John Doe,Engineering,65000,2022-05-01
102,Jane Smith,Marketing,55000,2021-08-15
103,Emily Johnson,Sales,70000,2020-09-22
104,Michael Brown,Engineering,72000,2019-12-01
105,Jessica White,Sales,68000,2021-01-10
106,Chris Green,Marketing,53000,2023-02-25
107,Sarah Black,Engineering,69000,2022-07-20
108,Tom Blue,Sales,71000,2018-06-18
109,Amy Gold,Engineering,65000,2023-03-30
110,David Silver,Marketing,56000,2020-11-11
```

---

# `awk` Columns and Delimiters

## Delimiters

By default, `awk` determines columns if they are separated by a **space (` `)**.

Here, space is known as the **Delimiter**.

### Change Delimiter

Use the `-F` option.

```bash
-F ","
```

### Built-in Variables

```text
$0
```

Entire line of text.

```text
$1, $2, ...
```

Represents each column/field in a line.

```text
NR
```

Line/record number.

```text
NF
```

Number of fields in the current record.

---

## Using `awk` with a File

```bash
awk 'options' file.txt
```

## Using `awk` with a Pipe

```bash
cat 'file.txt' | awk 'options'
```

---

## Example

```bash
cat log1.txt | awk '{print $1}'
```

Output:

```text
Name
John
Jane
Emily
```

### Print Column 2

```bash
cat log1.txt | awk '{print $2}'
```

Output:

```text
Salary
Doe
Smith
Johnson
```

---

## Using a Comma Delimiter

```bash
cat log.txt | awk -F "," '{print $2}'
```

Output:

```text
Name
John Doe
Jane Smith
Emily Johnson
Michael Brown
```

---

# More `awk`

## Compare a Column

```bash
awk '$3 > 50 {print $1, $3}' file.txt
```

Prints rows where column 3 is greater than 50.

### Example: Salary Greater Than 68000

```bash
cat log.txt | awk -F "," '$4 > 68000 {print $2}'
```

Output:

```text
Name
Emily Johnson
Michael Brown
Sarah Black
Tom Blue
```

---

## Print the Last Field

```bash
cat log.txt | awk -F "," '{print $NF}'
```

Output:

```text
Join Date
2022-05-01
2021-08-15
2020-09-22
2019-12-01
2021-01-10
2023-02-25
2022-07-20
2018-06-18
2023-03-30
2020-11-11
```

`$NF` represents the last field.

---

## Search for a Pattern

```bash
cat log.txt | awk -F "," '/6/ {print $2}'
```

Example output:

```text
John Doe
Jessica White
Chris Green
Sarah Black
Tom Blue
Amy Gold
David Silver
```

---

## Sum of a Column

```bash
cat log.txt | awk -F "," '{sum += $4} END {print "Total: ",sum}'
```

Output:

```text
Total: 644000
```

---

# Command Quick Reference

| Command | Purpose |
|---|---|
| `ls` | List directory contents |
| `ls -l` | List in long format |
| `ls -a` | Show hidden files |
| `ls -R` | List recursively |
| `tree` | Display files/folders as a tree |
| `cd` | Change directory |
| `pwd` | Print working directory |
| `echo` | Display text |
| `>` | Redirect output to a file |
| `>>` | Append output to a file |
| `cat` | Display file contents |
| `head` | Display beginning of a file |
| `tail` | Display end of a file |
| `less` | View file contents |
| `touch` | Create an empty file |
| `mkdir` | Create a directory |
| `mkdir -p` | Create nested directories |
| `clear` | Clear terminal screen |
| `rm` | Remove files |
| `rm -r` | Remove recursively |
| `rm -i` | Ask before removing |
| `rm -f` | Force removal |
| `cp` | Copy files/folders |
| `mv` | Move files/folders |
| `grep` | Search text patterns |
| `wc` | Count lines, words, bytes |
| `sed` | Stream editor for text processing |
| `awk` | Text processing and field extraction |
| `&&` | Execute next command when previous succeeds |
| `||` | Execute next command when previous fails |
| `\|` | Pass output of one command as input to another |

---

@innovatorsemir