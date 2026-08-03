# Introduction to Linux

#### What is Linux?

Linux is a **Kernel**.

#### What is Kernel?

Kernel is a code/program that is used to communicate between your software and hardware. It allocates system resources such as CPU, memory, and devices.

```text
Applications
      ↓
    Kernel
      ↓
CPU - Memory - Devices
```

---

## History of Linux

- In **1969**, a team led by computer scientists **Ken Thompson** and **Dennis Ritchie** created the first version of **UNIX** on a PDP-7 minicomputer.
- It was chosen mainly because of Thompson's familiarity with the system from his hobby work on it.
- However, UNIX was not cheap and was **not open-source**.
- Later, **Linus Torvalds** created the **Linux Kernel** and posted it online to make it open source. The Linux kernel was developed using the **C programming language**.
- **Richard Stallman** announced the **GNU Project** in **1983** and co-founded the **Free Software Foundation (FSF)** in **1985**.
- GNU was a free software replacement for the UNIX operating system, but it was **not a complete operating system**. It only provided software such as:
  - Bash
  - Tar
  - Emacs
- Therefore,

> **GNU + Linux = GNU/Linux Operating System**

- The GNU/Linux project was started to create an open-source Unix-like operating system whose source code could be copied, modified, and redistributed.

---

## What is Shell and its Types?

- Users communicate with the **Kernel** through the **Shell**.
- The **Shell** is a **Command Line Interpreter (CLI)**.
- It translates commands entered by the user into a language understood by the Kernel.

---

## Types of Shells

Based on their features, there are many types of shells.

### SH (Bourne Shell)
- The original Unix shell.
- Developed by **Stephen Bourne**.

### BASH (Bourne Again Shell)
- The most widely used shell in Linux.
- An enhanced version of SH with additional features.

### ZSH (Z Shell)
- A powerful shell that extends BASH.
- Features:
  - Better tab completion
  - Themes
  - Plugins

### FISH (Friendly Interactive Shell)
- A user-friendly shell.
- Features:
  - Syntax highlighting
  - Auto suggestions
  - Easy configuration

> They differ in:
- Coloring
- Piping
- Command completion
- Plugins
- Other advanced features

> To identify your current shell:

```bash
echo $SHELL
```

---

## What is an Operating System (OS)?

We have mentioned UNIX and GNU/Linux as operating systems, but what is an OS?

An **Operating System (OS)** is the main software of a computer that manages hardware and software resources and allows applications to run.

It contains:

- Kernel
- Software
- Desktop Environment

---

### Types of Desktop Environments in Linux

1. MATE
2. GNOME
   - Beautiful animations
   - Similar feel to Windows 11
3. KDE Plasma
   - Similar to Windows 10
4. XFCE
   - Lightweight
   - Used by Kali Linux

---

### Which Desktop Environment is Best?

Speed depends on:

- Animations
- Graphics
- Quality
- File Extensions
- Window Manager

Example:

- i3 Window Manager

---

## Why Linux?

### Fast

- Does not require high-spec computers.

### Most Used

- Around **47%** of professional developers use Linux-based operating systems.
- Linux powers **39.2%** of websites whose operating system is known.
- Linux powers **85%** of smartphones (Android).
- Linux is the third most popular desktop operating system.
- The Linux market size is expected to reach **$15.64 billion by 2027**.
- The world's **Top 500 supercomputers** all run Linux.
- Around **96.3%** of the top one million web servers run Linux.
- Today there are **600+ active Linux distributions**.

### Other Reasons

- Most hacking tools support Linux.
- Highly secure.
- Open source.
- Lightweight.
- Highly customizable.

---

## Linux Distributions (Distros)

A **Distribution (Distro)** is a complete operating system built around the Linux Kernel.

A distribution includes:

- Linux Kernel
- GNU Packages
- Package Manager
- Desktop Environment (UI)

There are many Linux distributions.

### Debian Family

- Debian
  - Kali Linux
  - Ubuntu
  - Parrot OS

### Arch Family

- Arch Linux
  - BlackArch
  - Garuda

### Others

- Fedora
- Red Hat
- Gentoo
- Android

---

## Beginner-Friendly Distros

- Ubuntu
- Pop!_OS
- elementary OS
- Linux Mint
- Zorin OS
- Solus

---

## Intermediate Distros

- Garuda Linux
- EndeavourOS
- Manjaro
- MX Linux
- Fedora
- openSUSE

---

## Advanced Distros

- Arch Linux
- Gentoo
- Slackware
- Linux From Scratch (LFS)
- Qubes OS
- NixOS

---

## Which Linux Distribution is Best for Hackers?

### Kali Linux

Kali Linux is a Debian-based Linux distribution designed for:

- Digital Forensics
- Penetration Testing

Maintained by:

- Offensive Security

Desktop Environment: XFCE

Package Manager: apt

Shell: zsh

---

### Parrot OS

Parrot OS is a Debian-based Linux distribution focused on:

- Security
- Privacy
- Development

Desktop Environment: MATE

Package Manager: apt

Shell: bash

---

### Garuda Linux

Garuda Linux is based on Arch Linux.

Desktop Environment: KDE Plasma

Package Manager: pacman

Shell: fish

---

### Ubuntu

Desktop Environment: GNOME

Package Manager: apt

Shell: bash

---

## Do Windows Have Distros?

- Windows is **not open-source**, so people cannot freely modify and redistribute it.
- Therefore, Windows does not have distributions like Linux.
- Microsoft only releases updates and new versions.

---

# How Can We Use Linux?

## 1. Main OS (Main Boot)

Linux is installed as the only operating system.

### Advantages

- Better Performance
- Simple Setup
- More Secure

### Disadvantages

- No access to another operating system.
- Risk of data loss during installation.

---

## 2. Dual Boot (2-in-1)

Linux is installed alongside Windows (or another operating system).

### Advantages

- Access to multiple operating systems.
- Better hardware performance than virtual machines.

### Disadvantages

- Installation is more complex.
- Storage is shared.

---

## 3. Live Boot

Run Linux directly from a USB drive or DVD without installing it.

### Advantages

- Better privacy.
- No risk of data loss.
- No installation required.

### Disadvantages

- Shared system resources.
- Usually slower than an installed system.

---

## 4. Cloud Terminals

You can practice Linux online without installing it.

- https://www.webminal.org
- https://shell.cloud.google.com/?show=ide,terminal

---

## 5. Virtual Machine (VM)

Modern computers support **Virtualization**, allowing multiple operating systems to run on one computer.

### Types of Virtualization

### Type 1 Hypervisor (Bare-Metal)

Runs directly on physical hardware.

Examples:

- VMware ESXi
- Proxmox
- Xen

Advantages:

- High performance
- Better resource management
- Better isolation
- Common in enterprise environments

---

### Type 2 Hypervisor (Hosted)

Runs on top of an existing operating system.

Examples:

- VMware Workstation
- Oracle VirtualBox

Advantages:

- Easy to install
- Suitable for learning and development

---

## 6. WSL v2 (Windows Subsystem for Linux)

Allows Linux to run inside Windows.

### Installation

Open **Windows PowerShell (Run as Administrator)**

```powershell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

Or simply install **Ubuntu**, **Kali Linux**, or another Linux distribution from the **Microsoft Store**.

---

## 7. Termux (Android)

Termux is an Android application that provides a Linux terminal.

It is useful for:

- Running Linux commands
- Programming
- Learning Bash
- Practicing simple Linux tasks

---

@innovatorsemir