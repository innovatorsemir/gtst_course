# Linux Notes: Script Installation, Processes, Services, Tmux, Wget, Find and More

## Script Installation

Many tools and programs are developed as open-source projects. Their source code can often be found on platforms such as GitHub.

To download a project from a Git repository, we can use the `git clone` command.

### Clone a GitHub Repository

```bash
git clone <repository_link>
```

Example:

```bash
git clone https://github.com/username/project.git
```

This downloads the repository into the current directory.

---

# Script Modules and Dependencies

Scripts can be written using different programming languages, such as:

- Python
- Bash
- Go
- Ruby

Many programs require additional modules, libraries, or dependencies to work correctly.

## Python Modules

Python uses `pip` to install modules.

```bash
pip install modulename
```

Example:

```bash
pip install requests
```

### Installing Dependencies from `requirements.txt`

Many Python projects include a file called:

```text
requirements.txt
```

To install all required dependencies:

```bash
pip install -r requirements.txt
```

On some Linux systems, you may need:

```bash
pip3 install -r requirements.txt
```

---

# Installing Python Pip

If `pip` is not installed, you may see an error similar to:

```text
Command 'pip' not found
```

You can install Python's package manager using:

```bash
sudo apt install python3-pip
```

Check the installed version:

```bash
pip3 --version
```

Install a Python module:

```bash
pip install modulename
```

Example:

```bash
pip install termcolor
```

Install project dependencies:

```bash
pip install -r requirements.txt
```

---

# Go Package Installation

Some programs and tools are written using the Go programming language.

There are different ways to install Go packages.

## Old Method

```bash
go get github.com/capotej/groupcache-db-experiment.git
```

## New Method

The commonly used modern method is:

```bash
go install github.com/lc/gau/v2/cmd/gau@latest
```

Go packages are often installed inside:

```text
~/go/bin
```

You can check the directory:

```bash
ls ~/go/bin
```

To move a binary to `/usr/bin`:

```bash
sudo mv filename /usr/bin/
```

After that, the command may be available system-wide.

Example:

```bash
sudo mv gau /usr/bin/
```

---

# Ruby Package Installation

Ruby uses the `gem` package manager.

To install a Ruby module:

```bash
gem install modulename
```

Example:

```bash
gem install bundler
```

---

# Getting Help on Linux

Linux provides several ways to get help about commands and programs.

## Man Pages

The `man` command displays the manual page of a command.

Syntax:

```bash
man command
```

Example:

```bash
man awk
```

Navigation keys:

- Arrow keys — Move through the manual.
- `q` — Quit the manual.

Example:

```bash
man ls
```

Not every command necessarily has a complete manual page installed.

---

## Help Options

Many commands provide built-in help.

Common formats:

```bash
command -h
```

```bash
command --help
```

Sometimes:

```bash
command -help
```

Example:

```bash
ls --help
```

---

# Linux Processes and Services

## Processes

A process is a running instance of a program.

For example, when you:

- Open a web browser.
- Run a command.
- Open a text editor.
- Start an application.

Linux loads the program into memory and runs it as a process.

Each process usually has a unique:

```text
PID
```

PID means:

```text
Process ID
```

Processes may also have:

```text
PPID
```

PPID means:

```text
Parent Process ID
```

The parent process is the process that started another process.

---

# Viewing Processes

The `ps` command is used to display processes.

Basic command:

```bash
ps
```

This usually shows processes associated with the current terminal.

View all processes:

```bash
ps -A
```

Another commonly used command:

```bash
ps aux
```

View processes for a specific user:

```bash
ps -u username
```

Example:

```bash
ps -u semir
```

---

# Managing Processes

Linux uses signals to communicate with processes.

To see available signals:

```bash
kill -l
```

Example output:

```text
HUP INT QUIT ILL TRAP ABRT BUS FPE KILL USR1 SEGV USR2
PIPE ALRM TERM STKFLT CHLD CONT STOP TSTP TTIN TTOU
URG XCPU XFSZ VTALRM PROF WINCH POLL PWR SYS
```

---

## Killing a Process

Syntax:

```bash
kill [options] PID
```

Example:

```bash
kill 3841
```

Forcefully terminate a process:

```bash
kill -9 PID
```

Example:

```bash
kill -9 3841
```

`-9` sends the `SIGKILL` signal.

This immediately terminates the process when possible.

---

## Stopping and Resuming Processes

Stop a process:

```bash
kill -19 PID
```

Resume a stopped process:

```bash
kill -18 PID
```

Signal numbers can be replaced with signal names in many cases.

For example:

```bash
kill -STOP PID
```

Resume:

```bash
kill -CONT PID
```

---

## Kill All Processes with a Specific Name

Use:

```bash
killall programname
```

Example:

```bash
killall picom
```

This terminates processes matching the specified program name.

---

# Real-Time Process Monitoring

The `ps` command gives a snapshot of processes.

For real-time monitoring, Linux provides:

```bash
top
```

Run:

```bash
top
```

The `top` command displays:

- Running processes.
- CPU usage.
- Memory usage.
- Process IDs.
- System load.

---

# HTOP

`htop` is an enhanced and interactive process monitoring tool.

Install it:

```bash
sudo apt install htop
```

Run:

```bash
htop
```

It provides a more interactive interface for managing processes.

---

# Foreground and Background Processes

Normally, when you run a command, it runs in the foreground.

The terminal waits until the command finishes.

Example:

```bash
nano file.txt
```

The terminal is occupied until Nano is closed.

---

## Running a Process in the Background

Use the `&` symbol.

Example:

```bash
command &
```

Example:

```bash
firefox &
```

This starts the program in the background.

---

## Suspending a Process

While a foreground process is running, press:

```text
Ctrl + Z
```

This suspends the process.

Example:

```text
[1]+ Stopped nano takeme1.txt
```

---

## Returning a Process to the Foreground

Use:

```bash
fg
```

Example:

```bash
fg
```

You can also specify a job:

```bash
fg %1
```

---

## Sending a Process to the Background

After suspending a process with:

```text
Ctrl + Z
```

You can run:

```bash
bg
```

This continues the suspended job in the background.

---

## Stopping a Running Foreground Process

Press:

```text
Ctrl + C
```

This sends an interrupt signal to the process.

---

# Linux Services

Services are programs that run in the background.

They are often used for:

- Web servers.
- Databases.
- Network services.
- System monitoring.
- Scheduled tasks.

Services are also commonly called:

```text
Daemons
```

Examples include:

- `apache2`
- `ssh`
- `mysql`
- `NetworkManager`

---

# Managing Services with systemctl

Modern Linux systems often use `systemd`.

The `systemctl` command is used to manage services.

## Start a Service

```bash
sudo systemctl start servicename
```

Example:

```bash
sudo systemctl start apache2
```

---

## Stop a Service

```bash
sudo systemctl stop servicename
```

Example:

```bash
sudo systemctl stop apache2
```

---

## Restart a Service

```bash
sudo systemctl restart servicename
```

---

## Check Service Status

```bash
sudo systemctl status servicename
```

Example:

```bash
sudo systemctl status apache2
```

---

## Enable a Service

Enable a service to start automatically when the computer boots:

```bash
sudo systemctl enable servicename
```

Example:

```bash
sudo systemctl enable apache2
```

---

## Disable a Service

Prevent a service from automatically starting at boot:

```bash
sudo systemctl disable servicename
```

Example:

```bash
sudo systemctl disable apache2
```

---

# Managing Services with service

Another command used on Linux systems is:

```bash
service
```

Start a service:

```bash
sudo service servicename start
```

Stop a service:

```bash
sudo service servicename stop
```

Example:

```bash
sudo service apache2 start
```

---

# The Null Device

The Linux null device is:

```text
/dev/null
```

Anything sent to `/dev/null` is discarded.

It is sometimes called:

```text
The bit bucket
```

You can use it when you want to ignore output.

---

# Standard Output and Standard Error

Linux programs generally use file descriptors.

```text
STDIN  = 0
STDOUT = 1
STDERR = 2
```

## Standard Output

Standard output can be redirected using:

```bash
command 1> filename
```

Example:

```bash
ls 1> stdout.txt
```

Or simply:

```bash
ls > stdout.txt
```

---

## Standard Error

Errors can be redirected using:

```bash
command 2> filename
```

Example:

```bash
ls Hello 2> stderr.txt
```

If `Hello` does not exist, the error will be stored inside:

```text
stderr.txt
```

Example:

```bash
cat stderr.txt
```

Possible output:

```text
ls: cannot access 'Hello': No such file or directory
```

---

## Redirect Errors to /dev/null

To hide errors:

```bash
command 2> /dev/null
```

Example:

```bash
ls Hello 2> /dev/null
```

The error will not be displayed.

---

## Redirect Both Output and Errors

Redirect standard output and standard error:

```bash
command > output.txt 2>&1
```

You can also redirect both to `/dev/null`:

```bash
command > /dev/null 2>&1
```

This hides both normal output and errors.

---

# Symbolic Links

A symbolic link is similar to a shortcut in Windows.

It points to another file or directory.

Symbolic links are useful when:

- A file path is very long.
- You want an easy shortcut.
- You want another path pointing to the same file.

---

## Creating a Symbolic Link

Syntax:

```bash
ln -s source_file target_name
```

Example:

```bash
ln -s /usr/share/ImageMagick-6/english.xml englishApache
```

Check the symbolic link:

```bash
ls -l englishApache
```

Example:

```text
lrwxrwxrwx 1 user user 36 Oct 20 18:23 englishApache -> /usr/share/ImageMagick-6/english.xml
```

A symbolic link starts with:

```text
l
```

The arrow:

```text
->
```

shows the original file or directory.

---

# Alias

An alias allows you to create a custom name for a command.

For example, instead of typing:

```bash
ls -la
```

You can create an alias:

```bash
alias rex='ls -la'
```

Now you can simply type:

```bash
rex
```

And it will run:

```bash
ls -la
```

---

# Temporary Aliases

Aliases created directly in the terminal are temporary.

Example:

```bash
alias rex='ls -la --color'
```

After closing the terminal, the alias may disappear.

---

# Permanent Aliases

To make aliases permanent, add them to your shell configuration file.

## Bash

For Bash:

```text
~/.bashrc
```

Edit it:

```bash
nano ~/.bashrc
```

Example:

```bash
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'
```

Add your own alias:

```bash
alias rex='ls -la --color'
```

Reload the configuration:

```bash
source ~/.bashrc
```

---

## Zsh

For Zsh:

```text
~/.zshrc
```

Edit:

```bash
nano ~/.zshrc
```

Add aliases:

```bash
alias hack='cd ~/Projects/Pentests/'
alias tools='cd ~/tools'
```

Reload:

```bash
source ~/.zshrc
```

---

## Fish Shell

Fish configuration file:

```text
~/.config/fish/config.fish
```

Example:

```bash
alias hack="cd ~/Projects/Pentests/"
alias tools="cd ~/tools"
```

---

# Example Alias Configuration

Example commands:

```bash
cowsay "Hello, Welcome Back" | lolcat
```

```bash
figlet HackTime
```

Aliases:

```bash
alias hackerone="cd ~/Projects/Pentests/H1"
alias ethio="cd ~/Projects/Pentests/Local"
alias tools="cd ~/tools"
```

---

# Important Alias Warning

Be careful when creating aliases.

For example:

```bash
alias cd='rm -rf'
```

This is extremely dangerous.

Never create destructive aliases unless you fully understand their effect.

---

# Tmux - Terminal Multiplexer

Tmux is a terminal multiplexer.

It allows you to:

- Create multiple terminal sessions.
- Split the terminal into multiple panes.
- Create windows or tabs.
- Switch between terminal sessions.

Install Tmux:

```bash
sudo apt install tmux
```

On some Linux distributions, it may already be installed.

Start Tmux:

```bash
tmux
```

---

# Tmux Configuration

The configuration file is usually:

```text
~/.tmux.conf
```

Create or edit it:

```bash
nano ~/.tmux.conf
```

Example configuration:

```text
unbind C-b
set -g prefix C-a

unbind %
unbind '"'

bind e split-window -h
bind o split-window -v

set -g base-index 1
setw -g pane-base-index 1
```

This changes the Tmux prefix from:

```text
Ctrl + B
```

to:

```text
Ctrl + A
```

---

# Tmux Commands

## Prefix Key

With the above configuration, the prefix is:

```text
Ctrl + A
```

Press the prefix first, then the command key.

---

## Split Horizontally

```text
Ctrl + A, then O
```

Depending on the configuration, this creates a horizontal split.

---

## Split Vertically

```text
Ctrl + A, then E
```

---

## Create a New Window

```text
Ctrl + A, then C
```

---

## Rename a Window

```text
Ctrl + A, then ,
```

Press:

```text
Ctrl + A
```

Then:

```text
,
```

---

## Switch Between Windows

```text
Ctrl + A, then window number
```

Example:

```text
Ctrl + A, then 1
```

---

## Switch Between Panes

```text
Ctrl + A, then Arrow Key
```

For example:

```text
Ctrl + A, then Right Arrow
```

---

## Exit Tmux

Type:

```bash
exit
```

You can also manage Tmux sessions using Tmux commands.

---

# Wget

`wget` is a command-line tool used to download files from websites and servers.

Syntax:

```bash
wget [options] [link]
```

Example:

```bash
wget https://example.com/file.pdf
```

Another example:

```bash
wget https://tldp.org/LDP/intro-linux/intro-linux.pdf
```

This downloads the file into the current directory.

---

# Find Command

The `find` command is used to search for files and directories.

It can search based on:

- Name.
- Type.
- Permission.
- Location.
- Size.
- Ownership.

Basic syntax:

```bash
find [search_path] [options] [search_value]
```

---

## Find a File by Name

Search the entire filesystem:

```bash
find / -name "linux"
```

This searches from the root directory.

---

## Find Inside a Specific Directory

Example:

```bash
find /home -name "file.txt"
```

---

# Find Files by Type

Find regular files:

```bash
find / -type f
```

Find directories:

```bash
find / -type d
```

Example:

```bash
find /home -type f
```

---

# Find Files by Permission

Find files with permission `777`:

```bash
find /home -perm 777
```

Be careful when searching the entire filesystem because some directories may generate permission errors.

You can hide those errors:

```bash
find / -perm 777 2> /dev/null
```

---

# Finding SUID Files

SUID files can be searched using:

```bash
find / -type f -perm -4000 2> /dev/null
```

Another common format:

```bash
find / -type f -perm /4000 2> /dev/null
```

This searches for regular files with the SUID permission.

---

# Useful Command Summary

## Git

| Command | Purpose |
|---|---|
| `git clone <link>` | Clone a repository |

## Python

| Command | Purpose |
|---|---|
| `pip install modulename` | Install a Python module |
| `pip install -r requirements.txt` | Install project dependencies |
| `sudo apt install python3-pip` | Install pip |

## Go

| Command | Purpose |
|---|---|
| `go install package@latest` | Install a Go package |
| `go get package` | Older method for fetching Go packages |

## Ruby

| Command | Purpose |
|---|---|
| `gem install modulename` | Install a Ruby module |

## Help

| Command | Purpose |
|---|---|
| `man command` | Open manual page |
| `command --help` | Display help |
| `command -h` | Display help |

## Processes

| Command | Purpose |
|---|---|
| `ps` | Show processes |
| `ps -A` | Show all processes |
| `ps aux` | Detailed process list |
| `ps -u username` | Show a user's processes |
| `kill PID` | Terminate a process |
| `kill -9 PID` | Forcefully terminate a process |
| `killall program` | Kill processes by name |
| `top` | Real-time process monitor |
| `htop` | Interactive process monitor |

## Foreground and Background

| Command | Purpose |
|---|---|
| `command &` | Run in background |
| `Ctrl + Z` | Suspend process |
| `bg` | Continue in background |
| `fg` | Return to foreground |
| `Ctrl + C` | Interrupt a process |

## Services

| Command | Purpose |
|---|---|
| `sudo systemctl start service` | Start service |
| `sudo systemctl stop service` | Stop service |
| `sudo systemctl restart service` | Restart service |
| `sudo systemctl status service` | Check status |
| `sudo systemctl enable service` | Enable at boot |
| `sudo systemctl disable service` | Disable at boot |

## Output Redirection

| Command | Purpose |
|---|---|
| `command > file` | Redirect standard output |
| `command 1> file` | Redirect standard output |
| `command 2> file` | Redirect errors |
| `command 2> /dev/null` | Hide errors |
| `command > /dev/null 2>&1` | Hide output and errors |

## Symbolic Links

| Command | Purpose |
|---|---|
| `ln -s source target` | Create a symbolic link |

## Aliases

| Command | Purpose |
|---|---|
| `alias name='command'` | Create an alias |
| `source ~/.bashrc` | Reload Bash configuration |
| `source ~/.zshrc` | Reload Zsh configuration |

## Tmux

| Command | Purpose |
|---|---|
| `tmux` | Start Tmux |
| `Ctrl + A, C` | Create new window |
| `Ctrl + A, E` | Split terminal |
| `Ctrl + A, O` | Split terminal |
| `Ctrl + A, Arrow` | Switch panes |
| `Ctrl + A, Number` | Switch windows |
| `exit` | Exit current shell/session |

## Wget

| Command | Purpose |
|---|---|
| `wget URL` | Download a file |

## Find

| Command | Purpose |
|---|---|
| `find / -name "name"` | Find by name |
| `find / -type f` | Find files |
| `find / -type d` | Find directories |
| `find /home -perm 777` | Find files by permission |
| `find / -type f -perm -4000 2> /dev/null` | Find SUID files |

---

# Final Notes

This section covered:

- Script installation from GitHub.
- `git clone`.
- Python modules and `pip`.
- `requirements.txt`.
- Go package installation.
- Ruby gems.
- Linux help commands.
- Processes and PIDs.
- Killing and managing processes.
- `top` and `htop`.
- Foreground and background processes.
- Linux services.
- `systemctl`.
- Output redirection.
- `/dev/null`.
- Symbolic links.
- Aliases.
- Shell configuration files.
- Tmux.
- `wget`.
- The `find` command.
- Searching files by name, type, and permission.
- Finding SUID files.

---

@innovatorsemir