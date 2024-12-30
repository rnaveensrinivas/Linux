# Table of Contents
* [Introduction](#Introduction)
* [Linux Directory Structure](#Linux-Directory-Structure)
  * [Summary of Introduction](#Summary-of-Linux-Directory-Structure)
* [Command Line Interface](#Command-Line-Interface)
* [Basic Commands](#Basic-Commands)
  * [Summary of Basic Commands](#Summary-of-Basic-Commands)
* [Directories](#Directories)
  * [Summary of Directory Commands](#Summary-of-Directory-Commands)
* [Viewing File and Directory Details](#Viewing-File-and-Directory-Details)
  * [Summary of Permissions Commands](#Summary-of-Permissions-Commands)
  * [Summary of Viewing files](#Summary-of-Viewing-files)
* [Permissions](#Permissions)
* [Viewing and Editing Files](#Viewing-and-Editing-Files)
  * [Summary of Vim Commands](#Summary-of-Vim-Commands)
* [Deleting, Moving, and Renaming Files and Directories](#deleting-moving-and-renaming-files-and-directories)
  * [Summary of Deleting, Moving, and Renaming Files and Directories Commands](#Summary-of-Deleting-Moving-and-Renaming-Files-and-Directories-Commands)
* [Finding, Sorting, and Comparing Files and Directories](#finding-sorting-and-comparing-files-and-directories)
  * [Summary of Finding, Sorting, and Comparing Files and Directories](#Summary-of-Finding-Sorting-and-Comparing-Files-and-Directories)
* [I/O Redirection](#io-redirection)
  * [Summary of I/O Redirection Commands](#Summary-of-IO-Redirection-Commands)
* [Additional Command Line Concepts](#Additional-Command-Line-Concepts)
  * [Summary of Additional Command Line Concept Commands](#Summary-of-Additional-Command-Line-Concept-Commands)
* [Processes and Jobs](#Processes-and-Jobs)
  * [Summary of Process and Job Control Commands](#Summary-of-Process-and-Job-Control-Commands)
* [Switching Users](#Switching-Users)
  * [Summary of Switching User Commands](#Summary-of-Switching-User-Commands)
* [Installing Software](#Installing-Software)
  * [Summary of Installing Software Commands](#Summary-of-Installing-Software-Commands)

# Introduction

## What is Linux?
Linux is a **Unix-like open-source operating system** renowned for its flexibility, security, and extensive community support. At its core is the **Linux kernel**, a fundamental component that bridges the gap between applications and hardware. The kernel manages system resources, ensures hardware-software communication, and provides essential services like memory management and process control.

Key characteristics of Linux:
- **Unix-like**: Shares architectural and conceptual similarities with Unix.
- **Open Source**: Freely available for use, modification, and distribution.
- **Kernel-Centric**: The kernel serves as the operating system's foundation.

---

## Linux Distributions
A **Linux distribution (distro)** is a complete operating system built around the Linux kernel. It bundles essential software, tools, and utilities tailored for various purposes, creating a cohesive and usable environment.

### Features of Linux Distributions:
1. **Shared Core**: The Linux kernel is consistent across distributions.
2. **Custom Software**: Each distribution includes different default software, tools, and configurations based on its focus.
3. **Versatile Applications**: Applicable to desktops, servers, and specialized systems.
4. **Community vs. Corporate**: Some distributions are maintained by volunteers, while others are backed by companies offering paid support.
5. **Desktop vs. Server**: Some distribution are exclusive for PC, Linux Desktops, eg. Linux Mint. While others are exclusive for Servers, eg. CentOS, RHEL. And some distro serves both Desktop and Server users, eg. Ubuntu..

### Popular Linux Distributions  

This table categorizes popular Linux distributions based on their primary usage (Desktop vs. Server) and support model (Community vs. Corporate).  

| **Distribution**        | **Primary Usage** | **Support Model** | **Notes**                                                                 |
|--------------------------|-------------------|-------------------|---------------------------------------------------------------------------|
| **Linux Mint**           | Desktop           | Community         | User-friendly, great for beginners.                                       |
| **Ubuntu**               | Both              | Community         | Widely used, offers LTS versions for stability.                           |
| **Debian**               | Both              | Community         | Stable and reliable, widely used for servers.                             |
| **Fedora**               | Both              | Community         | Cutting-edge features, upstream for RHEL.                                 |
| **openSUSE**             | Both              | Community/Corporate | Offers both Leap (stable) and Tumbleweed (rolling release) versions.     |
| **Arch Linux**           | Desktop           | Community         | Minimalist and highly customizable.                                       |
| **CentOS**               | Server            | Community         | RHEL-based, stable, and enterprise-ready.                                 |
| **Red Hat Enterprise Linux (RHEL)** | Server            | Corporate         | Commercial support for enterprise environments.                           |
| **Manjaro**              | Desktop           | Community         | Arch-based with user-friendly tools.                                      |
| **Elementary OS**        | Desktop           | Community         | Aesthetically pleasing, great for newcomers.                              |
| **Kali Linux**           | Desktop           | Community         | Specialized for penetration testing and security tasks.                   |
| **Zorin OS**             | Desktop           | Community         | Aimed at users transitioning from Windows.                                |
| **Pop!_OS**              | Desktop           | Community         | Developer and gamer-friendly, based on Ubuntu.                           |
| **AlmaLinux**            | Server            | Community         | RHEL clone, focused on enterprise users.                                  |
| **Slackware**            | Both              | Community         | Simple, traditional UNIX-like experience.                                 |
| **MX Linux**             | Desktop           | Community         | Lightweight, efficient, and great for older hardware.                     |
| **Deepin**               | Desktop           | Community         | Focuses on an elegant and intuitive desktop environment.                  |
| **Void Linux**           | Desktop           | Community         | Independent and minimalist, with a unique package manager (`xbps`).       |

**Legend**:  
- **Desktop**: Primarily tailored for personal or workstation use.  
- **Server**: Designed for stability, often used in enterprise or hosting environments.  
- **Community**: Developed and maintained by a community of volunteers.  
- **Corporate**: Backed by a company providing commercial support.  

---

### Why Learn Linux?
While the software bundled with each distribution varies, the **core principles and functionalities of Linux remain universal**. Mastering Linux concepts ensures you can adapt to any distribution and leverage its power effectively. Whether you are a system administrator, developer, or enthusiast, understanding Linux is a vital skill in today's technology-driven world.

---

# Linux Directory Structure

The Linux directory structure is hierarchical, resembling an inverted tree with the root (`/`) as its base. All directories branch off from the root, with forward slashes (`/`) separating directories.

**Directory** is nothing but a linux jargon for **folder**.

## Common Top-Level Directories

### `/` Root Directory
The starting point of the Linux file system. All files and directories reside under `/`. Additional storage devices are mounted as subdirectories like `/mnt` or `/media`.
```bash
$ ls /
bin                dev   lib64              mnt   run                 srv       usr
bin.usr-is-merged  etc   lib.usr-is-merged  opt   sbin                swap.img  var
boot               home  lost+found         proc  sbin.usr-is-merged  sys
cdrom              lib   media              root  snap                tmp
```

### `/bin` Binaries
Contains essential executable programs (e.g., basic commands like `ls`, `cp`). Additional non-essential binaries are found in `/usr/bin`.
```bash
$ ls /bin
'['                                   mpris-proxy
 aa-enabled                           mpstat
 aa-exec                              mscompress
 aa-features-abi                      msexpand
 aconnect                             mt
 acpidbg                              mt-gnu
 add-apt-repository                   mtr
 addpart                              mtrace
 addr2line                            mtr-
 ...
```

### `/etc` System Configuration Files
Houses configuration files for the system and applications (e.g., boot modes, nareetwork settings).
```bash
$ ls /etc
adduser.conf            fuse.conf             logrotate.d          rsyslog.d
alsa                    fwupd                 lsb-release          rygel.conf
alternatives            gai.conf              machine-id           sane.d
anacrontab              gdb                   magic                security
apache2                 gdm3                  magic.mime           selinux
apg.conf                geoclue               manpath.config       sensors3.conf
apm                     ghostscript           mime.types           sensors.d
apparmor                glvnd                 mke2fs.conf          services
apparmor.d              gnome                 ModemManager         sgml
apport                  gnome-remote-desktop  modprobe.d           shadow
apt                     gnutls                modules              shadow-
avahi                   gprofng.rc            modules-load.d       shells
bash.bashrc             groff                 mtab                 skel
bash_completion         group                 nanorc               snmp
bash_completion.d       group-                netconfig            speech-dispatcher
bindresvport.blacklist  grub.d                netplan              ssh
binfmt.d                gshadow               network              ssl
...
```

### `/home` Home Directories
User-specific directories containing personal files, configurations, and data. Example: `/home/user`.
```bash
$ ls /home/
sri
```

### `/opt` Optional or Third-Party Software
Used for software not bundled with the operating system, like Google Chrome.

**Fact** - Firefox comes builtin with the operating system. 
```bash
$ whereis firefox
firefox: /usr/bin/firefox /snap/bin/firefox
```

### `/tmp` Temporary Files
Temporary workspace for applications and users. Files here are cleared at boot time.
```bash
$ ls /tmp
snap-private-tmp
systemd-private-9e8bed51413f4d929422b8d7d854bbcd-bluetooth.service-rcvxLj
systemd-private-9e8bed51413f4d929422b8d7d854bbcd-colord.service-1fPQpU
systemd-private-9e8bed51413f4d929422b8d7d854bbcd-fwupd.service-RclrPC
systemd-private-9e8bed51413f4d929422b8d7d854bbcd-ModemManager.service-ItsVvS
...
```

### `/usr` User-Related Data
Contains user-related programs and **read-only data**. Subdirectories include:
- `/usr/bin`: Executable programs.
- `/usr/lib`: Libraries.
- `/usr/share`: Shared documentation and resources.

#### `/usr`
```bash
$ ls /usr
bin  games  include  lib  lib64  libexec  local  sbin  share  src
```
#### `/usr/bin`
```bash
$ ls /usr/bin
'['                                   mpris-proxy
 aa-enabled                           mpstat
 aa-exec                              mscompress
 aa-features-abi                      msexpand
 aconnect                             mt
 acpidbg                              mt-gnu
 add-apt-repository                   mtr
 addpart                              mtrace
 addr2line                            mtr-packet
 airscan-discover                     mv
 alsabat                              namei
 alsaloop                             nano
 ...
```
#### `/usr/lib`
```bash
$ ls /usr/lib
apg                        gvfs                                  pam.d
apparmor                   hdparm                                pcmciautils
apt                        init                                  pcrlock.d
aspell                     initramfs-tools                       pm-utils
bfd-plugins                ispell                                policykit-1
binfmt.d                   kernel                                polkit-1
brltty                     klibc                                 pppd
...
```
#### `/usr/share`
```bash
$ ls /usr/share/
accountsservice              gnome-tweaks                    pam-configs
aclocal                      gnupg                           perl
alsa                         groff                           perl5
alsa-base                    grub                            perl-openssl-defaults
alsa-card-profile            gst-plugins-base                pipewire
applications                 gstreamer-1.0                   pixmaps
apport                       gtk-3.0                         pkgconfig
appstream                    gtk-4.0                         plymouth
aspell                       gtk-engines                     pnm2ppa
avahi                        gtksourceview-2.0               pocketsphinx
backgrounds                  gtksourceview-3.0               polkit-1
base-files                   gtksourceview-4                 poppler
base-passwd                  gtksourceview-5                 ppd
bash-completion              gupnp-av                        ppdc
binfmts                      gupnp-dlna-2.0                  ppp
...
```
### What is the difference between `/bin` and `/usr/bin`?

The directories `/bin` and `/usr/bin` are part of the Linux filesystem hierarchy and are used to store executable files. However, they differ in purpose and historical usage.

---

#### **1. `/bin` (Essential User Binaries)**
- **Purpose**: Contains essential binaries required for the system to function, especially during boot or when the system is in single-user mode.
- **Availability**: These binaries are available even if the `/usr` directory is not mounted.
- **Usage**: Includes basic commands that are needed for system recovery, maintenance, and basic user interaction.
- **Examples**:
  - `ls`: List directory contents
  - `cp`: Copy files
  - `mv`: Move files
  - `cat`: Concatenate and display file contents
  - `bash`: The Bourne Again Shell
  
---

#### **2. `/usr/bin` (Non-Essential User Binaries)**
- **Purpose**: Contains binaries for general use by all users, but these are not essential for booting or repairing the system.
- **Availability**: Typically resides on a separate partition and may not be available if `/usr` is not mounted (e.g., during early boot stages or recovery modes).
- **Usage**: Includes a broader range of applications and tools that are not critical to the core system operation.
- **Examples**:
  - `vim`: Text editor
  - `gcc`: C compiler
  - `python`: Python interpreter
  - `git`: Version control system

---

#### **Key Differences**
| Aspect             | `/bin`                              | `/usr/bin`                          |
|--------------------|-------------------------------------|-------------------------------------|
| **Purpose**         | Essential commands for the system  | General-purpose commands and tools |
| **Availability**    | Always available, even in recovery | May not be available in early boot |
| **Examples**        | `ls`, `cat`, `bash`                | `vim`, `python`, `git`             |
| **System Dependence** | Required for booting and recovery | Not required for core boot         |

---

#### **Historical Context**
- In older UNIX systems, `/bin` was designed for essential commands, while `/usr/bin` held supplementary tools. Over time, `/usr/bin` grew to contain a significant portion of system utilities.
- Modern Linux systems often include `/bin` and `/usr/bin` as part of the same filesystem, and some distributions have unified these directories, symlinking `/bin` to `/usr/bin` for simplicity.


### `/var` Variable Data
Stores variable and runtime data, like log files in `/var/log`.

```bash
$ ls /var
backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  snap  spool  tmp
```
---

## Additional Important Directories
- `/boot`: Files required for system booting.
- `/dev`: Device files representing hardware.
- `/lib` and `/lib64`: Shared libraries.
- `/mnt` and `/media`: Mount points for external file systems or media.
- `/proc` and `/sys`: Virtual filesystems for process and system information.
- `/sbin`: System administration binaries.
- `/srv`: Data served by the system, e.g., web or FTP files.
- `/root`: Home directory for the root user.

---

## Application Directory Organizatoin Structure

Application directory structures can be organized similar to the operating system's layout. For example, when Apache is installed in `/usr/local`, its directories can look like:
- `/usr/local/apache/bin`: Binaries and executables
- `/usr/local/apache/etc`: Configuration files
- `/usr/local/apache/lib`: Libraries
- `/usr/local/apache/logs`: Log files

If installed in `/opt`, the structure is similar:
- `/opt/apache/bin`: Binaries
- `/opt/apache/etc`: Configurations
- `/opt/apache/lib`: Libraries
- `/opt/apache/logs`: Logs

Another common pattern is separating configuration and log data:
- `/etc/opt/apache`: Configuration files
- `/opt/apache/bin`: Binaries
- `/opt/apache/lib`: Libraries
- `/var/opt/apache`: Logs

Applications can also share common directory spaces. For instance, Apache might be installed in `/usr/local` along with other local applications.

## Summary of Linux Directory Structure

| **Directory**   | **Purpose**| **Key Contents**|
|------------------|-----------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| `/bin`           | Essential binaries for system operation and recovery.                      | Basic commands like `ls`, `cp`, `mv`, `cat`, `bash`.                                                     |
| `/boot`          | Contains bootloader files and the kernel.                                  | Kernel images, `grub` configuration files.                                                              |
| `/dev`           | Device files representing hardware and virtual devices.                    | Files like `/dev/sda` (disk), `/dev/null`, `/dev/tty` (terminals).                                       |
| `/etc`           | System-wide configuration files.                                           | Configs for services like `ssh`, `passwd`, `fstab`.                                                      |
| `/home`          | User home directories.                                                     | Personal files and directories for users (e.g., `/home/naveen`).                                         |
| `/lib`           | Essential shared libraries and kernel modules.                             | Libraries used by programs in `/bin` and `/sbin`.                                                       |
| `/media`         | Mount points for removable media.                                          | Subdirectories for CDs, USB drives (e.g., `/media/usb`).                                                |
| `/mnt`           | Temporary mount point for filesystems.                                     | Used for mounting partitions during maintenance or temporary usage.                                      |
| `/opt`           | Optional software packages installed outside standard directories.         | Third-party apps like `/opt/google`.                                                                    |
| `/proc`          | Virtual filesystem providing process and system information.               | Files like `/proc/cpuinfo`, `/proc/meminfo`.                                                            |
| `/root`          | Home directory for the root user.                                          | Files specific to the `root` superuser.                                                                 |
| `/run`           | Runtime files like process IDs (PIDs) and sockets.                        | Files such as `/run/sshd.pid`.                                                                          |
| `/sbin`          | System binaries for administrative tasks.                                  | Commands like `fsck`, `shutdown`, `mount`.                                                              |
| `/srv`           | Data served by the system, such as web server or FTP server files.         | E.g., `/srv/www` for websites.                                                                          |
| `/sys`           | Virtual filesystem for device and system configuration.                   | Hardware information and control files (e.g., `/sys/class`).                                            |
| `/tmp`           | Temporary files, often cleared on reboot.                                 | Session data, temporary downloads.                                                                      |
| `/usr`           | Secondary hierarchy for user programs and data.                           | Subdirectories like `/usr/bin`, `/usr/lib`, `/usr/share`.                                               |
| `/var`           | Variable data files that change during operation.                         | Logs (`/var/log`), spools (`/var/spool`), caches (`/var/cache`).                                         |

---

### Notes:
1. Some directories like `/media` or `/mnt` might not have content unless specifically used.
2. On modern systems, certain directories like `/bin` and `/sbin` may be symlinks to `/usr/bin` and `/usr/sbin`.
3. The layout and contents of these directories can vary slightly between Linux distributions.

---

# Command Line Interface

The **shell** is a program that accepts commands and directs the operating system to execute them. It serves as the interface between the user and the system. The **Command Line Interface (CLI)** is a text-based interface where users type commands.

## Shell and Interface Types
- **CLI (Text Interface)**: When connected to a Linux system, a shell is started, and the user interacts through the command line.
- **GUI (Graphical User Interface)**: When a Linux system is in graphical mode, users interact through a GUI. To access the CLI within a GUI, a terminal emulator (e.g., `xterm`, `GNOME Terminal`) must be used.

## Shell Prompt
The **shell prompt** provides information about the user, system, and current directory. For example:
```bash
jason@linuxsvr:~$
```
- `jason`: Username
- `linuxsvr`: Hostname
- `~`: Current directory (home directory, e.g., `/home/jason`)

The prompt can vary in format, and users can customize it. Special symbols like `~` refer to the user's home directory. For example, `~john` expands to `/home/john`.

## Examples of Shell Prompts:
- `[jason@linuxsvr /tmp]$`
- `linuxsvr:/home/jason>`
- `jason@linuxsvr:~>`

Shell prompts can also span multiple lines, showing additional information like time and session details. 

---

# Basic Commands

In Linux, commands are **case-sensitive** and typically in lowercase. Items surrounded by square brackets are optional. 

## Navigation Commands:
- **pwd**: Displays the present working directory.
  ```bash
  $ pwd
  /home/jason
  ```
- **cd [directory]**: Changes the current directory to the specified directory. Without an argument, it changes to the home directory.
  ```bash
  $ cd /home
  $ pwd
  /home
  ```
* Going to home directory using cd
  ```bash
  sri@envy:~
  $ cd ~

  sri@envy:~
  $ cd ~sri
  
  sri@envy:~
  $ cd /home/sri
  
  sri@envy:~
  $ cd
  
  sri@envy:~
  $
  ```

## Listing and Viewing Files:
- **ls**: Lists the contents of a directory.
  ```bash
  $ ls
  Desktop Documents Downloads Music Pictures to-do.txt
  ```
- **cat [file]**: Displays the contents of a file.
  ```bash
  $ cat to-do.txt
  This file contains my to-do list.
  * Mow the lawn.
  * Take over the world.
  ```

## Exiting the Shell:
- **exit**, **logout**, or **Ctrl-D**: Exits the shell or current session.
  ```bash
  $ exit
  ```
  ```bash
  $ logout 
  bash: logout: not login shell: use `exit'
  ```
  ```bash
  $ ^D
  ```


## Command Line Help:
Linux provides built-in documentation through **man** pages:
- **man [command]**: Displays the manual page for a command.
  ```bash
  $ man ls
  ```
- **man -k [keyword]**: Searches for commands related to a keyword.
  ```bash
  $ man -k reboot # returns all the man files which contain word 'reboot'
  grub-reboot (8)      - set the default boot entry for GRUB, for the next boot only
  halt (8)             - Power off, reboot, or halt the machine
  poweroff (8)         - Power off, reboot, or halt the machine
  reboot (2)           - reboot or enable/disable Ctrl-Alt-Del
  reboot (8)           - Power off, reboot, or halt the machine
  shutdown (8)         - Halt, power off or reboot the machine
  systemd-pcrlock-secureboot-authority.service (8) - Analyze and predict TPM2 PCR states and ...
  systemd-pcrlock-secureboot-policy.service (8) - Analyze and predict TPM2 PCR states and gen...
  systemd-reboot.service (8) - System shutdown logic
  systemd-soft-reboot.service (8) - Userspace reboot operation
  systemd-sysupdate-reboot.service (8) - Automatically Update OS or Other Resources
  systemd-sysupdate-reboot.timer (8) - Automatically Update OS or Other Resources
  ```
- **[command] --help**: Displays a help message for a command.
  ```bash
  $ ls --help
  $ cd --help
  ```

## Exploring Commands:
You can explore commands in directories like `/bin` and `/usr/bin` using `ls` and `man` to learn their functions.
```bash
$ cd /bin
$ ls
awk diff cal cat cp date du echo grep groups less more
$ man date
```
### Clearing the terminal screen.
Screen can be cleared using 
1. `clear` command
2. `CTRL + l` shortcut
   
#### 1. `clear` command
The below command clears the entire terminal. Gives a fresh terminal.
```bash
$ clear
```
#### 2. `CTRL + l` Shortcut
This doesn't doesn't clear the terminal, but clears the Window. If you scroll up you can see the previous commands. 
```bash
$ ^l
```
---

### Creating files
To create an empty files use `touch`
```bash
touch file[s]
```
---

## Summary of Basic Commands

| **Command**        | **Description**                                                   | **Example Output**                                                                  |
|---------------------|-------------------------------------------------------------------|-------------------------------------------------------------------------------------|
| **pwd**            | Displays the present working directory.                          | `/home/jason`                                                                       |
| **cd [directory]** | Changes the current directory to the specified directory.        | Changes to `/home` if `cd /home` is used.                                           |
| **ls**             | Lists the contents of a directory.                               | `Desktop Documents Downloads Music Pictures to-do.txt`                              |
| **cat [file]**     | Displays the contents of a file.                                 | Displays contents of `to-do.txt` like "Mow the lawn, Take over the world."          |
| **exit**           | Exits the shell or current session.                              | Logs out or ends the session.                                                       |
| **CTRL + d**       | Shortcut to log out of the shell or end the current input.       | Ends the terminal session if pressed at the command line.                           |
| **man [command]**  | Displays the manual (help) page for a command.                   | Shows documentation for `ls` or other commands.                                     |
| **man -k [keyword]**| Searches for a keyword in all man pages.                        | Lists all man pages related to "reboot" or other keywords.                          |
| **[command] --help**| Displays a help message for a command.                          | `ls --help` shows options for the `ls` command.                                     |
| **clear**          | Clears the terminal screen.                                      | Clears terminal output for a fresh screen.                                          |
| **CTRL + l**       | Clears the terminal window without erasing previous output.      | Scroll up to see previous commands after using this shortcut.                       |
| **touch [file]**   | Creates a new empty file or updates the timestamp of an existing file. | Creates `newfile.txt` or updates its timestamp.                                     |

---

# Directories
In linux, we call **folder** as **directory**.

## Absolute vs Relative Paths
### **Absolute Path**: 
Starts with a `/` and points to a location from the root of the file system.
```bash
$ cd /home/jason/Music   # Absolute path to the Music directory
```

### **Relative Path**: 
Doesn't start with a `/` and is relative to the current working directory.
```bash
$ cd Music   # Relative path, assuming you are already in /home/jason
```

## Home Directory
There are many ways to go to user's home directory from anywhere. 
```bash
sri@envy:~
$ cd ~

sri@envy:~
$ cd ~sri

sri@envy:~
$ cd /home/sri

sri@envy:~
$ cd

sri@envy:~
$
```

## Special Directory References
- `.` represents the **current directory**.
  ```bash
  $ cd .   # Stays in the current directory
  ```

- `..` represents the **parent directory**.
  ```bash
  $ cd ..   # Moves up one level to the parent directory
  ```

## Navigating Directories
### **Change directories using `cd`**: 
```bash
$ cd ~/Music   # Changes to the Music directory
$ pwd        # Shows the current directory, which should now be /home/sri/Music
/home/sri/Music
```

### **Return to the previous directory with `cd -`**:
```bash
$ cd /home/jason/Music   # Change to Music
$ cd -   # Goes back to the previous directory
```

## Creating and Removing Directories
### **Create a directory with `mkdir`**:
```bash
$ mkdir newdir   # Creates a new directory called newdir
```

### **Create directories with `mkdir -p`** (including intermediate directories):
```bash
$ mkdir -p newdir/one/two   # Creates newdir, then one, and then two inside it
```

### **Remove an empty directory with `rmdir`**:
```bash
$ rmdir newdir   # Removes the empty directory newdir
```

### **Forcefully remove a directory and its contents with `rm -rf`**:
```bash
$ rm -rf newdir   # Deletes the newdir directory and all of its contents
```

## Summary of Directory Commands

| **Command**          | **Description**                                                             | **Example Usage**                                  |
|-----------------------|-----------------------------------------------------------------------------|----------------------------------------------------|
| `pwd`                | Prints the current working directory.                                      | `pwd`                                              |
| `cd [directory]`     | Changes the current directory to the specified one.                        | `cd /home/jason`                                   |
| `cd ..`              | Moves up one directory level (to the parent directory).                    | `cd ..`                                            |
| `cd -`               | Returns to the previous working directory.                                 | `cd -`                                             |
| `cd`               | Changes to the home directory of the current user.                        | `cd`                                             |
| `cd ~`               | Changes to the home directory of the current user.                        | `cd ~`                                             |
| `cd ~[username]`     | Changes to the home directory of the specified user.                      | `cd ~sri`                                          |
| `mkdir [directory]`  | Creates a new directory.                                                   | `mkdir newdir`                                     |
| `mkdir -p [dir]`     | Creates a directory and any necessary parent directories.                  | `mkdir -p newdir/one/two`                         |
| `rmdir [directory]`  | Removes an empty directory.                                                | `rmdir newdir`                                     |
| `rm -rf [directory]` | Recursively and forcefully removes a directory and its contents.           | `rm -rf newdir`                                    |
| `.`                  | Represents the current directory.                                          | `cd .`                                             |
| `..`                 | Represents the parent directory.                                           | `cd ..`                                            |
| `/`                  | Root directory (absolute path starts here).                               | `cd /home/jason`                                   |
| `~`                  | Shortcut for the home directory.                                           | `cd ~/Music`                                       |

---

# Viewing File and Directory Details

In Linux, the `ls` command is used to list files and directories, but it can also provide detailed information about them when combined with different options. 

## Basic `ls` Command

The `ls` command by itself will simply list the files and directories in the current directory:
```bash
$ ls
Desktop  Documents  Downloads  Music  to-do.txt
```

## Using `ls -l` for Detailed Listings

The `-l` option provides a long listing format that gives detailed information about each file or directory. Here's an example:

```bash
$ ls -l
total 20
drwxrwxr-x 2 jason users 4096 May 3 08:33 Desktop
drwxrwxr-x 2 jason users 4096 May 3 08:35 Documents
drwxrwxr-x 2 jason users 4096 May 3 08:38 Downloads
drwxrwxr-x 3 jason users 4096 Jun 21 21:16 Music
-rw-r--r-- 1 jason users 73 Jun 22 19:34 to-do.txt
```

### Breakdown of the Output

The detailed output from `ls -l` is split into several columns:
- **Permissions**: The first column indicates the file's permissions.
- **Number of Links**: The second column shows how many links point to the file.
- **Owner**: The third column shows the owner of the file.
- **Group**: The fourth column shows the group associated with the file.
- **File Size**: The fifth column shows the size of the file in bytes.
- **Modification Time**: The sixth column displays the last modification date and time.
- **File/Directory Name**: The final column shows the name of the file or directory.

### Example Breakdown
```bash
-rw-r--r-- 1 sri users 73 Jun 22 19:34 to-do.txt
```
- `-rw-r--r--`: File permissions
- `1`: Number of links
- `sri`: Owner of the file
- `users`: Group associated with the file
- `73`: Size in bytes
- `Jun 22 19:34`: Modification date and time
- `to-do.txt`: Name of the file

## Displaying Hidden Files

By default, `ls` does not show hidden files (files that begin with a dot `.`). To display hidden files, use the `-a` option:
```bash
$ ls -a
.                 .cache      .gnupg    Public                     .vim
..                .config     .lesshst  .python_history            .viminfo
.aspell.en.prepl  Desktop     .local    snap                       .vimrc
.aspell.en.pws    Documents   Music     .ssh                       .vscode
.bash_history     .dotnet     Pictures  .sudo_as_admin_successful
.bash_logout      Downloads   .pki      Templates
.bashrc           .gitconfig  .profile  Videos
```
To list hidden files with details, use both the `-a` and `-l` options:
```bash
$ ls -a -l # or -al
total 160
drwxr-x--- 20 sri  sri   4096 Dec 30 11:38 .
drwxr-xr-x  3 root root  4096 Dec 28 16:16 ..
-rw-rw-r--  1 sri  sri     24 Dec 23 13:01 .aspell.en.prepl
-rw-rw-r--  1 sri  sri    108 Dec 23 13:01 .aspell.en.pws
-rw-------  1 sri  sri  20019 Dec 30 11:37 .bash_history
-rw-r--r--  1 sri  sri    220 Mar 31  2024 .bash_logout
-rw-r--r--  1 sri  sri   4316 Dec 29 18:48 .bashrc
drwx------ 19 sri  sri   4096 Dec 25 20:21 .cache
drwx------ 21 sri  sri   4096 Dec 25 16:17 .config
drwxr-xr-x  2 sri  sri   4096 Dec 29 20:45 Desktop
drwxr-xr-x 13 sri  sri   4096 Dec 29 18:04 Documents
drwxrwxr-x  3 sri  sri   4096 Dec 21 17:15 .dotnet
drwxr-xr-x  2 sri  sri   4096 Dec 29 18:02 Downloads
-rw-rw-r--  1 sri  sri    152 Dec 21 17:40 .gitconfig
drwx------  2 sri  sri   4096 Dec 30 11:37 .gnupg
-rw-------  1 sri  sri     63 Dec 30 11:38 .lesshst
drwx------  4 sri  sri   4096 Dec 21 16:45 .local
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Music
drwxr-xr-x  3 sri  sri   4096 Dec 23 15:41 Pictures
drwx------  3 sri  sri   4096 Dec 21 17:15 .pki
-rw-r--r--  1 sri  sri    807 Mar 31  2024 .profile
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Public
-rw-------  1 sri  sri    242 Dec 30 06:31 .python_history
drwx------  7 sri  sri   4096 Dec 25 16:08 snap
drwx------  2 sri  sri   4096 Dec 21 17:29 .ssh
-rw-r--r--  1 sri  sri      0 Dec 21 16:45 .sudo_as_admin_successful
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Templates
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Videos
drwxr-xr-x  2 sri  sri   4096 Dec 27 20:42 .vim
-rw-------  1 sri  sri  14258 Dec 29 19:37 .viminfo
-rw-rw-r--  1 sri  sri   1260 Dec 26 10:43 .vimrc
drwxrwxr-x  4 sri  sri   4096 Dec 21 17:15 .vscode
```
This will display all files, including hidden ones, in a long listing format.

## File Type Indicators with `-F`

The `-F` option appends a symbol to each file or directory to indicate its type. Here's how it works:
```bash
$ ls -aF
./                .cache/     .gnupg/    Public/                    .vim/
../               .config/    .lesshst   .python_history            .viminfo
.aspell.en.prepl  Desktop/    .local/    snap/                      .vimrc
.aspell.en.pws    Documents/  Music/     .ssh/                      .vscode/
.bash_history     .dotnet/    Pictures/  .sudo_as_admin_successful
.bash_logout      Downloads/  .pki/      Templates/
.bashrc           .gitconfig  .profile   Videos/
```
- `/` indicates a **directory**.
- `@` indicates a **symbolic link**.
- `*` indicates an **executable** file.
- `|` indicates a **named pipe**.
- `=` indicates a **socket**.

For a long listing with file type indicators:
```bash
$ ls -lF
total 36
drwxr-xr-x  2 sri sri 4096 Dec 29 20:45 Desktop/
drwxr-xr-x 13 sri sri 4096 Dec 29 18:04 Documents/
drwxr-xr-x  2 sri sri 4096 Dec 29 18:02 Downloads/
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Music/
drwxr-xr-x  3 sri sri 4096 Dec 23 15:41 Pictures/
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Public/
drwx------  7 sri sri 4096 Dec 25 16:08 snap/
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Templates/
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Videos/
```

### Example File Type Indicators
| File Type | Symbol |
|-----------|--------|
| Directory | `/`    |
| Symlink   | `@`    |
| Executable | `*`    |
| Socket    | `=`    |
| Named pipe| `\|`    |

## Symbolic Links

A symbolic link (symlink) is a file that points to another file or directory. For example:
```bash
$ ls -l link-to-to-do
lrwxrwxrwx 1 jason users 9 Jun 22 21:01 link-to-to-do -> to-do.txt
```
Here, `link-to-to-do` is a symlink pointing to `to-do.txt`.

## Sorting Files by Time

To list files sorted by their modification time, use the `-t` option:
```bash
$ ls -t
Desktop  Documents  Downloads  snap  Pictures  Music  Public  Templates  Videos

$ ls -lt
total 36
drwxr-xr-x  2 sri sri 4096 Dec 29 20:45 Desktop
drwxr-xr-x 13 sri sri 4096 Dec 29 18:04 Documents
drwxr-xr-x  2 sri sri 4096 Dec 29 18:02 Downloads
drwx------  7 sri sri 4096 Dec 25 16:08 snap
drwxr-xr-x  3 sri sri 4096 Dec 23 15:41 Pictures
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Music
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Public
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Templates
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Videos
```
To reverse the order (show the oldest files first), use `-r`:
```bash
$ ls -ltr
total 36
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Videos
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Templates
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Public
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Music
drwxr-xr-x  3 sri sri 4096 Dec 23 15:41 Pictures
drwx------  7 sri sri 4096 Dec 25 16:08 snap
drwxr-xr-x  2 sri sri 4096 Dec 29 18:02 Downloads
drwxr-xr-x 13 sri sri 4096 Dec 29 18:04 Documents
drwxr-xr-x  2 sri sri 4096 Dec 29 20:45 Desktop
```

## Recursive Listing with `-R`

To list all files and directories recursively, use the `-R` option:
```bash
$ ls -R
.:
Desktop  Documents  Downloads  link-to-to-do  Music  program  to-do.txt

./Desktop:
...

./Documents:
cat.jpg  report.txt

./Downloads:
...

./Music:
JohnColtrane

./Music/JohnColtrane:
giant-steps.mp3
```

## Tree Command for Visual Directory Structure

The `tree` command provides a more visually appealing way to view directory structures. 

`tree` is not installed by default: 
```bash
$ sudo apt install tree
```

You can use it as follows:
```bash
$ tree
.
|-- Desktop
|-- Documents
|   |-- cat.jpg
|   |-- report.txt
|-- Downloads
|-- Music
|   |-- JohnColtrane
|   |-- giant-steps.mp3
|-- program
|-- to-do.txt
5 directories, 6 files
```

For only directories, use `-d`:
```bash
$ tree -d
.
|-- Desktop
|-- Documents
|-- Downloads
|-- Music
|-- JohnColtrane
5 directories
```

To colorize the output, use `-C` (by deafult this option is used):
```bash
$ tree -C
```

## Working with Directories Using `-d`

If you want to list the **directory itself** (without showing its contents), use the `-d` option:
```bash
$ ls -d Music/
Music/
```

For a long listing of the directory:
```bash
$ ls -ld Music/
drwxrwxr-x 3 jason users 4096 Jun 21 21:16 Music/
```

## Colorized Output with `--color`

To add color to the `ls` output, use the `--color` option. This is present by default. This helps differentiate file types:
```bash
$ ls --color
Desktop  Documents  Downloads  link-to-to-do  Music  program  to-do.txt
```

## Escaping Special Characters in Filenames

Files or directories with spaces or special characters in their names require special handling. You can either use quotes or escape the characters with a backslash (`\ ` - escapes the whitespace).

### Example with Spaces:
```bash
$ ls "my to do list"
-rw-r--r-- 1 jason users 73 Jun 22 22:16 my to do list

$ ls my\ to\ do\ list
-rw-r--r-- 1 jason users 73 Jun 22 22:16 my to do list
```

### Using `-b` to View Escaped Names:
```bash
$ ls -b
-rw-r--r-- 1 jason users 73 Jun 22 22:16 my\ to\ do\ list
```

## Summary of File and Directory Commands

| **Command**                     | **Description**                                                                 |
|----------------------------------|---------------------------------------------------------------------------------|
| `ls`                             | Lists the contents of a directory.                                                |
| `ls -l`                          | Lists files and directories with detailed information (long format).             |
| `ls -a`                          | Lists all files, including hidden files (files starting with a dot).             |
| `ls -al` or `ls -a -l`           | Combines `-a` and `-l` options to list all files with detailed information.      |
| `ls -F`                          | Appends a character to file names to indicate the file type (`/` for directories, `*` for executables). |
| `ls -t`                          | Sorts files by modification time, with the most recent first.                    |
| `ls -r`                          | Reverses the order of the output (e.g., reverse alphabetical order).             |
| `ls -R`                          | Lists directories and their contents recursively.                                |
| `tree`                           | Displays a tree structure of directories and their contents.                     |
| `tree -d`                        | Displays a tree structure showing only directories, not files.                   |
| `tree -C`                        | Displays a tree structure with color coding for different file types.            |
| `ls -d`                          | Lists directories themselves, not their contents.                                |
| `ls --color`                     | Displays directory contents with color coding.                                  |
| `ls "file name with space.txt"`  | Lists a file with spaces in its name, using quotes around the file name.         |
| `ls file\ name\ with\ space.txt` | Lists a file with spaces in its name, escaping the spaces with backslashes.      |
| `ls -b`                          | Prints filenames with non-printing characters (e.g., spaces) escaped with backslashes. |


# Permissions 

## Understanding File Types

The `ls -l` command displays long listings of files and directories, including the file types. The first character of the permission string indicates the file type. Here are the common file types:

| **Symbol** | **File Type**       |
|------------|---------------------|
| `-`        | Regular file        |
| `b`        | Block special file  |
| `c`        | Character special file |
| `d`        | Directory           |
| `l`        | Symbolic link       |
| `p`        | FIFO (named pipe)   |
| `s`        | Socket              |
| `?`        | Unknown file type   |

### Example:

```bash
$ ls -l sales.data
-rw-r--r-- 1 jason users 10400 Jun 14 09:31 sales.data
```

In this example:
- The first character `-` indicates that `sales.data` is a regular file.
- The rest of the string shows the permissions and file metadata.

## File Permissions

Permissions are represented by three symbols: **read (`r`)**, **write (`w`)**, and **execute (`x`)**. Each permission grants specific abilities over files and directories.

| **Symbol** | **Permission** |
|------------|----------------|
| `r`        | Read           |
| `w`        | Write          |
| `x`        | Execute        |

### File Permissions

For files, the meanings of these permissions are straightforward:
- **Read** (`r`): Allows viewing the file's contents.
- **Write** (`w`): Allows modifying the file.
- **Execute** (`x`): Allows running the file as a program.

### Directory Permissions

For directories, the meanings differ slightly:
- **Read** (`r`): Allows viewing the names of files in the directory.
- **Write** (`w`): Allows modifying the directory's contents (creating, renaming, or deleting files).
- **Execute** (`x`): Allows entering the directory (`cd` command).

### Example:

```bash
$ ls -l /home/jason
drwxr-xr-x 2 jason users 4096 Jan 10 10:21 Documents
```

In this case:
- `drwxr-xr-x`: Indicates a directory (`d` at the beginning).
- The permissions `rwxr-xr-x` mean that the owner (`jason`) can read, write, and execute; the group (`users`) can read and execute, but not write; others can also read and execute but cannot write.

## User Categories for Permissions

Linux uses three categories for managing file ownership and permissions:
1. **User** (`u`): The file owner.
2. **Group** (`g`): The group associated with the file.
3. **Other** (`o`): All other users.
4. **All** (`a`): Refers to all three categories (`u`, `g`, and `o`).

When modifying file permissions, these categories are referenced to define who gets which permission.

| **Symbol** | **Category** |
|------------|--------------|
| `u`        | User         |
| `g`        | Group        |
| `o`        | Other        |
| `a`        | All          |

### Example:

```bash
$ ls -l sales.data
-rw-r--r-- 1 jason users 10400 Jun 14 09:31 sales.data
```

Here:
- **User** (`jason`) is the file owner.
- **Group** (`users`) is the group owner.
- **Others** are anyone else who is not the owner or part of the group.

### Viewing Group Memberships

To see which groups you belong to, you can run the following commands:

```bash
$ groups
$ id -Gn
```

For another user:

```bash
$ groups [username]
```

These commands display the groups the user belongs to, which help in determining the permissions granted to each user category.

## Changing Permissions

Linux provides the `chmod` command to modify file permissions. Permissions can be changed either using symbolic or numeric (octal) modes.

### Symbolic Mode:

In symbolic mode, you can assign or remove permissions using the following syntax:

```bash
chmod [user][operation][permissions] [file]
```

Where:
- `[user]` is one of `u` (user), `g` (group), or `o` (others).
- `[operation]` is either `+` (add), `-` (remove), or `=` (set exactly).
- `[permissions]` are `r`, `w`, `x`.

#### Examples:
- Add execute permission for the user:
  ```bash
  chmod u+x myscript.sh
  ```
- Remove write permission for the group:
  ```bash
  chmod g-w myscript.sh
  ```
- Set read-only permission for others:
  ```bash
  chmod o=r file.txt
  ```

### Numeric Mode:

In numeric (octal) mode, permissions are represented by three digits. Each digit is a sum of the permissions for user, group, and others:
- `r = 4`
- `w = 2`
- `x = 1`

#### Permissions Table:

| **Permission** | **Numeric Value** |
|----------------|-------------------|
| `rwx`          | 7                 |
| `rw-`          | 6                 |
| `r-x`          | 5                 |
| `r--`          | 4                 |
| `-wx`          | 3                 |
| `-w-`          | 2                 |
| `--x`          | 1                 |
| `---`          | 0                 |

#### Examples:
- Give the user full permissions, and the group and others read-only:
  ```bash
  chmod 744 myfile.txt
  ```
- Give the user read and write permissions, and the group and others no permissions:
  ```bash
  chmod 600 myfile.txt
  ```



## Decoding Permissions and Changing Modes

### Understanding File Permission Strings

In Linux, file permissions are displayed using the `ls -l` command, and they follow a specific format that helps you understand the file's type, owner, group, and access permissions. The format of a permissions string looks like this:

```
-rw-r--r-- 1 jason users 10400 Jun 14 09:31 sales.data
```

#### Breaking Down the Permissions String:

1. **File Type**: The first character indicates the type of file.
   - `-`: Regular file
   - `d`: Directory
   - `l`: Symbolic link
   - `b`: Block special file
   - `c`: Character special file
   - `p`: FIFO (named pipe)
   - `s`: Socket
   - `?`: Unknown file type

   Example: `-rw-r--r--` means it's a regular file.

2. **User (Owner) Permissions**: The next three characters show the permissions for the file's owner (user).
   - `r`: Read permission
   - `w`: Write permission
   - `x`: Execute permission
   - `-`: Permission is not granted

   Example: `rw-` means the owner can read and write, but cannot execute.

3. **Group Permissions**: The next three characters represent the permissions for the group.
   - Example: `r--` means the group can read the file, but cannot write or execute.

4. **Others Permissions**: The last three characters represent the permissions for all others.
   - Example: `r--` means others can read the file, but cannot write or execute.

#### Example Breakdown:
```
$ ls -l sales.data
-rw-r--r-- 1 jason users 10400 Jun 14 09:31 sales.data
```

- **File type**: `-` (regular file)
- **User (Owner)**: `rw-` (read and write)
- **Group**: `r--` (read only)
- **Others**: `r--` (read only)
- **Owner**: `jason`
- **Group**: `users`

If there are extra symbols like a period (`.`) or plus sign (`+`) at the end of the string, it means that advanced access control methods (SELinux or ACLs) are in use, which are rarely seen in typical systems.

#### Example with SELinux:
```
-rw-r--r--. 1 jason users 10400 Jun 14 09:31 sales.data
```

- **Trailing period (`.`)** indicates the use of SELinux security contexts.

### Changing File Permissions

Permissions in Linux can be modified using the `chmod` (change mode) command. There are two primary ways to specify permissions: **symbolic mode** and **numeric mode**. This section focuses on symbolic mode.

#### Symbolic Mode Syntax:

```
chmod user_category operator permission file
```

Where:
- **user_category**: Specifies who the permission applies to:
  - `u`: User (Owner)
  - `g`: Group
  - `o`: Others
  - `a`: All (user, group, and others)
  
- **operator**: Defines the change to apply:
  - `+`: Add permission
  - `-`: Remove permission
  - `=`: Set permission explicitly (overwrite existing)

- **permission**: The permission being set:
  - `r`: Read
  - `w`: Write
  - `x`: Execute

#### Examples:

1. **Add Write Permission to Group**:
   ```
   chmod g+w sales.data
   ```
   This adds write permission for the group. The permissions string changes from:
   ```
   -rw-r--r--  to  -rw-rw-r-- 
   ```
   Now the group has both read and write permissions.

2. **Remove Write Permission from Group**:
   ```
   chmod g-w sales.data
   ```
   This removes the write permission for the group. The permissions string changes from:
   ```
   -rw-rw-r--  to  -rw-r--r-- 
   ```

3. **Add Execute Permission to Group and Others**:
   ```
   chmod go+x sales.data
   ```
   This command adds execute permission for both the group and others. The permissions string changes from:
   ```
   -rw-r--r--  to  -rw-r--r-x 
   ```

4. **Set Permissions for User and Group**:
   ```
   chmod ug+wx sales.data
   ```
   This adds both write and execute permissions for the user and group. If the user already had write permission, only execute permissions are added. The permissions string changes from:
   ```
   -rw-r--r--  to  -rwxrwxr-- 
   ```

5. **Set Permissions Explicitly for User, Group, and Others**:
   ```
   chmod u=rwx,g+x,a=r file.txt
   ```
   This sets the permissions as follows:
   - **User**: rwx (read, write, execute)
   - **Group**: +x (execute)
   - **Others**: =r (read only)

   Resulting permissions string:
   ```
   -rwxr-xr--  (User: rwx, Group: rx, Others: r)
   ```

6. **Set Read-Only Permissions for Everyone**:
   ```
   chmod a=r file.txt
   ```
   This sets read-only permissions for everyone (user, group, and others). Any write or execute permissions will be removed. The permissions string changes from:
   ```
   -rw-r--r--  to  -r--r--r-- 
   ```

7. **Removing All Permissions for Others**:
   ```
   chmod o-rwx file.txt
   ```
   This removes all permissions (read, write, execute) for others, resulting in the following permissions:
   ```
   -rw-r--r--  to  -rw-------
   ```

#### Advanced Permissions Modifications:

- **Multiple Changes in One Command**:
  You can modify permissions for different categories simultaneously. For example:
  ```
  chmod u+x,g-w,o=r file.txt
  ```
  This command adds execute permission for the user, removes write permission for the group, and sets read-only permission for others. The resulting permissions string will look like:
  ```
  -rwxr--r-- 
  ```

- **Explicit Permission Setting**:
  The equal sign (`=`) can be used to overwrite existing permissions for a user category:
  ```
  chmod u=rwx file.txt
  ```
  This sets the user’s permissions to read, write, and execute, overriding any existing permissions for the user category. The resulting permissions string will look like:
  ```
  -rwxr--r-- 
  ```

## Numeric Based Permissions

In Linux, file permissions can be specified using either symbolic mode or octal (numeric) mode. While symbolic mode is more readable, numeric mode is often faster and more efficient for experienced users. Numeric mode uses octal (base-10) representation to specify file permissions based on the binary values for read, write, and execute permissions.

### Octal Mode (Numeric Mode) Overview

In numeric mode, each file permission is represented by a three-digit octal (base-10) number. These digits correspond to read, write, and execute permissions. The binary representation for each permission type is:

- **Read (r)**: `4`
- **Write (w)**: `2`
- **Execute (x)**: `1`

The value for each permission type is added to calculate the numeric permission for each user category (user, group, others). Here's how the permissions break down:

#### Binary and Decimal Conversion
Permissions are represented in a 3-bit binary system, where each bit corresponds to a permission type:

| **Permission Type** | **Binary** | **Decimal Value** |
|---------------------|------------|-------------------|
| No permissions       | `000`      | `0`               |
| Execute only         | `001`      | `1`               |
| Write only           | `010`      | `2`               |
| Write and Execute    | `011`      | `3`               |
| Read only            | `100`      | `4`               |
| Read and Execute     | `101`      | `5`               |
| Read and Write       | `110`      | `6`               |
| Read, Write, Execute | `111`      | `7`               |

#### Example:
To represent `rwxr-xr--` permissions:
- **User (owner)**: `rwx` → `7`
- **Group**: `r-x` → `5`
- **Others**: `r--` → `4`

The corresponding octal representation is `754`, and the command to set these permissions would be:
```bash
chmod 754 filename
```

### Common Octal Permissions

Here are some commonly used permission sets and their symbolic, binary, and octal representations:

| **Symbolic**   | **Octal** | **Meaning**                                                                                          |
|----------------|-----------|------------------------------------------------------------------------------------------------------|
| `-rwx------`   | `700`     | Owner has full control over the file; no one else has access.                                         |
| `-rwxr-xr-x`  | `755`     | Owner has full control; everyone else can execute the file but only the owner can edit it.            |
| `-rw-rw-r--`  | `664`     | Owner and group members can modify the file; others can only read it.                                |
| `-rw-rw----`  | `660`     | Owner and group members can modify the file; others have no access.                                  |
| `-rw-r--r--`  | `644`     | Owner can modify the file; everyone else can only read it.                                            |

#### Example:
To set the permission `-rwxr-xr-x` for a file, use:
```bash
chmod 755 filename
```

#### More Examples:
- **Set permissions to `700`**: Only the owner can read, write, and execute the file; others have no access.
  ```bash
  chmod 700 confidential_file
  ```
- **Set permissions to `644`**: The owner can read and write the file, while everyone else can only read it.
  ```bash
  chmod 644 public_document
  ```

### Understanding Security Risks with Permissions

It's crucial to avoid overly permissive permissions, such as `777` and `666`. These allow anyone on the system to read, write, or execute the file, which poses significant security risks. Some of the potential issues include:

- **Accidental Changes**: If a file has `777` permissions, anyone on the system can modify it, which could lead to accidental changes.
- **Privilege Escalation**: Malicious users could modify a script or program, introduce harmful code, and cause it to execute when someone else runs the file.
- **Data Destruction**: With `777` or `666` permissions, malicious or careless users can delete or corrupt important data.

#### Example of Over-Permissive Permissions:
If a script has `777` permissions, anyone on the system can modify and execute the file. This is an undesirable security practice:
```bash
chmod 777 risky_script
```

#### Best Practice:
Use appropriate permissions for different users and groups. Limit access to sensitive files and make use of groups to provide controlled access. Avoid using `777` or `666` permissions unless absolutely necessary. For example, if multiple users need write access, use groups and restrict permissions for others.

## Working with Groups and Special Modes

### Working with Groups

When multiple users need to access and modify a file, the `chgrp` command can be used to change the file's group ownership. This allows members of a group to share access to the file.

#### Example 1: Changing the Group Ownership of a File
If a file `sales.report` needs to be shared by a sales team, you can change the group ownership of the file to the `sales` group:

```bash
chgrp sales sales.report
```

#### Example 2: Setting Permissions for Group Access
To allow the members of the `sales` group to read and write the file, while others on the system should have read-only access, set the file permissions to `664`:

```bash
chmod 664 sales.report
```
This translates to:
- Owner: `rw-`
- Group: `rw-`
- Others: `r--`

If no access should be granted to users outside the `sales` group, set permissions to `660`:

```bash
chmod 660 sales.report
```
This means:
- Owner: `rw-`
- Group: `rw-`
- Others: `---`

#### Example 3: Sharing Files in a Common Directory
If you want all team members to access files from a common location, create a shared directory and set appropriate permissions. Assuming you have superuser privileges, create a directory `/usr/local/sales`:

```bash
mkdir /usr/local/sales
chgrp sales /usr/local/sales
chmod 770 /usr/local/sales
```

This gives full access to the sales team, while no access is granted to others. Permissions are:
- Owner: `rwx`
- Group: `rwx`
- Others: `---`

### Directory Permissions

Directory permissions are often misunderstood. Incorrect directory permissions can prevent file access and execution.

#### Example 4: Checking Directory Permissions
To check the permissions of a directory and its files, use `ls -ld` for the directory and `ls -l` for files:

```bash
ls -ld directory/
drwxr-xr-x 2 jason users 4096 Sep 29 22:02 directory/
ls -l directory/
-rwxr--r-- 1 jason users 0 Sep 29 22:02 testprog
```

#### Example 5: Changing Directory Permissions
If a directory's permissions are set incorrectly (e.g., `400`), files within the directory might be inaccessible:

```bash
chmod 400 directory
ls -ld directory/
dr-------- 2 jason users 4096 Sep 29 22:02 directory/
```

This restricts access to the directory, causing permission issues when trying to access files within:

```bash
ls -l directory/
ls: cannot access directory/testprog: Permission denied
```

Changing the directory permissions to `500` grants the owner execute permissions:

```bash
chmod 500 directory/
ls -ld directory/
dr-x------ 2 jason users 4096 Sep 29 22:02 directory/
```

The file `testprog` can now be accessed and executed:

```bash
directory/testprog
```

### Default Permissions and the File Creation Mask

The file creation mask (`umask`) determines the default permissions for new files and directories. The `umask` value is subtracted from the base permissions (777 for directories and 666 for files).

#### Example 6: Viewing the Umask
The `umask` command shows the current default settings:

```bash
umask
0022
```

A `umask` of `022` subtracts write permissions from the group and others, resulting in the following default permissions:
- Directories: `755`
- Files: `644`

#### Example 7: Setting a Specific Umask
To allow members of your group to modify files, set the `umask` to `002`:

```bash
umask 002
```
This results in:
- Directories: `775`
- Files: `664`

For a more restrictive `umask`, such as `007`, which grants no permissions to users outside the group:

```bash
umask 007
```
This results in:
- Directories: `770`
- Files: `660`

#### Example 8: Estimating Creation Permissions
To estimate the permissions of new files and directories based on the `umask`, subtract the umask from the base permissions:
- `umask 022` → Directories: `755`, Files: `644`
- `umask 002` → Directories: `775`, Files: `664`
- `umask 007` → Directories: `770`, Files: `660`

For precise results, convert the permissions to binary and perform bitwise operations.

### Special Modes

In addition to regular user, group, and other permissions, Linux supports three special modes: `setuid`, `setgid`, and the `sticky` bit. These special modes allow specific behaviors for file execution and access control.

#### Setuid (Set User ID)
The `setuid` permission allows a program to run with the privileges of the file's owner, not the user executing it. This is useful for commands that require elevated privileges, such as the `passwd` command, which modifies system files.

To enable `setuid`:
- Octal mode: Prepend `4`
- Symbolic mode: Use `u+s`

#### Example 9: Setting Setuid
```bash
chmod 4755 /usr/bin/passwd
```
This enables `setuid` for the `passwd` command, allowing it to run with superuser privileges.

#### Setgid (Set Group ID)
The `setgid` permission allows a program to run with the group of the file instead of the executing user's group. Additionally, when `setgid` is used on a directory, all files created within that directory inherit the directory’s group.

To enable `setgid`:
- Octal mode: Prepend `2`
- Symbolic mode: Use `g+s`

#### Example 10: Setting Setgid
```bash
chmod 2755 /usr/bin/locate
```
This enables `setgid` on the `locate` command.

#### Example 11: Setting Setgid on a Directory
```bash
chmod 2770 /usr/local/sales
```
This ensures that all new files created in `/usr/local/sales` will inherit the `sales` group.

#### Sticky Bit
The `sticky` bit prevents users from deleting files owned by others, even if they have write access to the directory. This is typically used in shared directories like `/tmp` to prevent file deletion by unauthorized users.

To enable the sticky bit:
- Octal mode: Prepend `1`
- Symbolic mode: Use `+t`

#### Example 12: Setting the Sticky Bit
```bash
chmod 1777 /tmp
```
This allows everyone to write to `/tmp`, but only the owner of a file can delete it.




## Summary of Permissions Commands


| **Command**      | **Description**                                                  | **Example**                                                 |
|------------------|------------------------------------------------------------------|-------------------------------------------------------------|
| `ls -l`          | Lists files with detailed information, including permissions.    | `ls -l myfile.txt`                                           |
| `chmod`          | Changes file permissions.                                        | `chmod u+x myscript.sh`                                      |
| `groups`         | Displays the groups a user belongs to.                           | `groups`                                                    |
| `id -Gn`         | Shows the list of groups for a specific user.                    | `id -Gn john`                                               |
| `ls -l` (example)| Displays detailed file listing with permissions for `sales.data`.| `-rw-r--r-- 1 jason users 10400 Jun 14 09:31 sales.data`      |
| `chmod 744`      | Sets permissions using numeric mode (user read/write, group/others read only). | `chmod 744 file.txt`                                         |
| `chmod u+x`      | Adds execute permission for the user.                            | `chmod u+x myscript.sh`                                      |
| `chmod g-w`      | Removes write permission for the group.                         | `chmod g-w myscript.sh`                                      |
| `chmod o=r`      | Sets read-only permissions for others.                          | `chmod o=r file.txt`                                         |
| `chmod 600`      | Sets file permissions for user (read/write) and no permissions for group/others. | `chmod 600 myfile.txt`                                       |
| `chmod 755`      | Grants full permissions to the user, and read/execute for group and others. | `chmod 755 script.sh`                                        |
| `ls -l`                           | Lists files and directories with detailed information including permissions.                     | `ls -l sales.data`                                        |
| `chmod g+w file`                  | Adds write permission for the group on the specified file.                                        | `chmod g+w sales.data`                                   |
| `chmod g-w file`                  | Removes write permission for the group on the specified file.                                    | `chmod g-w sales.data`                                   |
| `chmod go+x file`                 | Adds execute permission for both the group and others on the specified file.                      | `chmod go+x sales.data`                                  |
| `chmod ug+wx file`                | Adds both write and execute permissions for the user and group on the specified file.            | `chmod ug+wx sales.data`                                 |
| `chmod u=rwx,g+x,a=r file`        | Sets specific permissions for the user, group, and others.                                       | `chmod u=rwx,g+x,a=r sales.data`                         |
| `chmod a=r file`                  | Sets read-only permissions for everyone (user, group, and others).                               | `chmod a=r sales.data`                                   |
| `chmod o-rwx file`                | Removes all permissions (read, write, execute) for others.                                       | `chmod o-rwx sales.data`                                 |
| `chmod u+x,g-w,o=r file`          | Adds execute permission for the user, removes write permission for the group, and sets read-only permissions for others. | `chmod u+x,g-w,o=r sales.data`                           |
| `chmod u=rwx file`                | Explicitly sets the user’s permissions to read, write, and execute, overwriting any existing user permissions. | `chmod u=rwx sales.data`                                 |
| `chmod 700 filename`     | Sets full control for the owner, and no permissions for others.       | Grants owner `rwx` permissions, group and others have no access. |
| `chmod 755 filename`     | Grants full permissions to the owner, and read and execute permissions to group and others. | Owner: `rwx`, Group: `r-x`, Others: `r-x`. |
| `chmod 664 filename`     | Grants read and write permissions to the owner and group, and read-only permission to others. | Owner: `rw-`, Group: `rw-`, Others: `r--`. |
| `chmod 660 filename`     | Grants read and write permissions to the owner and group, and no permissions to others. | Owner: `rw-`, Group: `rw-`, Others: `---`. |
| `chmod 644 filename`     | Grants read and write permissions to the owner, and read-only permissions to others. | Owner: `rw-`, Group: `r--`, Others: `r--`. |
| `chmod 777 filename`     | Grants full control to everyone (user, group, others).                | Owner: `rwx`, Group: `rwx`, Others: `rwx`. |
| `chmod 755 confidential_file` | Grants full control to the owner, and read and execute permissions to group and others. | Owner: `rwx`, Group: `r-x`, Others: `r-x`. |
| `chmod 644 public_document` | Grants read and write permissions to the owner, and read-only permissions to others. | Owner: `rw-`, Group: `r--`, Others: `r--`. |
| `chgrp`          | Changes the group ownership of a file or directory.       | `chgrp sales sales.report`                                           |
| `chmod`          | Changes the permissions of a file or directory.           | `chmod 664 sales.report`                                             |
| `chmod`          | Sets directory permissions to restrict access to the group. | `chmod 770 /usr/local/sales`                                         |
| `ls -ld`         | Displays detailed information about a directory.          | `ls -ld directory/`                                                  |
| `ls -l`          | Displays detailed information about files in a directory. | `ls -l directory/`                                                   |
| `umask`          | Displays or sets the file creation mask (umask).           | `umask 022`                                                          |
| `umask` (with `-S`) | Displays or sets the file creation mask using symbolic notation. | `umask -S`                                                           |
| `chmod` (with `setuid`) | Sets the setuid permission to run a program with the owner's privileges. | `chmod 4755 /usr/bin/passwd`                                          |
| `chmod` (with `setgid`) | Sets the setgid permission to run a program with the group's privileges. | `chmod 2755 /usr/bin/locate`                                          |
| `chmod` (with `sticky bit`) | Sets the sticky bit to prevent users from deleting files owned by others. | `chmod 1777 /tmp`                                                    |


# Viewing and Editing Files

## Viewing Files

### `cat` - Concatenate and Display the Entire File

The `cat` command displays the entire contents of a file. It is useful for smaller files but can be overwhelming for large files.

**Example**:
```bash
cat goals.txt
```
This will display the full content of `goals.txt`.

---

### `more` - Browse Through a Text File

The `more` command allows you to view a file one page at a time, which is useful for larger files.

- **Spacebar**: Move forward by one page.
- **Enter**: Move forward by one line.
- **q**: Quit viewing the file.

**Example**:
```bash
more goals.txt
```
This will display the content of `goals.txt`, allowing you to scroll through it.

---

### `less` - Browse Backward and Search Within a File

The `less` command is similar to `more`, but it offers additional functionality like backward navigation and searching.

- **Spacebar**: Move forward by one page.
- **b**: Move backward by one page.
- **/pattern**: Search for a specific pattern forward in the file.
  - **`n`** to go to find
  - **`N`** to go to previous find
- **?pattern**: Search for a specific pattern backward in the file.
- **F**: Follow the file as it grows.

**Example**:
```bash
less goals.txt
```
You can scroll up and down through the file, search for patterns, and use other advanced features like following the file.

### Philosophy: *less is more*

---

### `head` - Display the Beginning of a File

The `head` command shows the first 10 lines of a file by default. You can also specify how many lines to display using `-N`, where `N` is the number of lines.

**Example**:
```bash
$ head goals.txt
```
This will display the first 10 lines of `goals.txt`.

To display only the first line of a file:
```bash
$ head -1 goals.txt
```

---

### `tail` - Display the End of a File

The `tail` command shows the last 10 lines of a file by default. You can specify the number of lines with `-N`, where `N` is the number of lines you want to display.

**Example**:
```bash
$ tail goals.txt
```
This will display the last 10 lines of `goals.txt`.

To display only the last line of a file:
```bash
$ tail -1 goals.txt
```

---

### `tail -f` - Follow a File as It Grows

The `-f` flag with `tail` allows you to view a file as it is updated in real time. This is particularly useful for log files.

**Example**:
```bash
$ tail -f /var/log/syslog
```
This will show the contents of `syslog` as it gets updated.

Alternatively, after opening a file with `less`, you can type `F` to start following the file as it grows.

**Example**:
```bash
less goals.txt
```
Then, type `F` to follow the file in real-time.

## Summary of Viewing files

| **Command**          | **Description**                                                                            | **Example**                                   |
|----------------------|--------------------------------------------------------------------------------------------|-----------------------------------------------|
| `cat [file]`         | Displays the entire contents of a file. Useful for smaller files.                          | `cat goals.txt`                              |
| `more [file]`        | Displays a file one page at a time. Useful for larger files.                               | `more goals.txt`                             |
| `less [file]`        | Allows backward navigation and searching within a file.                                   | `less goals.txt`                             |
| `head [file]`        | Displays the first 10 lines of a file.                                                     | `head goals.txt`                             |
| `head -N [file]`     | Displays the first N lines of a file.                                                      | `head -5 goals.txt`                          |
| `tail [file]`        | Displays the last 10 lines of a file.                                                      | `tail goals.txt`                             |
| `tail -N [file]`     | Displays the last N lines of a file.                                                       | `tail -5 goals.txt`                          |
| `tail -f [file]`     | Displays the last lines of a file and follows it as it grows (useful for logs).           | `tail -f /var/log/syslog`                    |
| `less [file]` + `F`  | Follow a file as it grows in real-time within `less`.                                      | `less goals.txt` then type `F`               |

---

## The Vim Editor

Vim is a highly powerful and efficient text editor that is often used in Linux and Unix systems. It is an improvement on the original `vi` editor, adding advanced features such as syntax highlighting, multi-level undo/redo, network file editing, and screen splitting. Vim is often available by default on many Linux distributions, and when you run `vi`, you are usually running Vim.

Vim's main feature is its use of different **modes** to manage interaction with the file, providing a powerful and efficient way to navigate and edit text.

### Modes in Vim

#### 1. Command Mode

Vim starts in **Command Mode**, where keystrokes are interpreted as commands, not text input. In this mode, you can navigate, search, delete, copy, paste, and perform many other actions without directly typing into the file.

- **Return to Command Mode**: Press `Esc` at any time.

**Navigation Keys in Command Mode**:
| Action                              | Key  |
|-------------------------------------|------|
| Move up one line                    | `k`  |
| Move down one line                  | `j`  |
| Move left one character             | `h`  |
| Move right one character            | `l`  |
| Move right one word                 | `w`  |
| Move left one word                  | `b`  |
| Move to the beginning of the line   | `^`  |
| Move to the end of the line         | `$`  |
| Move to the beginning of the file   | `gg` |
| Move to the end of the file         | `G`  |

**Example**:
- To move the cursor 3 lines down, type `3j`.
- To move to the start of the file, type `gg`.
- To move to the end of the file, type `G`.

#### 2. Insert Mode

In **Insert Mode**, you can type text into the file. To enter Insert Mode from Command Mode, press:
- `i` to insert at the current position.
- `I` to insert at the beginning of the line.
- `a` to append text after the cursor.
- `A` to append at the end of the line.

Once you have finished typing, press `Esc` to return to Command Mode.

**Example**:
- Press `i` to enter Insert Mode at the current cursor position and start typing.
- Press `A` to start typing at the end of the line.

#### 3. Line Mode

Line Mode (also called Command Line Mode) is accessed from Command Mode by typing `:`. In Line Mode, you can issue commands to save, quit, replace text, and perform some forms of navigation.

| Action                             | Key   |
|------------------------------------|-------|
| Save the file                      | `:w`  |
| Save the file even if permissions are not set | `:w!` |
| Quit the editor                    | `:q`  |
| Quit without saving changes        | `:q!` |
| Save and quit                      | `:wq` or `:x` |
| Go to line `n`                     | `:n`  |
| Go to the last line of the file    | `:$`  |
| Enable line numbers                | `:set nu` |
| Disable line numbers               | `:set nonu` |
| Access help documentation          | `:help` |

**Examples**:
- To save a file, type `:w`.
- To quit Vim, type `:q`.
- To go to line 20, type `:20`.
- To enable line numbering, type `:set nu`.

### Repeating Commands

In Vim, many commands can be repeated by prefixing them with a number. For example:
- To move down three lines, type `3j`.
- To insert the word "Hello" twenty times, type `20iHello` and press `Esc`.

**Example**:
- To delete 5 lines, type `5dd`.

### Additional Command Mode Actions

Vim provides a wide range of commands for modifying and managing text efficiently.

#### Deleting Text

| Action                             | Key  |
|------------------------------------|------|
| Delete a character                 | `x`  |
| Delete a word                      | `dw` |
| Delete a line                      | `dd` |
| Delete from the current position to the end of the line | `D` |

**Examples**:
- To delete a single character, move the cursor over it and press `x`.
- To delete a word, place the cursor at the beginning of the word and press `dw`.
- To delete an entire line, press `dd`.

#### Changing Text

| Action                             | Key  |
|------------------------------------|------|
| Replace the current character      | `r`  |
| Change the current word            | `cw` |
| Change the current line            | `cc` |
| Change from the current position to the end of the line | `c$` |

**Examples**:
- To replace the current character with `d`, type `rd`.
- To change the current word, press `cw` and type the new word.
- To change the entire line, type `cc` and then type the new content.

#### Copying and Pasting Text

Vim's `yank` command allows you to copy text, and the `p` command allows you to paste it.

| Action                             | Key  |
|------------------------------------|------|
| Yank (copy) the current line       | `yy` |
| Yank a word                        | `yw` |
| Paste the most recent yanked text  | `p`  |

**Examples**:
- To copy (yank) the current line, type `yy`.
- To paste the copied line, type `p`.

#### Undo and Redo

Vim allows you to undo and redo changes.

| Action                             | Key       |
|------------------------------------|-----------|
| Undo the last change               | `u`       |
| Redo the last undone change        | `Ctrl + r`|

**Examples**:
- To undo the last change, type `u`.
- To redo the undone change, press `Ctrl + r`.

#### Searching in Vim

You can search for patterns within the file in Vim.

| Action                             | Key              |
|------------------------------------|------------------|
| Start a forward search for `<pattern>` | `/pattern`       |
| Start a reverse search for `<pattern>` | `?pattern`      |

**Examples**:
- To search for the word "hello", type `/hello` and press `Enter`.
- To search backward for "hello", type `?hello` and press `Enter`.

#### Case Changing

Vim allows you to change the case of letters.

| Action                             | Key  |
|------------------------------------|------|
| Reverse the case of the current character | `~`  |

**Example**:
- To change the case of the current character, type `~`.

#### Other Useful Commands

| Action                             | Key  |
|------------------------------------|------|
| Move the cursor to the next word   | `w`  |
| Move the cursor to the previous word | `b` |
| Move the cursor to the beginning of the line | `^` |
| Move the cursor to the end of the line | `$` |
| Move the cursor to the next match of a search | `n` |
| Move the cursor to the previous match of a search | `N` |

**Example**:
- To move to the next word, type `w`.
- To move to the previous word, type `b`.

---

## Summary of Vim Commands

| Action                                         | Key     |
|------------------------------------------------|---------|
| Move up one line                               | `k`     |
| Move down one line                             | `j`     |
| Move left one character                        | `h`     |
| Move right one character                       | `l`     |
| Move right one word                            | `w`     |
| Move left one word                             | `b`     |
| Move to the beginning of the line              | `^`     |
| Move to the end of the line                    | `$`     |
| Move to the beginning of the file              | `gg`    |
| Move to the end of the file                    | `G`     |
| Insert at the current position                 | `i`     |
| Insert at the beginning of the line            | `I`     |
| Append text after the cursor position          | `a`     |
| Append text at the end of the line             | `A`     |
| Save the file                                  | `:w`    |
| Save the file even if permissions are not set  | `:w!`   |
| Quit the editor                                | `:q`    |
| Quit without saving the file                   | `:q!`   |
| Save and quit                                  | `:wq` or `:x` |
| Go to line `n`                                 | `:n`    |
| Go to the last line of the file                | `:$`    |
| Enable line numbering                          | `:set nu` |
| Disable line numbering                         | `:set nonu` |
| Access the help documentation                  | `:help` |
| Repeat a command with a number prefix (e.g., 3j to move down 3 lines) | `3j`, `20iText`, `80i_`  |
| Delete a character                             | `x`     |
| Delete a word                                  | `dw`    |
| Delete a line                                  | `dd`    |
| Delete from the current position to the end of the line | `D`     |
| Replace the current character                  | `r`     |
| Change the current word                        | `cw`    |
| Change the current line                        | `cc`    |
| Change from the current position to the end of the line | `c$`    |
| Reverse the case of the current character      | `~`     |
| Yank (copy) the current line                   | `yy`    |
| Yank a word                                    | `yw`    |
| Paste the most recent yanked text              | `p`     |
| Undo the last change                           | `u`     |
| Redo the last undone change                    | `Ctrl + r` |
| Start a forward search for `<pattern>`         | `/pattern` |
| Start a reverse search for `<pattern>`         | `?pattern` |
| Reverse the case of the current character      | `~`     |
| Move the cursor to the next word               | `w`     |
| Move the cursor to the previous word           | `b`     |
| Move the cursor to the beginning of the line   | `^`     |
| Move the cursor to the end of the line         | `$`     |
| Move the cursor to the next match of a search  | `n`     |
| Move the cursor to the previous match of a search | `N`   |

---

# Deleting, Moving, and Renaming Files and Directories

## Deleting Files and Directories

The `rm` command is used to remove files and directories. It is a powerful tool, and with great power comes great responsibility, so it is important to understand its options thoroughly.

### Basic Usage

- **Remove a file**:
  ```bash
  rm file
  ```
  This command will delete the specified file. For example:
  ```bash
  rm test.txt
  ```
  This will delete the file `test.txt` in the current directory.

- **Remove a directory**:
  The `-r` option is required to remove a directory recursively, including its contents (files and subdirectories).
  ```bash
  rm -r directory
  ```
  Example:
  ```bash
  rm -r my_folder
  ```
  This command deletes the directory `my_folder` and all of its contents.

- **Force remove a file**:
  The `-f` option forces the removal of a file without prompting for confirmation, even if the file is write-protected.
  ```bash
  rm -f file
  ```
  Example:
  ```bash
  rm -f old_backup.txt
  ```
  This will remove `old_backup.txt` without asking for confirmation.

### Using Wildcards with `rm`

Wildcards are useful for matching multiple files or directories at once.

- **Asterisk (`*`)**: Matches any string of characters, including none.
  ```bash
  rm *.txt
  ```
  This command deletes all `.txt` files in the current directory.

- **Question mark (`?`)**: Matches exactly one character.
  ```bash
  rm file?.txt
  ```
  This command deletes files like `file1.txt`, `file2.txt`, but not `file10.txt`.

- **Hidden files**: Files and directories that begin with a period (`.`) are considered hidden. To remove hidden files, you need to specify the period in your search pattern.
  ```bash
  rm .hidden_file
  ```

## Copying Files and Directories

The `cp` command is used to copy files and directories. You can create duplicates of files or move files to different locations without modifying the original.

### Basic Usage

- **Copy a file**:
  ```bash
  cp source_file destination_file
  ```
  Example:
  ```bash
  cp document.txt backup.txt
  ```
  This copies the contents of `document.txt` to `backup.txt`.

- **Copy multiple files to a directory**:
  ```bash
  cp source_file1 [source_fileN ...] destination_directory
  ```
  Example:
  ```bash
  cp file1.txt file2.txt /backup/
  ```
  This copies `file1.txt` and `file2.txt` into the `/backup/` directory.

### Interactive Mode

- **Interactive copy**: Use the `-i` option to **prompt before overwriting** existing files.
  ```bash
  cp -i source_file destination_file
  ```
  Example:
  ```bash
  cp -i file1.txt file2.txt
  ```
  If `file2.txt` exists, `cp` will ask if you want to overwrite it.
  **Always try to use interactive copy**.

### Copying Directories

- **Copy a directory recursively**: Use the `-r` option to copy a directory and its contents.
  ```bash
  cp -r source_directory destination_directory
  ```
  Example:
  ```bash
  cp -r project_folder /backup/
  ```
  This copies the entire `project_folder` to `/backup/`.

  If you don't use `-r` when dealing with directories, you will get error. 
  ```bash
  $ cp source_directory destination_directory
  cp: -r not specified; omitting directory 'source_directory'
  ```

## Moving and Renaming Files and Directories

The `mv` command is used to **move files and directories** from one location to another. It can also be used to **rename files and directories**.

### Basic Usage

- **Move a file**:
  ```bash
  mv source destination
  ```
  Example:
  ```bash
  mv test.txt /home/user/backup/
  ```
  This moves `test.txt` to the `/home/user/backup/` directory.

- **Move and rename a file**:
  ```bash
  mv old_name new_name
  ```
  Example:
  ```bash
  mv document.txt new_document.txt
  ```
  This renames `document.txt` to `new_document.txt`.

- **Move a file into a directory**:
  If the destination is a directory, the file will be moved inside that directory.
  ```bash
  mv file1.txt /path/to/directory/
  ```
  Example:
  ```bash
  mv image.jpg /home/user/photos/
  ```
  This moves `image.jpg` into the `photos` directory.

### Interactive Mode

- **Interactive move**: The `-i` option prompts for confirmation before overwriting an existing file.
  ```bash
  mv -i source destination
  ```
  Example:
  ```bash
  mv -i old_document.txt new_document.txt
  ```
  If `new_document.txt` exists, `mv` will ask whether you want to overwrite it.
  **Always try to use interactive move.**

### Renaming a Directory

You can use `mv` to rename a directory in the same way you would rename a file.

- **Rename a directory**:
  ```bash
  mv old_directory_name new_directory_name
  ```
  Example:
  ```bash
  mv old_project new_project
  ```
  This renames the directory `old_project` to `new_project`.

## Examples: Renaming and Moving Files

Let’s take a closer look at some real-world examples.

### Example 1: Renaming and Moving a Directory

1. **Rename a directory**:
   ```bash
   mv 1dir 1dir-renamed
   ```
   This renames the directory `1dir` to `1dir-renamed`.

2. **Rename a file and move it into the renamed directory**:
   ```bash
   mv 1file 1dir-renamed/file1
   ```
   This renames `1file` to `file1` and moves it into the `1dir-renamed` directory.

3. **Move a file into a new directory, overwriting if necessary**:
   ```bash
   mv file1.txt 2file.txt
   ```
   This renames `file1.txt` to `2file.txt` in the current directory.

4. **Move a file interactively**:
   ```bash
   mv -i 2file.txt file1.txt
   ```
   If `file1.txt` exists, this command will ask for confirmation before overwriting it.

---

## Summary of Deleting, Moving, and Renaming Files and Directories Commands

| **Command**| **Description**| **Example**|
|------------|----------------|------------|
| `rm file`| Remove a file.| `rm test.txt` - Removes `test.txt`.|
| `rm -r directory`| Remove a directory recursively, including its contents (files and subdirectories).
| `rm -r my_folder` - Removes the `my_folder` directory and all its contents.|
| `rm -f file`| Force removal of a file without confirmation, even if the file is write-protected.| `rm -f old_backup.txt` - Forces removal of `old_backup.txt` without prompting.|
| `rm *`| Use wildcard to match all files with the specified extension or pattern.| `rm *.txt` - Deletes all `.txt` files in the current directory.|
| `rm ?`| Use wildcard to match a single character.| `rm file?.txt` - Deletes files like `file1.txt`, `file2.txt`, but not `file10.txt`.|
| `rm .hidden_file`| Remove hidden files (files starting with a dot).| `rm .env` - Removes the hidden file `.env`.|
| `cp source_file destination_file`| Copy a file to a new file.| `cp document.txt backup.txt` - Copies `document.txt` to `backup.txt`.|
| `cp source_file1 [source_fileN ...] destination_directory` | Copy multiple files to a directory.| `cp file1.txt file2.txt /backup/` - Copies `file1.txt` and `file2.txt` to `/backup/` directory.|
| `cp -i source_file destination_file`              | Interactive copy; prompts for confirmation if the destination file exists.| `cp -i file1.txt file2.txt` - Asks for confirmation before overwriting `file2.txt`.|
| `cp -r source_directory destination_directory`     | Recursively copy a directory and its contents.| `cp -r project_folder /backup/` - Copies `project_folder` to `/backup/` directory.|
| `mv source destination`| Move a file or directory to a new location, or rename it if the destination is a file.| `mv file1.txt /home/user/backup/` - Moves `file1.txt` to `/home/user/backup/` directory.|
| `mv old_name new_name`| Rename a file or directory.| `mv old_project new_project` - Renames `old_project` to `new_project`.|
| `mv source destination_directory`| Move a file into a directory. If the destination is a directory, the file is moved there.| `mv image.jpg /home/user/photos/` - Moves `image.jpg` to `/home/user/photos/` directory.|
| `mv -i source destination`| Interactive move; prompts for confirmation if the destination file exists and will be overwritten.| `mv -i old_document.txt new_document.txt` - Asks for confirmation before overwriting `new_document.txt`.|
| `mv 1dir 1dir-renamed`| Rename a directory.| `mv 1dir 1dir-renamed` - Renames `1dir` to `1dir-renamed`.|
| `mv file1.txt 1dir-renamed/file1`| Rename a file and move it into another directory.| `mv 1file 1dir-renamed/file1` - Renames `1file` to `file1` and moves it into `1dir-renamed` directory.|
| `mv file1.txt 2file.txt`| Rename a file without prompt (can overwrite).| `mv file1.txt 2file.txt` - Renames `file1.txt` to `2file.txt`.|
| `mv -i 2file.txt file1.txt`| Interactive move; prompts before overwriting an existing file.| `mv -i 2file.txt file1.txt` - Prompts before overwriting `file1.txt`.|

### Notes:
- The `-i` flag is useful for confirming file overwrites to prevent accidental deletion or overwriting.
- The `-r` flag is necessary for copying or deleting directories and their contents recursively.
- Wildcards (`*`, `?`) allow you to match files based on patterns, providing a powerful way to work with multiple files at once.

---

# Finding, Sorting, and Comparing Files and Directories

## Finding Files and Directories

### find Command
The `find` command is used to recursively search for files and directories based on different criteria, such as name, size, owner, or modification time.

#### Syntax:
```
find [path...] [expression]
```
- `path`: The directory path to start the search (defaults to the current directory if omitted).
- `expression`: The condition used to filter the files.

#### Common `find` Options and Examples:

| **Command**                                   | **Description**                                             | **Example**                                                                 |
|-----------------------------------------------|-------------------------------------------------------------|-----------------------------------------------------------------------------|
| `find . -name pattern`                        | Display items whose names match a pattern (case-sensitive)   | `find . -name "*.txt"` - Finds all `.txt` files in the current directory and subdirectories. |
| `find . -iname pattern`                       | Same as `-name`, but case-insensitive                        | `find . -iname "*.jpg"` - Finds all `.jpg` files, case-insensitive.        |
| `find . -ls`                                  | Perform an `-ls` operation on each found item                | `find . -ls` - Lists detailed information for all files in the current directory and subdirectories. |
| `find . -mtime number_of_days`                | Display items that are a specific number of days old         | `find . -mtime 7` - Finds files modified 7 days ago.                        |
| `find . -size number`                         | Display items that match a size criterion                    | `find . -size +10M` - Finds files larger than 10MB.                          |
| `find . -newer file`                          | Display items newer than a specified file                    | `find . -newer reference.txt` - Finds files modified after `reference.txt`. |
| `find . -exec command {} \;`                   | Run a command on each found item                             | `find . -name "*.log" -exec rm {} \;` - Deletes all `.log` files found.    |

#### Combining `find` Options
You can combine multiple expressions to refine your search. For example, to find `.txt` files modified in the last 7 days:
```
find . -name "*.txt" -mtime -7
```

### locate Command
The `locate` command is faster than `find` because it uses an index database updated by the `updatedb` process. However, it does not include recently created files.

#### Syntax:
```
locate pattern
```

#### Example:
```
locate example.txt
```
- Finds all instances of `example.txt` in the system based on the pre-built index.

**Note:** Since `locate` relies on an index, it won't find files created since the last `updatedb` run (usually updated daily).

## Sorting Files

The `sort` command is used to sort the contents of a file or input in various ways, such as by **key**, in **reverse order**, or uniquely.

### Common `sort` Options and Examples:

| **Command**| **Description**| **Option**| **Example**|
|------------|----------------|-----------|------------|
| `sort file`| Sort the contents of a file **line by line**| `file`| `sort mylist.txt` - Sorts the lines in `mylist.txt` in ascending order. |
| `sort -k FIELD_NUM`  | Sort by a specific field/column| `-k FIELD_NUM`| `sort -k 2 mylist.txt` - Sorts by the second column in `mylist.txt`.   |
| `sort -r`| Sort in reverse order| `-r`| `sort -r mylist.txt` - Sorts the lines in `mylist.txt` in descending order. |
| `sort -u`| Sort uniquely (no duplicates)| `-u`| `sort -u mylist.txt` - Sorts `mylist.txt` and removes duplicates.|

#### Sorting by Multiple Keys:
To sort by multiple keys (columns), you can use multiple `-k` options:
```bash
sort -k 2 -k 1 mylist.txt
```
This sorts first by the second column and then by the first column.

### Example of Sorting with Specific Keys:
Suppose `mylist.txt` contains the following data:
```
John 28
Alice 22
Bob 25
Alice 25
```
Running the command:
```
sort -k 2 -k 1 mylist.txt
```
Would output:
```
Alice 22
Alice 25
Bob 25
John 28
```

## Comparing Files

The `diff`, `sdiff`, and `vimdiff` commands are used to compare files and directories, displaying differences in their contents.

### diff Command
The `diff` command shows the differences between two files.

#### Syntax:
```
diff file1 file2
```

#### Example:
```
diff old_version.txt new_version.txt
```
Output:
```
1c1
< Old line
---
> New line
```
- The `<` symbol indicates the line from the first file, and `>` represents the line from the second file.
- `c` means "change" (line 1 was changed).

### sdiff Command
The `sdiff` command displays files side-by-side, highlighting differences.

#### Syntax:
```
sdiff file1 file2
```

#### Example:
```
sdiff old_version.txt new_version.txt
```
Output:
```
Old line     | New line
Another line | Another line
```
- Differences are shown in two columns with a pipe (`|`) separating them.

### vimdiff Command
The `vimdiff` command uses the `vim` editor to show the differences between files in a split screen.

#### Syntax:
```
vimdiff file1 file2
```

#### Example:
```
vimdiff old_version.txt new_version.txt
```
- The files will be displayed side by side within `vim`, with differences highlighted.

## Summary of Finding, Sorting, and Comparing Files and Directories

| **Command** | **Description** | **Example** |
|-------------|-----------------|-------------|
| `find` | Recursively searches for files and directories based on specified conditions. | `find . -name "*.txt"` - Finds all `.txt` files in the current directory and subdirectories. |
| `find . -iname pattern` | Same as `-name`, but case-insensitive search. | `find . -iname "*.jpg"` - Finds `.jpg` files, case-insensitive. |
| `find . -ls` | Lists detailed information for all files found. | `find . -ls` - Lists detailed info for files in the current directory and subdirectories. |
| `find . -mtime number_of_days` | Finds files modified a specific number of days ago. | `find . -mtime 7` - Finds files modified 7 days ago. |
| `find . -size number` | Finds files of a specific size. | `find . -size +10M` - Finds files larger than 10MB. |
| `find . -newer file` | Finds files modified after a specific file. | `find . -newer reference.txt` - Finds files modified after `reference.txt`. |
| `find . -exec command {} \;` | Runs a command on each file found. | `find . -name "*.log" -exec rm {} \;` - Deletes all `.log` files found. |
| `locate` | Searches for files using an indexed database (faster than `find`). | `locate example.txt` - Finds all instances of `example.txt` in the system. |
| `sort` | Sorts the contents of a file. | `sort mylist.txt` - Sorts the lines in `mylist.txt` in ascending order. |
| `sort -k FIELD_NUM` | Sorts by a specific column. | `sort -k 2 mylist.txt` - Sorts by the second column in `mylist.txt`. |
| `sort -r` | Sorts the contents in reverse order. | `sort -r mylist.txt` - Sorts the lines in `mylist.txt` in descending order. |
| `sort -u` | Sorts and removes duplicates. | `sort -u mylist.txt` - Sorts `mylist.txt` and removes duplicates. |
| `diff` | Compares two files and shows their differences. | `diff old_version.txt new_version.txt` - Compares `old_version.txt` and `new_version.txt`. |
| `sdiff` | Compares two files side by side, showing differences. | `sdiff old_version.txt new_version.txt` - Displays a side-by-side comparison. |
| `vimdiff` | Compares two files in the Vim editor with differences highlighted. | `vimdiff old_version.txt new_version.txt` - Displays differences in `vim`. |

# I/O Redirection

Linux uses a concept called **I/O streams** to handle input and output between commands and files. There are three default I/O streams in Linux:

- **Standard Input (stdin)**: File descriptor 0. Typically, this comes from your keyboard.
- **Standard Output (stdout)**: File descriptor 1. This is where the command output is displayed (typically on your screen).
- **Standard Error (stderr)**: File descriptor 2. This is where error messages are displayed.

These streams abstract the communication between commands and files. For example, input can be taken from a file, output can be saved to a file, and error messages can be redirected to another file.

## Standard Streams Overview

| **Stream**          | **Abbreviation** | **File Descriptor** |
|---------------------|------------------|---------------------|
| Standard Input      | stdin            | 0                   |
| Standard Output     | stdout           | 1                   |
| Standard Error      | stderr           | 2                   |

### File Descriptors and EOF
Each stream is assigned a **file descriptor**. For standard input, output, and error, these are assigned file descriptors 0, 1, and 2, respectively.

In Linux, input (like a file or standard input) is terminated by an **EOF (End of File)** marker. This can be generated by pressing `Ctrl-d` in the terminal.

### Example: Using `sort` Command
- If you provide a file to the `sort` command, it sorts the contents of the file:
  ```bash
  sort file.txt
  ```
- If you don't specify a file, you can provide standard input manually:
  ```bash
  sort
  ```
  (Now, type the text you want to sort. Press `Ctrl-d` to indicate EOF, and the text will be sorted).

## Pipes and Redirection

You can also redirect the output of one command to be the input of another. This is done using the **pipe (`|`)** symbol.

### Example: Pipe

```bash
cat file.txt | sort
```

This command takes the contents of `file.txt` (via `cat`) and sorts it (via `sort`).

### Redirecting Input and Output

- **Input Redirection**: To use the contents of a file as standard input, use the **less than sign (`<`)**:
  ```bash
  sort < file.txt
  ```

- **Output Redirection**: To redirect the output of a command to a file, use the **greater than sign (`>`)**:
  ```bash
  echo "Hello, World!" > output.txt
  ```
  If the file does not exist, it will be created. If it does exist, it will be overwritten.

- **Appending Output to a File**: To append output to a file, use the **double greater than sign (`>>`)**:
  ```bash
  echo "New Line" >> output.txt
  ```
  This appends "New Line" to `output.txt`.

## Redirection with Specific File Descriptors

You can explicitly reference file descriptors when redirecting input or output. The following example shows how to redirect standard error to a file:

```bash
command 2> error.log
```

This sends the error messages from `command` to `error.log` (standard error to the file). 

### Redirecting Both Standard Output and Standard Error

You can combine both **standard output** and **standard error** into one file. Use the **`2>&1`** syntax to redirect both streams to the same destination:

```bash
command > output.log 2>&1
```

This command redirects both the standard output and standard error from `command` into `output.log`.

### Redirecting Output to `/dev/null`

If you don't want to display the output of a command (or save it to a file), you can discard it by redirecting it to the **null device** (`/dev/null`). This "bit bucket" discards anything sent to it.

- Redirecting **standard output**:
  ```bash
  command > /dev/null
  ```

- Redirecting **standard error**:
  ```bash
  command 2> /dev/null
  ```

- Redirecting **both output and error**:
  ```bash
  command > /dev/null 2>&1
  ```

### More Complex Examples

1. **Reading from a file and redirecting output**:
   ```bash
   sort < test.txt > sorted.txt
   ```
   This reads input from `test.txt` and sorts it, saving the sorted output to `sorted.txt`.

2. **Using pipes and redirecting output**:
   ```bash
   cat file.txt | grep "search term" > result.txt
   ```
   This command finds "search term" in `file.txt` and saves the results to `result.txt`.

3. **Redirecting output and errors to different files**:
   ```bash
   command > output.txt 2> error.txt
   ```
   This command redirects **standard output** to `output.txt` and **standard error** to `error.txt`.

4. **Combining output and error into one file**:
   ```bash
   command > combined-output.txt 2>&1
   ```

## Summary of I/O Redirection Commands

| **Action**                                                   | **Format**            | **Operator**      | **Description**                                                                 |
|--------------------------------------------------------------|-----------------------|-------------------|---------------------------------------------------------------------------------|
| **Create or overwrite file** with standard output from a command | `cmd > file`           | `>`               | Redirects the standard output of `cmd` to a file, creating or overwriting the file. |
| **Create or append to file** with standard output from a command | `cmd >> file`          | `>>`              | Redirects the standard output of `cmd` to a file, appending to the file if it exists. |
| **Use contents of a file as standard input to command**       | `cmd < file`           | `<`               | Redirects the contents of `file` to `cmd` as standard input.                   |
| **Redirect standard error to a file**                         | `cmd 2> file`          | `2>`              | Redirects the standard error of `cmd` to a file.                                |
| **Redirect both output and error to the same file**           | `cmd > file 2>&1`      | `2>&1`            | Combines both standard output and standard error into `file`.                   |
| **Discard output (send it to the null device)**               | `cmd > /dev/null`      | `> /dev/null`      | Discards the standard output by redirecting it to `/dev/null`.                 |
| **Discard standard error (send it to the null device)**       | `cmd 2> /dev/null`     | `2> /dev/null`     | Discards the standard error by redirecting it to `/dev/null`.                  |
| **Combine output and error, sending both to `/dev/null`**     | `cmd > /dev/null 2>&1` | `> /dev/null 2>&1` | Discards both standard output and standard error by redirecting them to `/dev/null`. |



# Additional Command Line Concepts

## Environment Variables
Environment variables are name-value pairs that provide information to processes about the environment in which they run. These variables help programs adjust their behavior based on the environment. They are case-sensitive and typically written in uppercase letters.

### Common Environment Variables
| **Variable** | **Description**  |
|--------------|------------------|
| `EDITOR`     | The program used to edit files. |
| `HOME`       | The user's home directory. |
| `LOGNAME`    | The user ID or login ID of the current user. |
| `MAIL`       | The location of the user's mailbox on the local system. |
| `OLDPWD`     | The old, or previous, working directory. |
| `PATH`       | The search path for commands. |
| `PAGER`      | The program used for paging through a file. |
| `PS1`        | The primary prompt string. |
| `PWD`        | The present working directory. |

### Viewing Environment Variables
- Use `echo $VAR_NAME` to view the value of a specific environment variable.
- Alternatively, you can use the `printenv` command: `printenv VAR_NAME` to print the value of the variable.
- To display all environment variables, simply run `env` or `printenv` without arguments.

### Setting and Exporting Variables
- You can set an environment variable using:  
  ```bash
  VAR_NAME=value
  ```
- To make the variable available to subprocesses, export it using:
  ```bash
  export VAR_NAME
  ```

### Removing Environment Variables
- To remove an environment variable, use the `unset` command:
  ```bash
  unset VAR_NAME
  ```

---

## Aliases
Aliases allow you to create shortcuts for commands that you frequently use, saving you time and reducing the need for long or complex commands.

### Creating and Managing Aliases
- To create an alias:
  ```bash
  alias alias_name='command'
  ```
  For example, to create an alias for `ls -l`:
  ```bash
  alias ll='ls -l'
  ```

- To list all current aliases:
  ```bash
  alias
  ```

- To remove an alias:
  ```bash
  unalias alias_name
  ```

- To remove all aliases:
  ```bash
  unalias -a
  ```

#### Example Alias Usage:
```bash
# Create an alias for long listing of files
alias ll='ls -lh'

# List all aliases
alias

# Remove the 'll' alias
unalias ll
```

### Persistent Aliases
Aliases are only available for the current session. To make them persistent, add them to your personal initialization files such as `~/.bashrc` or `~/.bash_profile`.

---

## Personal Initialization Files
Personal initialization files are used to save customizations to your shell environment.

### Files Used for Customization
- `~/.bash_profile`: Read and executed for login shells.
- `~/.bashrc`: Read and executed for non-login shells (like when opening a new terminal tab).

To make `~/.bash_profile` source `~/.bashrc`, add the following line to `~/.bash_profile`:
```bash
if [ -f ~/.bashrc ]; then
  . ~/.bashrc
fi
```

### Using the `source` Command
The `source` command allows you to load configurations or scripts into the current shell:
```bash
source ~/.bashrc
```
Alternatively, you can use a dot (`.`) as a shortcut for `source`:
```bash
. ~/.bashrc
```

---

## Shell History
Bash retains the commands you execute during a session in memory, saving them to `~/.bash_history` when the session ends. You can configure the number of commands stored by setting the `HISTSIZE` environment variable.

### Commands for Managing History
- `history`: Displays the list of commands from your shell history.
- `!N`: Repeats the command from line number N in history.
- `!!`: Repeats the last command executed.
- `!pattern`: Repeats the most recent command that starts with the specified pattern.

#### Example:
```bash
history             # Show command history
!100                # Re-run command on line 100
!!                  # Re-run the last command
!grep               # Re-run the last command starting with 'grep'
```

### Searching History
- Press `Ctrl-r` to initiate a reverse search. Keep pressing `Ctrl-r` to continue searching for earlier commands that match the search term.
- Once you find the command, press `Enter` to execute it again, or press `Esc` to edit it before running.

---

## Tab Completion
Tab completion is a powerful feature that allows you to quickly complete commands, file names, and directories by pressing the `Tab` key.

### Example:
1. Type the beginning of a command or file name and press `Tab` to auto-complete.
2. If there are multiple options, press `Tab` twice to list all possibilities.

#### Completing Commands and File Paths
- Type `ls /ho` and press `Tab`. If `/home` exists, it will complete the path.
- Similarly, type `rm /etc/pa` and press `Tab` to complete the file name if it exists.

---

## Line Continuation
To split a long command across multiple lines, use the backslash (`\`) at the end of the line. This allows the command to continue on the next line without being executed until the entire command is complete.

### Example:
```bash
echo "This is a very long line \
that spans multiple lines \
for better readability."
```

This will be interpreted as a single command, and the output will be:
```
This is a very long line that spans multiple lines for better readability.
```

The continued lines will be prefixed with the greater-than symbol (`>`).

---

## Summary of Additional Command Line Concept Commands

| **Command**          | **Description**                                    | **Example Usage**                              |
|----------------------|----------------------------------------------------|------------------------------------------------|
| `echo $VAR_NAME`      | Display the value of an environment variable.      | `echo $HOME`                                   |
| `printenv VAR_NAME`   | Display the value of an environment variable.      | `printenv PATH`                                |
| `env`                 | Display all environment variables.                 | `env`                                          |
| `export VAR_NAME`     | Export an environment variable to be inherited by subprocesses. | `export PAGER=less`                           |
| `unset VAR_NAME`      | Remove an environment variable.                    | `unset PAGER`                                  |
| `alias`               | List all current aliases.                          | `alias`                                        |
| `alias alias_name='command'` | Create an alias for a command.                | `alias ll='ls -l'`                             |
| `unalias alias_name`  | Remove an alias.                                   | `unalias ll`                                   |
| `unalias -a`          | Remove all aliases.                                | `unalias -a`                                   |
| `source ~/.bashrc`    | Execute commands from a file in the current shell. | `source ~/.bashrc`                             |
| `. ~/.bashrc`         | Same as `source`, execute commands from a file in the current shell. | `. ~/.bashrc`                                  |
| `history`             | Show a list of commands from shell history.        | `history`                                      |
| `!N`                  | Repeat the command on line N from history.         | `!100`                                         |
| `!!`                  | Repeat the last executed command.                  | `!!`                                           |
| `!pattern`            | Repeat the last command starting with a specific pattern. | `!grep`                                      |
| `Ctrl-r`              | Initiate a reverse search in shell history.        | `Ctrl-r` (then type part of the command)       |
| `Tab`                 | Auto-complete a command or file path.              | `ls /ho` (press Tab to complete)               |
| `\`                   | Line continuation character for multi-line commands. | `echo "This is a long line \`                   |


# Processes and Jobs 

## Overview

In Linux, processes are the running instances of commands, applications, or programs. The `ps` command is a key tool for viewing information about currently running processes. You can also use other commands like `top`, `htop`, and `pstree` to monitor and manage processes. This chapter covers the `ps` command, which is used for viewing processes, as well as other tools and options to manage and track system activities.

## 1. The `ps` Command

The `ps` (process status) command provides a snapshot of the currently running processes on your system. By default, `ps` shows processes associated with your current terminal session.

### Basic Usage of `ps`

- **Running `ps` without arguments**:
  When you run `ps` without any arguments, it shows processes related to your current terminal session:
  ```bash
  ps
  ```
  Example output:
  ```
  PID TTY          TIME CMD
  1234 pts/0    00:00:05 bash
  5678 pts/0    00:00:00 ps
  ```

- **Display all running processes for your user**:
  To display all processes running under your username, use the following command:
  ```bash
  ps -u username
  ```
  Example:
  ```bash
  ps -u john
  ```

- **Display every process running on the system**:
  To see all processes running on the system, regardless of the user or terminal, use:
  ```bash
  ps -e
  ```
  This shows all processes running across all users and terminals.

### Commonly Used Options with `ps`

The `ps` command has several options to control the level of detail displayed in its output.

| **Description**                         | **Option**       |
|-----------------------------------------|------------------|
| Display all processes                   | `-e`             |
| Use a full-format listing               | `-f`             |
| Display processes for a specific user   | `-u <username>`  |
| Display processes by process ID (PID)   | `-p <PID>`       |
| Display processes in a hierarchical format (tree) | `-H` |
| Display processes in a tree format using ASCII art | `--forest` |

#### Example Commands

- **Display all processes:**
  ```bash
  ps -e
  ```

- **Display all processes with a full format listing:**
  ```bash
  ps -ef
  ```

- **Display processes in a hierarchical (tree) format:**
  ```bash
  ps -eH
  ```

- **Display all processes in a tree format with ASCII art:**
  ```bash
  ps -e --forest
  ```

- **Display processes for a specific user:**
  ```bash
  ps -u <username>
  ```

- **Display information for a specific process ID (PID):**
  ```bash
  ps -p 1234
  ```

## 2. `pstree` Command

The `pstree` command is another tool that displays running processes in a tree-like format. It is similar to the `ps -H` or `ps --forest` command options but with a more visually structured output. Unlike `ps`, `pstree` provides a continuous, updated process tree.

To use `pstree`:
```bash
pstree
```

This will display all processes in a hierarchical tree structure.

### Example:
```bash
pstree
```
Example output:
```
init─┬─bash─┬─ps
     └─sshd─┬─sshd───bash───pstree
```

## 3. Real-Time Process Monitoring with `top` and `htop`

While `ps` gives a snapshot of processes at a specific moment, `top` and `htop` are dynamic tools that display processes in real-time, refreshing periodically.

### The `top` Command

`top` is a command-line utility that provides an overview of the system's performance and real-time process monitoring.

- **Basic usage of `top`**:
  ```bash
  top
  ```
  This displays a continuously updating list of processes sorted by CPU usage by default.

- **Interactive Options in `top`**:
  While `top` is running, you can press the following keys to interact with the process list:
  - `P`: Sort processes by CPU usage.
  - `M`: Sort processes by memory usage.
  - `k`: Kill a process by specifying its PID.
  - `q`: Quit `top`.

### The `htop` Command

`htop` is an improved, interactive version of `top` with a more user-friendly interface and additional features like color coding. However, it is not installed by default on all distributions, so you may need to install it first.

- **Install `htop`**:
  ```bash
  sudo apt install htop  # For Ubuntu/Debian-based systems
  sudo yum install htop  # For CentOS/RHEL-based systems
  ```

- **Run `htop`**:
  ```bash
  htop
  ```

### Differences between `top` and `htop`

| Feature              | `top`                 | `htop`                   |
|----------------------|-----------------------|--------------------------|
| User Interface       | Text-based, simple    | Interactive, colorful UI |
| Process Tree         | No                    | Yes                      |
| Sort Process by CPU  | Yes                   | Yes                      |
| Sort Process by Memory | Yes                  | Yes                      |
| Kill Processes       | Yes                   | Yes                      |
| Install by Default   | Yes                   | No (needs installation)  |

### Example Workflow for Process Management

1. **List all processes**:
   ```bash
   ps -e
   ```

2. **Get a detailed view of a specific process (e.g., PID 1234)**:
   ```bash
   ps -p 1234 -f
   ```

3. **Monitor processes in real-time**:
   ```bash
   top
   ```

4. **Kill a process** (for example, PID 5678):
   ```bash
   kill 5678
   ```

5. **Monitor system in a more user-friendly way (install and run `htop`)**:
   ```bash
   sudo apt install htop
   htop
   ```

## Jobs - In-Depth Summary

### Overview

In Linux, when you execute a command at the terminal, it runs in the foreground by default, meaning it occupies the terminal session and prevents you from entering other commands until it finishes. However, sometimes you may want to run a long-running task but continue working on other tasks in the meantime. To achieve this, you can run processes in the background or suspend and manage jobs using job control commands.

This section covers how to control jobs in a Linux environment, including how to start jobs in the background, manage job statuses, suspend, resume, and kill jobs, and use the `fg`, `bg`, and `kill` commands effectively.

### 1. Running Jobs in the Background

When you start a command in the background, the terminal immediately returns the prompt, allowing you to continue executing other commands. To start a command in the background, you append an ampersand (`&`) to the command:

```bash
command &
```

#### Example:
```bash
sleep 30 &
```
In this example, the `sleep 30` command will run in the background for 30 seconds while you are free to use the terminal for other tasks.

When a command runs in the background, two pieces of information are displayed: the **job number** and the **process ID (PID)**. The job number is enclosed in square brackets, and the PID is shown next to it.

Example output:
```bash
[1] 12345
```
Here, `1` is the job number, and `12345` is the process ID of the background job.

#### Job Control Table

| **Description**                                   | **Command**          |
|---------------------------------------------------|----------------------|
| Start command in the background                   | `command &`          |
| Kill the foreground process                       | `Ctrl-C`             |
| Suspend the foreground process                    | `Ctrl-Z`             |
| Background a suspended process                    | `bg [%num]`          |
| Foreground a backgrounded process                 | `fg [%num]`          |
| Kill a process by job number or PID               | `kill [%num]` or `kill <PID>` |
| List all jobs or a specific job by job number     | `jobs [%num]`        |

### 2. Job Status and Job Numbers

The `jobs` command lists all the jobs running in the background or suspended. The job numbers are displayed in square brackets. Jobs that are running or stopped are listed with their status.

Example output:
```bash
[1]+  12345 Running                 sleep 30 &
[2]-  12346 Stopped                 nano
```
- The job number `[1]` is running (`Running`).
- The job number `[2]` is stopped (`Stopped`).

#### Understanding the Job Status Symbols

- **`+`**: Indicates the current job.
- **`-`**: Indicates the previous job.

These symbols help you identify which job is currently active or was last active.

### 3. Managing Jobs with `fg` and `bg`

You can control jobs that are running in the background or that have been suspended by bringing them to the foreground or resuming them in the background.

#### 3.1 Foregrounding a Job

To bring a background job to the foreground, use the `fg` command followed by the job number.

```bash
fg %1
```

Alternatively, you can use shorthand notation to refer to the current job using `%%` or `%+` and bring it to the foreground:
```bash
fg %%
```
This will bring the most recently started or suspended job to the foreground.

#### 3.2 Backgrounding a Suspended Job

If a job is suspended (e.g., using `Ctrl-Z`), you can resume it in the background by using the `bg` command followed by the job number.

```bash
bg %1
```

If you want to resume the most recently suspended job in the background, simply use `bg` without specifying the job number:

```bash
bg
```

This will resume the last suspended job in the background.

#### Example:

1. **Suspending a job**:
   ```bash
   sleep 30
   ```
   Press `Ctrl-Z` to suspend it.

2. **Resume the suspended job in the background**:
   ```bash
   bg
   ```

3. **Bring the background job to the foreground**:
   ```bash
   fg
   ```

### 4. Killing Jobs

To terminate a job, you can use the `kill` command. This command sends a signal to a process, and by default, the signal is `SIGTERM` (termination).

#### 4.1 Killing Foreground Jobs

To kill a foreground job, you can simply press `Ctrl-C`. This sends the `SIGINT` signal (interrupt), which immediately stops the process.

#### 4.2 Killing Background Jobs by Job Number or PID

To kill a background job, use the `kill` command followed by the job number or process ID (PID). 

To kill a job by job number:
```bash
kill %1
```

To kill a job by its PID:
```bash
kill 12345
```

You can also use `kill -l` to list all the available signals that can be sent to a process.

#### 4.3 Sending Specific Signals

The `kill` command can send different types of signals. By default, `kill` sends `SIGTERM` (signal 15) to gracefully terminate the process. If the process does not terminate after receiving `SIGTERM`, you can forcefully terminate it by sending `SIGKILL` (signal 9).

To send `SIGTERM` (default):
```bash
kill %1
```

To send `SIGKILL` to forcefully kill a job:
```bash
kill -9 %1
```

#### 4.4 Listing Signals with `kill -l`

To view a list of all available signals, use the `kill -l` command:

```bash
kill -l
```

Example output:
```bash
1) SIGHUP    2) SIGINT    3) SIGQUIT   9) SIGKILL   15) SIGTERM
```

You can use these signal names or numbers to control the behavior of the `kill` command.

### 5. Practical Examples of Job Control

#### Example 1: Starting a Process in the Background
```bash
sleep 60 &
```

Output:
```bash
[1] 12345
```
The `sleep 60` command runs in the background, and its job number is `1` with PID `12345`.

#### Example 2: Listing Jobs
```bash
jobs
```

Output:
```bash
[1]+  12345 Running                 sleep 60 &
[2]-  12346 Stopped                 nano
```

#### Example 3: Suspending a Job
Run a command and suspend it:
```bash
nano myfile.txt
```
Press `Ctrl-Z` to suspend.

#### Example 4: Resume Suspended Job in the Background
```bash
bg %2
```

#### Example 5: Bring Job to Foreground
```bash
fg %1
```

#### Example 6: Kill a Job by Job Number
```bash
kill %1
```

#### Example 7: Kill a Job by PID
```bash
kill 12345
```

#### Example 8: Force Kill a Job
```bash
kill -9 %1
```

## Summary of Process and Job Control Commands

| **Command**               | **Description**                                                                 | **Example**                                               |
|---------------------------|---------------------------------------------------------------------------------|-----------------------------------------------------------|
| `ps`                       | Lists running processes on the system.                                           | `ps`                                                      |
| `ps -e`                    | Displays all processes running on the system.                                    | `ps -e`                                                   |
| `ps -ef`                   | Displays all processes with a full format listing.                               | `ps -ef`                                                  |
| `ps -eH`                   | Displays processes in a hierarchical (tree) format.                              | `ps -eH`                                                  |
| `ps -e --forest`           | Displays processes in a tree format using ASCII art.                            | `ps -e --forest`                                          |
| `ps -u <username>`         | Displays processes running for a specific user.                                 | `ps -u john`                                              |
| `ps -p <PID>`              | Displays information for a specific process ID (PID).                           | `ps -p 1234`                                              |
| `pstree`                   | Displays processes in a hierarchical tree format.                               | `pstree`                                                  |
| `top`                      | Displays a real-time process list with system performance information.          | `top`                                                     |
| `htop`                     | Interactive and improved version of `top` with a user-friendly interface.       | `htop`                                                    |
| `kill <PID>`               | Terminates a running process using its process ID (PID).                        | `kill 5678`                                               |
| `sudo apt install htop`    | Installs `htop` on a Debian-based system.                                        | `sudo apt install htop`                                   |
| Start a command in the background                 | `command &`                | `sleep 60 &`                                  |
| Kill the foreground process                       | `Ctrl-C`                   | (Press `Ctrl-C` while the job is in the foreground) |
| Suspend the foreground process                    | `Ctrl-Z`                   | (Press `Ctrl-Z` while the job is running)     |
| Resume a suspended job in the background          | `bg [%num]`                | `bg %1`                                       |
| Resume the most recently suspended job in the background | `bg`                     | `bg`                                          |
| Bring a backgrounded job to the foreground        | `fg [%num]`                | `fg %1`                                       |
| Bring the most recent background job to the foreground | `fg`                     | `fg`                                          |
| Kill a job by job number or PID                   | `kill [%num]` or `kill <PID>` | `kill %1` or `kill 12345`                    |
| List all jobs or a specific job by job number     | `jobs` or `jobs [%num]`    | `jobs` or `jobs %1`                           |
| List available signals                            | `kill -l`                  | `kill -l`                                     |
| Send a specific signal to a job                   | `kill -<signal> %num` or `kill -<signal> <PID>` | `kill -9 %1` or `kill -9 12345`             |
| Force kill a job (SIGKILL signal)                 | `kill -9`                  | `kill -9 %1`                                  |

---

# Switching Users

In Linux, switching between users or performing administrative tasks requires specific commands. Let's look at two important commands: `su` (Switch User) and `sudo` (Super User Do).

## Switching Users with `su` (Switch User)

The `su` command is used to switch between users in a Linux system. By default, `su` switches to the superuser (root). You can also use `su` to switch to any specific user by providing their username as an argument.

### Common `su` Usage

- **Switch to Root**:  
  The `su` command without any arguments switches to the root user.
  ```bash
  $ su
  ```
  The above command may give error: 
  ```bash
  $ su
  Password: 
  su: Authentication failure
  ```
  On many modern Linux distributions, the root account is disabled by default for security reasons. In this case, you might need to use sudo to gain root privileges instead of su. Ensure to enter the current user's password and not the superuser.
  ```bash
  $ sudo su
  root@envy:/home/sri/Documents/Linux# 
  ```

- **Switch to a Specific User**:  
  To switch to a specific user, use the command `su [username]`. Enter the **switching user**'s password and not current user's password. 

  In the below example you will have to enter switching user, `ram`'s passowrd. 
  ```bash
  sri@envy:~/Documents/Linux
  $ su ram
  Password: 
  ram@envy:/home/sri/Documents/Linux$ 
  ```
  Also notice that you are still the same directory as before. 

  To quit from this user (`ram` here) account: 
  ```bash
  ram@envy:/home/sri/Documents/Linux$ exit
  exit
  sri@envy:~/Documents/Linux
  $ 
  ```
  
  Another way of logging to another user is through `sudo su [username]`, use the **current user**'s password. 

  In the below example you will have to enter current user, `sri`'s password. 
  ```bash
  sri@envy:~/Documents/Linux
  $ sudo su ram
  [sudo] password for sri: 
  ram@envy:/home/sri/Documents/Linux$ 
  ```

- **Simulate Logging In as a User**:  
  By adding a hyphen (`-`), you simulate logging in directly as that user. This changes your environment variables and your working directory to the user’s home directory. **While the previous method don't change the working directory.** 
  ```bash
  sri@envy:~/Documents/Linux
  $ sudo su - ram
  [sudo] password for sri: 
  ram@envy:~$ 
  ```
- **Excuting command as another user**: 
  By using `-c` option with `su` we can execute command as another user. 
  ```bash
  sri@envy:~/Documents/Linux
  $ su - ram # swtiching to ram
  Password: 
  ram@envy:~$ echo "I am ram" > a.txt # creating a file
  ram@envy:~$ exit # switch back to sri
  logout
  # this below command will not work, since it logins and stays in /home/sri/Documents/Linux
  sri@envy:~/Documents/Linux
  $ su ram -c "cat a.txt" 
  Password: 
  cat: a.txt: No such file or directory

  # this below command will WORK, since it logins and stays in ~ram
  sri@envy:~/Documents/Linux
  $ su ram -c "cat ~/a.txt"
  Password: 
  I am ram
  sri@envy:~/Documents/Linux # haven't switched to ram, still in sri
  $ 
  ```
---

### Common `su` Options

| Option| Description|
|-------|------------|
| `su -`        | Simulates a login as the user, setting the working directory and environment. |
| `su -c`       | Runs a specified command as another user. The command needs to be quoted if it contains spaces. |
| `su [user]`   | Switch to the specified user. Without the hyphen, the environment and directory remain unchanged. |

**In all the above case, we will use the switching user's password.**

We can also prefix the above commands with **sudo**, where we will use **current user's password**.

---

### Checking Current User

To check which user you are currently working as, use the `whoami` command:
```bash
$ whoami
# Output: jason
```
After switching to another user with `su`, `whoami` will show the new user:
```bash
$ su ram
Password:
whoami
# Output: ram
```

---

## `sudo` (Super User Do)

The `sudo` command allows a permitted user to execute a command as another user, typically the root user, without switching users entirely. It’s often used for administrative tasks, such as installing software or managing system services, that require superuser privileges.

---

### Why Use `sudo` Over `su`?

- **Password Requirements**: `sudo` asks for the current user's password, while `su` requires the password of the user you're switching to (typically the root user).
- **Security**: `sudo` allows more granular control over which commands can be executed with elevated privileges, reducing the need for shared or generic root passwords.
- **Logging and Auditing**: `sudo` provides better logging of commands that require elevated privileges, which is helpful for security audits.
- **One-Time Commands**: `sudo` is typically used for a single command, while `su` changes the shell to the target user, allowing multiple commands to be executed.

---

### Common `sudo` Usage

| Command| Description| Example|
|--------|------------|--------|
| `sudo -l`| List commands that can be run with `sudo`| `sudo -l`|
| `sudo command`| Run a command with superuser privileges| `sudo apt update`|
| `sudo -u user command`| Run a command as a specific user (other than root)| `sudo -u ram whoami`|
| `sudo su`| Switch to the superuser account (root)| `sudo su`|
| `sudo su -`| Switch to the **superuser account (root)** with the user's environment| `sudo su -`|
| `sudo su - username`| Switch to a **specific user’s account** with that user's environment| `sudo su - ram`|

---

### Example of Using `sudo`

1. **Run a Command as Root**:
   ```bash
   sudo /etc/init.d/apache2 start
   # Output: Starting web server apache2
   ```

2. **Run a Command as Another User**:
   ```bash
   sudo -u fred /opt/fredsApp/bin/start
   # Output: Fred's app started as user fred.
   ```

3. **Switch to ram User as Root**:
   ```bash
   sri@evny:~
   $ sudo su - ram
   [sudo] password for ram:
   
   ram@envy:~
   $ whoami
   ram
   
   ram@envy:~
   $ exit
   
   sri@envy:~
   $
   ```
---

## Summary of Differences Between `su` and `sudo`

| Feature             | `su`                                                | `sudo`                                             |
|---------------------|------------------------------------------------------|----------------------------------------------------|
| **Password Prompt**  | Requires the target user’s password (e.g., root).    | Requires the current user’s password.              |
| **Command Scope**    | Changes the current shell to the target user’s shell. | Runs a single command as the specified user.       |
| **Security**        sudo su ram | Requires sharing of passwords for different users.   | Provides better control and logging of commands.   |
| **Usage**            | Best for switching users to run multiple commands.   | Best for executing one-off commands with elevated privileges. |

`sudo` is generally preferred over `su` for security reasons, as it reduces the risk of exposing root passwords and provides better auditing and control over user actions.

## Summary of Switching User Commands

| Command| Description| Example Usage|
|--------|------------|--------------|
| `su`| Switch to the superuser (root) or another specified user.| `su` or `su ram`|
| `su -`| Switch to the specified user with their environment (login shell).     | `su - ram`|
| `su -c 'command'`| Run a command as another user, with their environment.| `su -c 'echo $ram_HOME' ram`           |
| `whoami`| Display the current user’s name.| `whoami`|
| `sudo`| Execute a command with superuser privileges or as another user.        | `sudo ls`|
| `sudo -l`| List the commands available to run with `sudo`.| `sudo -l`|
| `sudo command`| Run a command with superuser privileges.| `sudo apt-get update`|
| `sudo -u user command`| Run a command as another user (other than root).| `sudo -u fred /opt/fredsApp/bin/start`       |
| `sudo su`| Switch to the superuser account (root) with the current shell.         | `sudo su`|
| `sudo su -`| Switch to the superuser account (root) with a login shell.| `sudo su -`|
| `sudo su - username`| Switch to the specified user's account with a login shell.| `sudo su - ram`|
| `sudo visudo`| Edit the sudoers file for configuration.| `sudo visudo`|

---

# Installing Software

Software installation on Linux is commonly done through packages, which contain both the software files and additional metadata (such as installation scripts, version info, dependencies, and more). A package manager handles the installation, upgrading, and removal of software and maintains a database of installed packages and their dependencies.

## DEB-Based Distributions

Linux distributions based on Debian use the DEB package format. Popular Debian-based distributions include **Debian**, **Ubuntu**, **Linux Mint**, and **Elementary OS**. The package manager used is **APT** (Advanced Packaging Tool). 

### Common APT Commands

Here's the table converted to use only `sudo apt` commands:

| Command                      | Description                                                                         | Example                          |
|------------------------------|-------------------------------------------------------------------------------------|----------------------------------|
| `sudo apt update`                 | Update package list and metadata from repositories                                | `sudo apt update`                |
| `sudo apt upgrade`                | Upgrade all installed packages to the latest available versions                   | `sudo apt upgrade`               |
| `sudo apt autoremove`             | Remove unnecessary packages that were installed as dependencies but are no longer needed | `sudo apt autoremove`     |
| `sudo apt clean`                  | Clear the local repository cache to free up space                                 | `sudo apt clean`                 |
| `sudo apt search search-pattern` | Search for packages matching the search pattern                                   | `sudo apt search web browser`    |
| `sudo apt install package`        | Install a package| `sudo apt install firefox`       |
| `sudo apt install -y package`     | Install a package and automatically answer "yes" to prompts                       | `sudo apt install -y firefox`    |
| `sudo apt remove package`         | Remove a package, leaving behind configuration files                              | `sudo apt remove firefox`        |
| `sudo apt purge package`          | Remove a package, including its configuration files                               | `sudo apt purge firefox`         |
| `sudo apt show package`           | Display detailed information about a package                                      | `sudo apt show firefox`          |
| `sudo apt full-upgrade`           | Perform an upgrade with more aggressive handling of dependencies                   | `sudo apt full-upgrade`          |

### Example Workflow: Installing and Managing GIMP (GNU Image Manipulation Program)

1. **Update package list**:  
   Before installing or managing any package, ensure the package list is up to date:
   ```bash
   $ sudo apt update
   $ sudo apt upgrade -y
   ```

2. **Search for a package**:  
   To search for packages related to "image editor":
   ```bash
   $ sudo apt search image editor
   ```

3. **Display package details**:  
   To view detailed information about the GIMP package:
   ```bash
   $ sudo apt show gimp
   ```

4. **Install a package**:  
   To install GIMP:
   ```bash
   $ sudo apt install gimp
   ```

5. **Upgrade installed packages**:  
   To upgrade all installed packages to their latest versions:
   ```bash
   $ sudo apt upgrade
   ```

6. **Full upgrade (handle dependencies)**:  
   To perform an upgrade with more aggressive dependency handling:
   ```bash
   $ sudo apt full-upgrade
   ```

7. **Remove a package**:  
   To remove GIMP while keeping its configuration files:
   ```bash
   $ sudo apt remove gimp
   ```

8. **Purge a package**:  
   To completely remove GIMP along with its configuration files:
   ```bash
   $ sudo apt purge gimp
   ```

9. **Clean up unnecessary packages**:  
   To remove packages that are no longer needed as dependencies:
   ```bash
   $ sudo apt autoremove
   ```

10. **Clear the package cache**:  
    To free up disk space by clearing the local repository cache:
    ```bash
    $ sudo apt clean
    ```
---

### What is the difference between `apt upgrade` and `apt full-upgrade`?

- **`sudo apt upgrade`**:
  - This command upgrades all the currently installed packages to their latest versions, but **without removing** any installed packages or adding new ones. If a package upgrade requires removing other packages, it will **not be installed**.
  - Essentially, it only upgrades packages that can be updated without causing any dependency issues.
  
- **`sudo apt full-upgrade`** (formerly `dist-upgrade`):
  - This command performs a more **aggressive upgrade** by upgrading all installed packages **and** also handling changes in dependencies, such as:
    - Removing packages that are no longer required.
    - Installing new dependencies required by upgraded packages.
  - If upgrading a package requires removing others or installing additional packages, `full-upgrade` will allow it.

#### Key Differences:
- **`apt upgrade`**: Only upgrades packages and won't remove or install anything unless it's necessary for the upgrade of an existing package.
- **`apt full-upgrade`**: Upgrades packages and **may remove or install packages** to resolve dependencies and ensure a successful upgrade.

---

### What is the difference between `apt` and `apt-get`?

| **Feature**               | **`apt`**                             | **`apt-get`**                        |
|---------------------------|---------------------------------------|--------------------------------------|
| **User Focus**            | Designed for end-users with a simpler and cleaner interface. | Designed for scripts and advanced users. |
| **Default Output**        | Provides a more user-friendly and colored output. | Outputs detailed but less formatted information. |
| **Commands**              | Combines commands like `install`, `remove`, `update`, `upgrade`, etc. | Requires separate commands for some actions, like `apt-get` and `apt-cache`. |
| **Introduced In**         | Ubuntu 16.04+ / Debian 8+             | Older tool, part of APT package manager since inception. |
| **Use Case**              | Recommended for interactive use.       | Recommended for scripting and backward compatibility. |

#### **Key Commands Comparison**

| Task                     | `apt` Command          | `apt-get` Command     |
|--------------------------|------------------------|-----------------------|
| Install a package        | `sudo apt install`     | `sudo apt-get install` |
| Remove a package         | `sudo apt remove`      | `sudo apt-get remove` |
| Update package list      | `sudo apt update`      | `sudo apt-get update` |
| Upgrade installed packages | `sudo apt upgrade`   | `sudo apt-get upgrade` |
| Full system upgrade      | `sudo apt full-upgrade` | `sudo apt-get dist-upgrade` |

**Summary**: Use `apt` for day-to-day tasks and `apt-get` for scripting or advanced operations.

---

### Managing DEB Packages Directly with `dpkg`

While `apt` is the most common tool for package management, you can interact directly with the **DEB package manager** using `dpkg`.  

| Command                     | Description                                                     |
|-----------------------------|-----------------------------------------------------------------|
| `dpkg -l`                  | List all installed packages.                                    |
| `dpkg -S /path/to/file`    | Find the package that provides a specific file.                 |
| `sudo dpkg -i package.deb` | Install a package from a `.deb` file.                          |
| `dpkg -L <package>`         | List all files installed by a package.                         |

#### Example Workflow with `dpkg`

1. **Install a `.deb` package**:  
   Download and install a `.deb` file:
   ```bash
   sudo dpkg -i package.deb
   ```

2. **Fix broken dependencies (if needed)**:  
   If the above command fails due to unmet dependencies, run:
   ```bash
   sudo apt install -f
   ```

3. **List installed files for a package**:  
   To see which files a package has installed:
   ```bash
   dpkg -L <package>
   ```

4. **Find a package by file**:  
   To identify which package installed a specific file:
   ```bash
   dpkg -S /path/to/file
   ```

---

### What is the difference between `apt` and `dpkg`?

| **Feature**               | **`apt`**                                 | **`dpkg`**                             |
|---------------------------|-------------------------------------------|---------------------------------------|
| **Purpose**               | High-level package manager for managing packages (installing, upgrading, searching, etc.) with dependency resolution. | Low-level package manager for installing, removing, and inspecting `.deb` packages without resolving dependencies. |
| **Dependency Handling**   | Automatically handles dependencies during package installation and removal. | Does not manage dependencies; errors occur if dependencies are missing. |
| **Interface**             | User-friendly commands like `install`, `update`, `upgrade`, etc. | Requires direct interaction with `.deb` files using precise commands. |
| **Use Case**              | Used for managing packages from repositories and performing system-wide package management. | Used for manual installation or troubleshooting specific `.deb` files. |
| **Example Commands**      | `sudo apt install firefox`                | `sudo dpkg -i firefox.deb`           |

**Summary**: Use `apt` for general package management and `dpkg` for direct `.deb` file manipulation or troubleshooting.

## Summary of Installing Software Commands

| **Command**                     | **Description**                                                        | **Example**                          |
|----------------------------------|------------------------------------------------------------------------|--------------------------------------|
| `sudo apt update`                | Update package list and metadata from repositories                     | `sudo apt update`                   |
| `sudo apt upgrade`               | Upgrade all installed packages to the latest available versions        | `sudo apt upgrade`                  |
| `sudo apt autoremove`            | Remove unnecessary packages that were installed as dependencies but are no longer needed | `sudo apt autoremove`            |
| `sudo apt clean`                 | Clear the local repository cache to free up space                      | `sudo apt clean`                    |
| `sudo apt search search-pattern` | Search for packages matching the search pattern                        | `sudo apt search web browser`       |
| `sudo apt install package`       | Install a package                                                      | `sudo apt install firefox`          |
| `sudo apt install -y package`    | Install a package and automatically answer "yes" to prompts            | `sudo apt install -y firefox`       |
| `sudo apt remove package`        | Remove a package, leaving behind configuration files                   | `sudo apt remove firefox`           |
| `sudo apt purge package`         | Remove a package, including its configuration files                    | `sudo apt purge firefox`            |
| `sudo apt show package`          | Display detailed information about a package                           | `sudo apt show firefox`             |
| `sudo apt full-upgrade`          | Perform an upgrade with more aggressive handling of dependencies        | `sudo apt full-upgrade`             |
| `dpkg -l`                        | List all installed packages.                                           | `dpkg -l`                           |
| `dpkg -S /path/to/file`          | Find the package that provides a specific file.                        | `dpkg -S /path/to/file`             |
| `sudo dpkg -i package.deb`       | Install a package from a `.deb` file.                                  | `sudo dpkg -i package.deb`          |
| `dpkg -L <package>`              | List all files installed by a package.                                 | `dpkg -L <package>`                 |
| **Example Workflow with `dpkg`** | **Description**                                                        | **Command**                          |
| Install a `.deb` package         | Install a `.deb` file.                                                 | `sudo dpkg -i package.deb`          |
| Fix broken dependencies          | Fix unmet dependencies after installing a `.deb` package.              | `sudo apt install -f`               |
| List installed files for a package | View which files a package has installed.                              | `dpkg -L <package>`                 |
| Find a package by file           | Identify which package installed a specific file.                      | `dpkg -S /path/to/file`             |