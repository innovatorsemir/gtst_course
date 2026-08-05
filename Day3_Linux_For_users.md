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

# Linux Commands

## pwd (Print Working Directory)

### Synopsis

```bash
pwd [options]
```

### Description

Prints the absolute path of the current working directory, starting from the root directory.

Example:

```bash
pwd
```

Output:

```text
/home/rexder/Documents
```

---

## cd (Change Directory)

### Synopsis

```bash
cd [directory]
```

### Description

Changes the current working directory.

Examples:

Go to the root directory:

```bash
cd /
```

Return to your home directory:

```bash
cd
```

Go back one directory:

```bash
cd ..
```

Go back two directories:

```bash
cd ../..
```

Open a folder:

```bash
cd Downloads
```

If the folder name contains spaces:

```bash
cd "Folder Name"
```

---

## ls (List Directory Contents)

Displays files and folders inside a directory.

### Basic Usage

```bash
ls
```

---

### Useful Options

List in long format:

```bash
ls -l
```

Show hidden files:

```bash
ls -a
```

List a specific file or directory:

```bash
ls filename
```

List directories recursively:

```bash
ls -R
```

Combine options:

```bash
ls -Rla
```

or

```bash
ls -la
```

> **Note:** Hidden files in Linux begin with a dot (`.`).

Examples:

```text
.bashrc
.profile
.cache
.config
```

---

# tree Command

Displays directories and files in a tree structure.

Example:

```bash
tree
```

Output:

```text
.
├── Documents
├── Downloads
├── Music
├── Pictures
└── Videos
```

---

# Multiple Command Execution

Run multiple commands in one line.

Execute one after another:

```bash
pwd ; ls ; whoami
```

Run the next command only if the previous command succeeds:

```bash
mkdir test && cd test
```

Run the second command only if the first one fails:

```bash
mkdir test || echo "Folder already exists"
```

---

# Text Manipulation with Linux

Linux provides many command-line utilities for manipulating text files.

Common commands include:

- cat
- less
- more
- head
- tail
- nano
- vim
- grep
- sort
- uniq
- cut
- tr
- sed
- awk

These commands allow you to:

- View files
- Edit text
- Search for patterns
- Replace text
- Filter output
- Process large files efficiently

---

@innovatorsemir