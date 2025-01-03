# Table of Contents
* [Introduction](#Introduction)
* [Linux Directory Structure](#Linux-Directory-Structure)
  * [Summary](#Summary-of-Linux-Directory-Structure)
* [Command Line Interface](#Command-Line-Interface)
* [Basic Commands](#Basic-Commands)
  * [Summary](#Summary-of-Basic-Commands)
* [Directories](#Directories)
  * [Summary](#Summary-of-Directory-Commands)
* [Viewing File and Directory Details](#Viewing-File-and-Directory-Details)
  * [Summary](#summary-of-viewing-file-and-directory-commands)
* [Permissions](#Permissions)
  * [Summary](#summary-of-permissions-commands)
* [Viewing and Editing Files](#Viewing-and-Editing-Files)
  * [Summary](#summary-of-viewing-files)
* [The Vim Editor](#the-vim-editor)
  * [Summary](#Summary-of-Vim-Commands)
* [The Vim Editor](#the-vim-editor)
  * [Summary](#summary-of-vim-commands)
* [Deleting, Moving, and Renaming Files and Directories](#deleting-moving-and-renaming-files-and-directories)
  * [Summary](#Summary-of-Deleting-Moving-and-Renaming-Files-and-Directories-Commands)
* [Finding, Sorting, and Comparing Files and Directories](#finding-sorting-and-comparing-files-and-directories)
  * [Summary](#Summary-of-Finding-Sorting-and-Comparing-Files-and-Directories)
* [I/O Redirection](#io-redirection)
  * [Summary](#Summary-of-IO-Redirection-Commands)
* [Additional Command Line Concepts](#Additional-Command-Line-Concepts)
  * [Summary](#Summary-of-Additional-Command-Line-Concept-Commands)
* [Processes and Jobs](#Processes-and-Jobs)
  * [Summary](#Summary-of-Processes-and-Jobs-Control-Commands)
* [Switching Users](#Switching-Users)
  * [Summary](#Summary-of-Switching-User-Commands)
* [Installing Software](#Installing-Software)
  * [Summary](#Summary-of-Installing-Software-Commands)
* [**CheatSheet**](#Cheat-Sheet)
---

# Introduction  

## What is Linux?  
Linux is a **Unix-like open-source operating system** renowned for its flexibility, security, and extensive community support. At its core is the **[Linux kernel](https://github.com/torvalds/linux)**, the foundational component that bridges the gap between applications and hardware. The kernel manages system resources, ensures hardware-software communication, and provides essential services like memory management and process control.  

### Key Characteristics of Linux  
- **Unix-like**: Shares architectural and conceptual similarities with Unix.  
- **Open Source**: Freely available for use, modification, and distribution.  
- **Kernel-Centric**: The kernel serves as the foundation of the operating system.  

---

## A Brief History of Linux  
Linux was created in **1991** by **Linus Torvalds**, a Finnish computer science student, as a personal project to develop a free and open-source alternative to proprietary Unix systems. Inspired by **Minix**, a Unix-like system for educational purposes, Torvalds initially released the kernel under a proprietary license but soon adopted the **GNU General Public License (GPL)**. This move aligned Linux with the **GNU Project**, initiated by **Richard Stallman**, which aimed to create a completely free operating system.  

Since its inception, Linux has evolved through collaboration between Torvalds and a global community of developers. Today, it powers desktops, servers, embedded systems, and supercomputers, becoming one of the most versatile and widely used operating systems.  

---

## Linux Distributions  
A **Linux distribution (distro)** is a complete operating system built around the Linux kernel. Distributions bundle essential software, tools, and utilities tailored to various purposes, creating a cohesive and usable environment.  

### Features of Linux Distributions  
1. **Shared Core**: All distributions are built on the Linux kernel.  
2. **Custom Software**: Each distribution bundles software, tools, and configurations based on its focus.  
3. **Targeted Use Cases**: Some distributions cater to **desktops** (e.g., Linux Mint), others to **servers** (e.g., CentOS, RHEL), while some serve both (e.g., Ubuntu).  
4. **Support Models**: Distributions are maintained by either **community** volunteers or **corporations** offering professional support.  

### Popular Linux Distributions  

| **Distribution**| **Primary Usage** | **Support Model**| **Notes** |
|--------------------------|-------------------|-----------------------|---------------------------------------------------------------------------|
| **Linux Mint**   | Desktop   | Community | User-friendly, ideal for beginners.   |
| **Ubuntu**   | Both  | Community | Widely used with LTS versions for stability.  |
| **Debian**   | Both  | Community | Stable and reliable, popular for servers. |
| **Fedora**   | Both  | Community | Cutting-edge features, upstream for RHEL. |
| **openSUSE** | Both  | Community/Corporate   | Offers Leap (stable) and Tumbleweed (rolling release) versions.   |
| **Arch Linux**   | Desktop   | Community | Minimalist and highly customizable.   |
| **CentOS**   | Server| Community | RHEL-based, stable, enterprise-ready. |
| **RHEL** | Server| Corporate | Commercial support for enterprise environments.   |
| **Manjaro**  | Desktop   | Community | Arch-based with user-friendly tools.  |
| **Elementary OS**| Desktop   | Community | Aesthetic design, excellent for newcomers.|
| **Kali Linux**   | Desktop   | Community | Specialized for penetration testing and security tasks.   |
| **Zorin OS** | Desktop   | Community | Perfect for users transitioning from Windows. |
| **Pop!_OS**  | Desktop   | Community | Developer- and gamer-friendly, based on Ubuntu.   |
| **AlmaLinux**| Server| Community | RHEL clone, focused on enterprise users.  |
| **Slackware**| Both  | Community | Traditional UNIX-like experience. |
| **MX Linux** | Desktop   | Community | Lightweight and efficient for older hardware. |

**Legend**:  
- **Desktop**: Tailored for personal or workstation use.  
- **Server**: Designed for stability, often used in enterprise or hosting environments.  
- **Community**: Developed and maintained by volunteers.  
- **Corporate**: Backed by companies providing commercial support.  

---

## Why Learn Linux?  
The core principles and functionalities of Linux remain consistent across distributions, making it a universal skill for tech enthusiasts and professionals. Linux powers:  
- **90% of the world's supercomputers**,  
- **96.3% of the top 1 million web servers**,  
- **74% of smartphones (via Android)**.  

Its unmatched flexibility, security, and open-source nature have made Linux a cornerstone of modern technology. Learning Linux opens doors to diverse career opportunities and empowers you to work efficiently in today's computing environments.  

---  

# Linux Directory Structure

The Linux directory structure is hierarchical, resembling an inverted tree with the **root** or **trunk** (`/`) as its base. All directories branch off from the root, with forward slashes (`/`) separating directories.

**Directory** is nothing but a linux jargon for **folder**.

## Common Top-Level Directories

### `/` Root Directory
The root of the Linux file system, often referred to as the **slash (/)** or the **trunk**, serves as the starting point for all files and directories. Everything in Linux resides under `/`. This is similar to `C:\` in Windows. However, unlike Windows, where additional storage is assigned drive letters like `D:\`, Linux mounts additional storage devices as subdirectories, typically under locations like `/mnt` or `/media`.

```bash
$ ls /
bin                dev   lib64              mnt   run                 srv       usr
bin.usr-is-merged  etc   lib.usr-is-merged  opt   sbin                swap.img  var
boot               home  lost+found         proc  sbin.usr-is-merged  sys
cdrom              lib   media              root  snap                tmp
```

### `/bin` Binaries
Contains **essential executable programs** (e.g., basic commands like `ls`, `cp`). Additional non-essential binaries like graphical apps, mail, and trivial cmd utitlies are found in `/usr/bin`.
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
Houses **configuration files** that controls how the operating system and applications (e.g., boot modes, nareetwork settings) behave.
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
Each user on a Linux system has a subdirectory dedicated to their account in the /home directory. For example,Example: `/home/sri`.
```bash
$ ls /home/
sri
```

### `/opt` Optional or Third-Party Software
Used for **software not bundled with the operating system**, like Google Chrome.

**Fact** - Firefox comes builtin with the operating system. 
```bash
$ whereis firefox
firefox: /usr/bin/firefox /snap/bin/firefox
```

### `/tmp` Temporary Files
Temporary workspace for applications and users. Files here are **cleared at boot time**.
```bash
$ ls /tmp
snap-private-tmp
systemd-private-9e8bed51413f4d929422b8d7d854bbcd-bluetooth.service-rcvxLj
systemd-private-9e8bed51413f4d929422b8d7d854bbcd-colord.service-1fPQpU
systemd-private-9e8bed51413f4d929422b8d7d854bbcd-fwupd.service-RclrPC
systemd-private-9e8bed51413f4d929422b8d7d854bbcd-ModemManager.service-ItsVvS
...
```

### `/usr` - User-Related Data  
The `/usr` directory contains user-related programs and **read-only data**, which are not essential for the operating system's core functionality. Subdirectories include:
- `/usr/bin`: Executable programs.
- `/usr/lib`: Libraries.
- `/usr/share/doc`: Shared documentation and resources.

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
#### `/usr/share/doc`
```bash
$ ls /usr/share/doc
accountsservice                                libmpc3
acl                                            libmpcdec6
adduser                                        libmpeg2-4
adwaita-icon-theme                             libmpfr6
alsa-base                                      libmpg123-0t64
alsa-topology-conf                             libmsgraph-0-1
alsa-ucm-conf                                  libmtdev1t64
alsa-utils                                     libmtp9t64
amd64-microcode                                libmtp-common
anacron                                        libmtp-runtime
apg                                            libmutter-14-0
apparmor                                       libmysofa1
apport                                         libnautilus-extension4
apport-core-dump-handler                       libncurses6
apport-gtk                                     libncursesw6
...
```

### What is the difference between `/bin` and `/usr/bin`?

#### `/bin` (Essential Binaries)
- **Purpose**: Contains essential binaries required for the system to function, especially during boot or when the system is in single-user mode.
- **Availability**: These binaries are available even if the `/usr` directory is not mounted.
- **Usage**: Includes basic commands that are needed for system recovery, maintenance, and basic user interaction.
- **Examples**:
  - `ls`: List directory contents
  - `cp`: Copy files
  - `mv`: Move files
  - `cat`: Concatenate and display file contents
  - `bash`: The Bourne Again Shell


#### `/usr/bin` (Non-Essential User Binaries)
- **Purpose**: Contains binaries for general use by all users, but these are not essential for booting or repairing the system.
- **Availability**: Typically resides on a separate partition and may not be available if `/usr` is not mounted (e.g., during early boot stages or recovery modes).
- **Usage**: Includes a broader range of applications and tools that are not critical to the core system operation.
- **Examples**:
  - `vim`: Text editor
  - `gcc`: C compiler
  - `python`: Python interpreter
  - `git`: Version control system

#### **Historical Context**
- In older UNIX systems, `/bin` was designed for essential commands, while `/usr/bin` held supplementary tools. Over time, `/usr/bin` grew to contain a significant portion of system utilities.
- Modern Linux systems often include `/bin` and `/usr/bin` as part of the same filesystem, and some distributions have unified these directories, **symlinking `/bin` to `/usr/bin`** for simplicity.
- 
---

### What is the difference between `/usr/bin` and `/opt`?

#### **`/usr/bin`**
This directory contains user binaries (executable files) that are part of the core system software (not for OS but for system users). These are programs and utilities that are necessary for normal system operations and user tasks. They are typically installed by the distribution's package manager and are shared across all users on the system.

#### **`/opt`**
This directory is used for installing optional software packages that are **not part of the default system installation**. Software in `/opt` is typically self-contained, meaning it may include all necessary libraries and dependencies. It is often used for third-party software or larger applications that don't conform to the standard Linux directory structure. E.g. Google Chromee, Microsoft Edge. 

#### Key Differences:
- **Purpose**:  
  - `/usr/bin` is for essential, system-wide binaries required by the OS and users.  
  - `/opt` is for optional, third-party software that is installed separately from the core system.
  
- **Installation**:  
  - Binaries in `/usr/bin` are generally installed by the system package manager.  
  - Software in `/opt` is often manually installed or provided by vendors as standalone packages.

---

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
- `/lost+found`: Used by the file system to store recovered files after a file system check has been performed.
- `/mnt` and `/media`: Mount points for external file systems or media.
- `/proc` and `/sys`: Virtual filesystems for process and system information.
- `/sbin`: System administration binaries.
- `/srv`: Data served by the system, e.g., web or FTP files.
- `/root`: Home directory for the root user.

---

### Library in Linux:

In Linux, a **library** is a collection of precompiled, reusable code that provides specific functionality for programs. Libraries contain functions or routines that programs can call to perform common tasks, such as handling files, performing mathematical operations, or managing network connections. Rather than each program writing its own code for these tasks, it can instead link to a library, saving time, reducing redundancy, and ensuring consistency across programs.

There are two main types of libraries in Linux:

#### Static Libraries (`.a` files):  
   These are collections of compiled object files that are embedded directly into the executable at compile time. When a program links to a static library, the library's code becomes part of the program itself, making the executable larger but eliminating the need for the library to be present at runtime.

#### Dynamic Libraries (`.so` files):  
   These libraries are loaded into memory at runtime when the program is executed. They are not part of the program's executable file but are instead shared by multiple programs. This reduces memory usage because the library is only loaded into memory once. Dynamic libraries can be updated independently of the programs using them, providing greater flexibility.

### Difference Between `/bin` and `/lib`:

#### `/bin` (Binaries):  
  The `/bin` directory contains **essential system binaries** (executable programs) required for the basic functionality of the system. These are crucial programs that both the operating system and regular users need to perform system tasks. Examples of binaries in `/bin` include commands like `ls`, `cp`, and `mkdir`. These binaries are essential for the system to operate and for users to interact with the system.

#### `/lib` (Libraries):  
  The `/lib` directory contains **shared libraries** that provide essential support for the binaries in `/bin` (and other directories). These libraries contain the compiled code needed by system programs to execute specific tasks. For example, the C standard library (`libc.so`) is stored in `/lib` and provides fundamental functions like input/output handling and memory management. The files in `/lib` are not executable on their own but are used by the binaries to run efficiently.

#### Key Differences:
- **Purpose**:  
  - `/bin` contains **executable programs** (binaries) required for system operation.  
  - `/lib` contains **shared libraries** that provide support for these programs to run.
  
- **Content**:  
  - `/bin` holds essential **commands** for both system administrators and regular users.  
  - `/lib` holds **shared code** that is needed by these commands and other applications to function.

- **Functionality**:  
  - Programs in `/bin` execute tasks directly, while programs in `/lib` provide the necessary libraries that programs in `/bin` rely on to perform their functions.

---

## Finding binary, source, and manual pages

The `whereis` command in Linux is used to locate the **binary, source, and manual page** files for a command or program. It's a helpful tool for finding the location of executables, their associated documentation, and related source code.

### Syntax:
```bash
whereis [options] <command_name>
```

### Common Options:
- **`-b`**: Search only for binary files (executable files).
- **`-m`**: Search only for manual pages.
- **`-s`**: Search only for source code.
- **`-u`**: Locate unlinked files (files that don't have a corresponding entry in the database).
- **`-B <path>`**: Specify a directory to search for binaries.
- **`-M <path>`**: Specify a directory to search for manual pages.
- **`-S <path>`**: Specify a directory to search for source files.

### Example Usage:

1. **Locate all files related to the `ls` command**:
   ```bash
   $ whereis ls
   ls: /usr/bin/ls /usr/share/man/man1/ls.1.gz
   ```
   This will return locations for the `ls` binary, its manual page, and possibly its source code.

2. **Find the binary for `gcc` only**:
   ```bash
   $ whereis -b gcc
   gcc: /usr/bin/gcc /usr/lib/gcc /usr/libexec/gcc /usr/share/gcc
   ```
   This will only return the location of the `gcc` binary.

3. **Find the manual page for `bash`**:
   ```bash
   $ whereis -m bash
   bash: /usr/share/man/man1/bash.1.gz
   ```
   This will return the location of the `bash` manual page.

### How It Works:
- The `whereis` command searches through predefined directories set in system configuration files (like `/usr/bin`, `/bin`, `/usr/local/bin`, etc.).
- It uses a database to speed up the process of locating files, unlike the `which` command, which only returns the location of the executable in the directories specified in the `$PATH` environment variable.

### Use Cases:
- Quickly finding the path to an executable, manual page, or source code.
- Verifying whether a specific command or tool is installed on the system.
- Locating specific documentation or source code for a program.

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
| `/bin`   | Essential binaries for system operation and recovery.  | Basic commands like `ls`, `cp`, `mv`, `cat`, `bash`. |
| `/boot`  | Contains bootloader files and the kernel.  | Kernel images, `grub` configuration files.  |
| `/dev`   | Device files representing hardware and virtual devices.| Files like `/dev/sda` (disk), `/dev/null`, `/dev/tty` (terminals).   |
| `/etc`   | System-wide configuration files.   | Configs for services like `ssh`, `passwd`, `fstab`.  |
| `/home`  | User home directories. | Personal files and directories for users (e.g., `/home/naveen`). |
| `/lib`   | Essential shared libraries and kernel modules. | Libraries used by programs in `/bin` and `/sbin`.   |
| `/media` | Mount points for removable media.  | Subdirectories for CDs, USB drives (e.g., `/media/usb`).|
| `/mnt`   | Temporary mount point for filesystems. | Used for mounting partitions during maintenance or temporary usage.  |
| `/opt`   | Optional software packages installed outside standard directories. | Third-party apps like `/opt/google`.|
| `/proc`  | Virtual filesystem providing process and system information.   | Files like `/proc/cpuinfo`, `/proc/meminfo`.|
| `/root`  | Home directory for the root user.  | Files specific to the `root` superuser. |
| `/run`   | Runtime files like process IDs (PIDs) and sockets.| Files such as `/run/sshd.pid`.  |
| `/sbin`  | System binaries for administrative tasks.  | Commands like `fsck`, `shutdown`, `mount`.  |
| `/srv`   | Data served by the system, such as web server or FTP server files. | E.g., `/srv/www` for websites.  |
| `/sys`   | Virtual filesystem for device and system configuration.   | Hardware information and control files (e.g., `/sys/class`).|
| `/tmp`   | Temporary files, often cleared on reboot. | Session data, temporary downloads.  |
| `/usr`   | Secondary hierarchy for user programs and data.   | Subdirectories like `/usr/bin`, `/usr/lib`, `/usr/share`.   |
| `/var`   | Variable data files that change during operation. | Logs (`/var/log`), spools (`/var/spool`), caches (`/var/cache`). |

### Notes:
1. Some directories like `/media` or `/mnt` might not have content unless specifically used.
2. On modern systems, certain directories like `/bin` and `/sbin` may be symlinks to `/usr/bin` and `/usr/sbin`.
3. The layout and contents of these directories can vary slightly between Linux distributions.

| Commands  | Description   |
|-----------------------------------|-------------------------------------------------------------------|
| `ls [dir]`| Lists the contents of a directory.|
| `whereis -b [command]`| Searches for the binary (executable) file of a command.   |
| `whereis -m [command]`| Searches for the manual page of a command.|
| `whereis -s [command]`| Searches for the source code of a command.|
| `whereis -u [command]`| Finds unlinked files (files not listed in the system's database). |
| `whereis -B <path> [command]` | Specifies a directory to search for binaries. |
| `whereis -M <path> [command]` | Specifies a directory to search for manual pages. |
| `whereis -S <path> [command]` | Specifies a directory to search for source files. | 

This table now includes the `whereis` command, along with its options and descriptions.

---

# Command Line Interface

The **shell** is a program that accepts commands and directs the operating system to execute them. It serves as the interface between the user and the system. The **Command Line Interface (CLI)** is a text-based interface where users type commands.

## Shell and Interface Types
- **CLI (Text Interface)**: When connected to a Linux system, a shell is started, and the user interacts through the command line.
- **GUI (Graphical User Interface)**: When a Linux system is in graphical mode, users interact through a GUI. To access the CLI within a GUI, a terminal emulator (e.g., `xterm`, `GNOME Terminal`) must be used.

## Shell Prompt
The **shell prompt** provides information about the user, system, and current directory. For example:
```bash
sri@envy:~$
```
- `sri`: Username
- `envy`: Hostname
- `~`: Current directory (home directory, e.g., `/home/sri`)

The prompt can vary in format, and users can customize it. Special symbols like `~` (tilde) refer to the user's home directory. For example, `~sri` expands to `/home/sri`.

### Examples of Shell Prompts:
- `[sri@envy /tmp]$`
- `envy:/home/sri>`
- `sri@envy:~>`

Shell prompts can also span multiple lines, showing additional information like time and session details. 
```bash
sri@envy:~/Document/Linux
$
```
## What is the difference between terminal and shell?

The terms **terminal** and **shell** are often used interchangeably, but they refer to different components of a Linux or Unix-based system. Here's the distinction:

### Terminal:
- A **terminal** is a program or interface that allows the user to interact with the computer by entering text-based commands. It provides the environment where you can type and execute commands, and it displays the output of those commands.
- **Terminal** is essentially the window or emulator where the user interacts with the system's shell.
- In the past, a **terminal** referred to physical hardware (like a teletype machine or a console), but today, it usually refers to terminal emulator software (like `gnome-terminal`, `xterm`, or `Konsole`) that runs on modern graphical desktop environments.

**Example**: `gnome-terminal`, `xterm`, `Konsole`, etc.

### Shell:
- The **shell** is a program that interprets and executes the commands you type in the terminal. It acts as a command-line interface (CLI) between the user and the operating system.
- The shell processes the commands you type, interprets them, and sends them to the operating system for execution. It also handles tasks like piping commands, file redirection, environment variables, and script execution.
- Common types of shells in Linux include:
 - **Bash** (Bourne Again Shell)
 - **Zsh** (Z Shell)
 - **Fish** (Friendly Interactive Shell)
 - **Tcsh** (an enhanced version of the C shell)

**Example**: `bash`, `zsh`, `fish`, `sh`, etc.

### Key Differences:
- **Terminal**:  
  - The **interface** or **emulator** where commands are entered and output is displayed.
  - It's a window or program that allows interaction with the system.
  
- **Shell**:  
  - The **program** that interprets and executes commands typed into the terminal.
  - It's the command processor that runs inside the terminal and interacts with the operating system.

### Example to Illustrate the Difference:
- When you open a **terminal** (like `gnome-terminal`), you're launching a program that displays a window.
- Inside that terminal window, a **shell** (like `bash`) is running, and it waits for you to type commands.
- When you type a command in the terminal, the **shell** processes and executes it.

In short, the **terminal** is the interface you use to interact with the system, and the **shell** is the program that interprets the commands you input in that interface.

---

# Basic Commands

In Linux, commands are **case-sensitive** and typically in **lowercase**. Items surrounded by square brackets are optional. 

## Navigation Commands:
### `pwd` Command
Displays the present working directory.
```bash
# Syntax
$ pwd

# Example 
sri@envy:~/Documents/Linux
$ pwd
/home/sri/Documents/Linux
```
### `cd` Command 
Changes the current directory to the specified directory. Without an argument, it changes to the home directory.
```bash
# Syntax
$ cd [directory]

# Example
sri@envy:~/Documents/Linux
$ cd /home
sri@envy:/home
$ pwd
/home
```

If you want to go to previous directory use `cd -`, it's like a back button.
```bash
# Syntax 
$ cd -

# Example
sri@envy:~
$ cd Documents/Linux/
sri@envy:~/Documents/Linux
$ cd -
/home/sri
sri@envy:~
$ cd -
/home/sri/Documents/Linux
sri@envy:~/Documents/Linux
$ 
```


You can get to the user's home directory in **four** differnet ways using `cd`. 

```bash
# 1. using "cd"
sri@envy:~/Documents/Linux
$ cd 
sri@envy:~
$ 

# 2. using "cd ~"
sri@envy:~/Documents/Linux
$ cd ~
sri@envy:~
$ 

# 3. using "cd ~sri"
sri@envy:~/Documents/Linux
$ cd ~sri
sri@envy:~
$ 

# using "cd /home/sri"
sri@envy:~/Documents/Linux
$ cd /home/sri
sri@envy:~
$ 
```

## Listing and Viewing Files:
### `ls` Command
Lists the contents of a directory.
```bash
# Syntax
$ ls [path]

# Examples
sri@envy:~
$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  snap  Templates  Videos
sri@envy:~
$ 

# Using relative path
sri@envy:~
$ ls Documents/Linux/
Linux_command_line_for_you_and_me_Release_0.1.pdf  Linux_Succinctly.pdf  README.md
sri@envy:~
$ 

# Using absolute path
sri@envy:~
$ ls /home/sri/Documents/Linux/
Linux_command_line_for_you_and_me_Release_0.1.pdf  Linux_Succinctly.pdf  README.md
sri@envy:~
$ 

```
### `cat` Command 
Displays the contents of a **file**.
```bash
# Syntax
$ cat [file]

# Example
sri@envy:~
$ cat /home/sri/Documents/Linux/README.md 
# Table of Contents
* [Introduction](#Introduction)
* [Linux Directory Structure](#Linux-Directory-Structure)
  * [Summary](#Summary-of-Linux-Directory-Structure)
* [Command Line Interface](#Command-Line-Interface)
* [Basic Commands](#Basic-Commands)
  * [Summary](#Summary-of-Basic-Commands)

# Without any arguments
$ cat
This will just repeat whatever I type in standard input.
This will just repeat whatever I type in standard input.
To quit press, Ctrl+c
To quit press, Ctrl+c
^C
sri@envy:~
$ 
```

## Exiting the Shell:

### `exit` Command
Exit the current shell. 
```bash
sri@envy:~
$ exit
```
### `logout` Command
Exit from current login session.
```bash
# Not available in Ubuntu 24.04 Desktop
$ logout 
bash: logout: not login shell: use `exit'
```
### `CTRL + d` Shortcut
Exit from shell using the shortcut, `CTRL + d` or `CTRL + D`.
```bash
$ ^D
```

## Command Line Help:
Linux provides built-in documentation through **man** pages, detailing options, example usage and arugments of a specified command.

### `man` Command 
Displays the manual page for a command.
```bash
# Syntax
$ man command

# Example
sri@envy:~
$ man ls
```

#### Navigating man pages

| Key   | Action  |
|-----------------------|-----------------------------|
| Enter, Down Arrow | Move down one line. |
| Up Arrow  | Move up one line.   |
| Spacebar, Page Down   | Move down one page. |
| Page Up   | Move up one page.   |
| `g`   | Go to the start or top. |
| `G`   | Go to the end or bottom.|
| `h`   | Display help.   |
| `j`   | Move down one line. |
| `k`   | Move up one line.   |
| `q`   | Quit.   |


#### Searching man pages

##### `man -k` Command
Returns all the man pages that contain the **keyword**.
```bash
sri@envy:~
# Syntax 
$ man -k [keyword]

# Example
sri@envy:~
$ man -k reboot
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
sri@envy:~
$ 
```
##### `apropos` Command
Work similar to `man -k [keyword]`.

```bash
# Syntax
$ apropos [keyword]

# Example
sri@envy:~
$ apropos reboot
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
sri@envy:~
$ 
```

### `--help` option
Displays a help message for a command.
```bash
# Syntax
$ command --help

# Example
sri@envy:~
$ ls --help
Usage: ls [OPTION]... [FILE]...
List information about the FILEs (the current directory by default).
Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.

Mandatory arguments to long options are mandatory for short options too.
  -a, --all                  do not ignore entries starting with .
  -A, --almost-all           do not list implied . and ..
      --author               with -l, print the author of each file
...

sri@envy:~
$ cd --help
cd: cd [-L|[-P [-e]] [-@]] [dir]
    Change the shell working directory.
    
    Change the current directory to DIR.  The default DIR is the value of the
    HOME shell variable. If DIR is "-", it is converted to $OLDPWD.
    
    The variable CDPATH defines the search path for the directory containing
    DIR.  Alternative directory names in CDPATH are separated by a colon (:).
    A null directory name is the same as the current directory.  If DIR begins
    with a slash (/), then CDPATH is not used.
...
```

## Exploring Commands:
You can explore commands in directories like `/bin` and `/usr/bin` using `ls` and `man` to learn their functions.
```bash
sri@envy:~
$ cd /bin
sri@envy:/bin
$ ls
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
 alsamixer                            nautilus
 alsatplg                             nautilus-autorun-software
 alsaucm                              nautilus-sendto
 amidi                                nawk
 amixer                               nc
 apg                                  nc.openbsd
 apgbfm                               neqn
 aplay                                netaddr
sri@envy:/bin
$ man mv
sri@envy:/bin
$ 
```

### Know what a command does with `whatis`
```bash
# Syntax
$ whatis [command]

# Example
sri@envy:~/Documents
$ whatis ln
ln (1)               - make links between files
sri@envy:~/Documents
$ whatis ls
ls (1)               - list directory contents
sri@envy:~/Documents
$ whatis cd
cd: nothing appropriate.
sri@envy:~/Documents
$ whatis man
man (1)              - an interface to the system reference manuals
sri@envy:~/Documents
$ whatis whatis
whatis (1)           - display one-line manual page descriptions
sri@envy:~/Documents
$ 
```

## Clearing the terminal screen.
Screen can be cleared using 

#### `clear` command
The below command clears the entire terminal. Gives a fresh terminal.
```bash
$ clear
```
#### `CTRL + l` Shortcut
This doesn't doesn't clear the terminal, but clears the Window. If you scroll up you can see the previous commands. 
```bash
$ ^l
```
---

## Creating files
To create an empty files use `touch`
```bash
# Syntax
$ touch file[s]

# Example
sri@envy:~
$ ls
Desktop    Downloads  Pictures  snap       Videos
Documents  Music      Public    Templates
sri@envy:~
$ touch random_file
sri@envy:~
$ ls
Desktop    Downloads  Pictures  random_file  Templates
Documents  Music      Public    snap         Videos
sri@envy:~down
$ touch random1 randome2
sri@envy:~
$ ls
Desktop    Downloads  Pictures  random1   random_file  Templates
Documents  Music      Public    randome2  snap         Videos
sri@envy:~
$ 
```
---

## Summary of Basic Commands

| Command| Description |
|------------------------|-------------|
| `pwd`  | Displays the present working directory. |
| `cd [directory]`   | Changes the current directory to the specified directory. |
| `cd -` | Changes to the previous directory. |
| `cd`   | Changes to the user's home directory. |
| `cd ~` | Changes to the user's home directory. |
| `cd ~user`  | Changes to the home directory of the user `user`. |
| `cd /home/user` | Changes to the directory `/home/user`. |
| `ls [path]`| Lists the contents of the specified path. |
| `ls`   | Lists the contents of the current directory. |
| `cat [file]`   | Displays the contents of a specified file. |
| `cat`  | Reads from the standard input and displays the input. |
| `exit` | Exits the current shell. |
| `logout`   | Exits the current login session (not available in all shells). |
| `^D` or `^d`   | Exits the shell using the shortcut `CTRL+D`. |
| `man command`| Displays the manual page for a command. |
| `man -k keyword` | Returns all man pages containing the specified keyword. |
| `apropos keyword`| Searches for the keyword in the manual page descriptions. |
| `[command] --help` | Displays a help message for the specified command. |
| `whatis [command]`| Display one-line manual page descriptions |
| `clear`| Clears the entire terminal screen. |
| `^L` or `^l`   | Clears the terminal window (history still accessible via scroll). |
| `touch file(s)`  | Creates empty file(s). |

### Navigating man pages

| Key  | Action   |
|----------------------|--------------------------------------|
| Enter, Down Arrow | Move down one line. |
| Up Arrow, `k` | Move up one line.   |
| Spacebar, Page Down   | Move down one page. |
| `g`   | Go to the start or top. |
| `G`   | Go to the end or bottom.|
| `h`   | Display help.   |
| `j`   | Move down one line. |
| `k`   | Move up one line.   |
| `l`   | Move right (scroll horizontally).   |
| `q`   | Quit.   |

---

# Directories
In linux, we call **folder** as **directory**. In Linux, directories end with a trailing forward slash.

## Absolute vs Relative Paths
### Absolute Path: 
Starts with a `/` and points to a location from the root of the file system.
```bash
sri@envy:~/Documents/Linux
$ cd /home/sri/Music/
sri@envy:~/Music
$ 
```

### Relative Path: 
Doesn't start with a `/` and is relative to the current working directory.
```bash
sri@envy:~/Documents/Linux
$ cd ../../Music/
sri@envy:~/Music
$ 
```

## Home Directory
There are many ways to go to user's home directory from anywhere. 
```bash
# 1. using "cd"
sri@envy:~/Documents/Linux
$ cd 
sri@envy:~
$ 

# 2. using "cd ~"
sri@envy:~/Documents/Linux
$ cd ~
sri@envy:~
$ 

# 3. using "cd ~sri"
sri@envy:~/Documents/Linux
$ cd ~sri
sri@envy:~
$ 

# using "cd /home/sri"
sri@envy:~/Documents/Linux
$ cd /home/sri
sri@envy:~
$ 
```

## Special Directory References
- `.` represents the **current directory**.
  ```bash
  # Syntax
  $ cd .   # Stays in the current directory

  # Example
  sri@envy:~/Documents/Linux
  $ cd .
  sri@envy:~/Documents/Linux
  $
  ```

- `..` represents the **parent directory**.
  ```bash
  # Syntax
  $ cd ..   # Moves up one level to the parent directory
  
  # Example
  sri@envy:~/Documents/Linux
  $ cd ..
  sri@envy:~/Documents
  $ 
  ```

## Navigating Directories
### Change directories using `cd`: 
```bash
# Syntax
$ cd [directory]

# Example
sri@envy:~/Documents/Linux
$ cd ~/Music/
sri@envy:~/Music
$ pwd
/home/sri/Music
sri@envy:~/Music
$ 
```

### Return to the previous directory with `cd -`:
```bash
# Syntax:
$ cd -

# Example
sri@envy:~/Documents/Linux
$ cd ~/Music/
sri@envy:~/Music
$ cd -
/home/sri/Documents/Linux
sri@envy:~/Documents/Linux
$ 
```

Note using `cd .` affects the navigation of `cd -`.
```bash
sri@envy:~
$ cd ~/Documents/Linux/     # going to Linux
sri@envy:~/Documents/Linux
$ cd -                      # going to home
/home/sri
sri@envy:~
$ cd -                      # going to Linux
/home/sri/Documents/Linux
sri@envy:~/Documents/Linux
$ cd .                      # Staying in Linux
sri@envy:~/Documents/Linux
$ cd -                      # Staying in Linux itself
/home/sri/Documents/Linux
sri@envy:~/Documents/Linux
$ cd -
/home/sri/Documents/Linux
sri@envy:~/Documents/Linux
$ cd -
/home/sri/Documents/Linux
sri@envy:~/Documents/Linux
$ 

# Internally uses $OLDPWD
# When you use "cd .", 
# $OLDPWD gets modified.

sri@envy:~
$ cd ~/Documents/Linux/
sri@envy:~/Documents/Linux
$ echo $OLDPWD
/home/sri
sri@envy:~/Documents/Linux
$ cd -
/home/sri
sri@envy:~
$ echo $OLDPWD
/home/sri/Documents/Linux
sri@envy:~
$ cd -
/home/sri/Documents/Linux
sri@envy:~/Documents/Linux
$ echo $OLDPWD
/home/sri
sri@envy:~/Documents/Linux
$ cd .
sri@envy:~/Documents/Linux
$ echo $OLDPWD
/home/sri/Documents/Linux
sri@envy:~/Documents/Linux
$ cd -
/home/sri/Documents/Linux
sri@envy:~/Documents/Linux
$ cd -
/home/sri/Documents/Linux
sri@envy:~/Documents/Linux
$ 
```
The loop happens because `cd -` toggles between the current directory and the last visited directory. When you use `cd .`, it doesn't change the directory, so the "previous directory" remains the same. Repeatedly using `cd -` in the same location keeps toggling to the same directory, causing the apparent loop.

## Creating and Removing Directories
### Create a directory with `mkdir`:
```bash
# Syntax
$ mkdir newdir   # Creates a new directory called newdir

# Example
sri@envy:~/Desktop
$ ls 
sri@envy:~/Desktop
$ mkdir dir
sri@envy:~/Desktop
$ ls
dir
sri@envy:~/Desktop
$ ls -ld dir
drwxrwxr-x 2 sri sri 4096 Jan  1 12:00 dir
sri@envy:~/Desktop
$ 
```

### Create directories with `mkdir -p` (including intermediate directories):
```bash
# Syntax
$ mkdir -p newdir/one/two   # Creates newdir, then one, and then two inside it

# Example
sri@envy:~/Desktop
$ ls
sri@envy:~/Desktop
$ mkdir dir/sub-dir/sub-sub-dir
mkdir: cannot create directory ‘dir/sub-dir/sub-sub-dir': No such file or directory
sri@envy:~/Desktop
$ mkdir -p dir/sub-dir/sub-sub-dir
sri@envy:~/Desktop
$ tree dir
dir
└── sub-dir
    └── sub-sub-dir

3 directories, 0 files
sri@envy:~/Desktop
$ 

```

### Remove an empty directory with `rmdir`:
```bash
# Syntax
$ rmdir newdir   # Removes the empty directory newdir

# Example
sri@envy:~/Desktop
$ ls
dir
sri@envy:~/Desktop
$ ls -l dir # Empty directory
total 0
sri@envy:~/Desktop
$ rmdir dir
sri@envy:~/Desktop
$ ls
sri@envy:~/Desktop
$ 

sri@envy:~/Desktop
$ ls
dir
sri@envy:~/Desktop
$ ls -l dir # Empty directory
total 0
sri@envy:~/Desktop
$ rm -r dir
sri@envy:~/Desktop
$ ls
sri@envy:~/Desktop
$ 

```

### Forcefully remove a directory and its contents with `rm -rf`:

Consider this setup to demonstrate the need for forcefull removal of directory. We creating a temporary git repository. 
```bash
sri@envy:~/Desktop
$ mkdir temp_repo
sri@envy:~/Desktop
$ cd temp_repo/
sri@envy:~/Desktop/temp_repo
$ touch a
sri@envy:~/Desktop/temp_repo
$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: 	git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: 	git branch -m <name>
Initialized empty Git repository in /home/sri/Desktop/temp_repo/.git/
sri@envy:~/Desktop/temp_repo
$ git add .
sri@envy:~/Desktop/temp_repo
$ git commit -m "sample commit"
[master (root-commit) 681a648] sample commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 a
```

Now, let's try to delete this directory with `rm -r`
```bash
sri@envy:~/Desktop/temp_repo
$ cd .. 
sri@envy:~/Desktop
$ rm -r temp_repo/
rm: remove write-protected regular file 'temp_repo/.git/objects/e6/9de29bb2d1d6434b8b29ae775ad8c2e48c5391'? 
```
There will be lot of warnings, requesting us about deletion. The input `y` has to be given repeatedly to delete the directory entirely. Here is where `-f` option comes in, it allows us to delete the directory in one go, without any warnings. But this can be dangerous, since there is **no reversion** of a wrong delete. 

```bash
# Syntax
$ rm -rf newdir   # Deletes the newdir directory and all of its contents FORCEFULLY

# Example
sri@envy:~/Desktop
$ rm -rf temp_repo/
sri@envy:~/Desktop
$ 
```

## Summary of Directory Commands

| Command  | Description   |
|--------------------------|-------------------------------------------------------------------------------------------------------|
| `cd [directory]` | Changes the current directory to the specified directory.|
| `cd -`   | Returns to the previous directory.   |
| `cd` | Changes to the home directory.   |
| `cd ~`   | Changes to the home directory (shortcut).|
| `cd ~[username]` | Changes to the home directory of the specified user. |
| `cd /home/[username]`| Changes to the absolute path of the specified user's home directory. |
| `cd .`   | Stays in the current directory.  |
| `cd ..`  | Moves up one level to the parent directory.  |
| `mkdir [directory]`  | Creates a new directory with the specified name. |
| `mkdir -p [path]`| Creates nested directories, including intermediate ones, if they don't exist.|
| `rmdir [directory]`  | Removes an empty directory.  |
| `rm -r [directory]`  | Removes a directory and its contents recursively, prompting for confirmation for protected files.|
| `rm -rf [directory]` | Removes a directory and its contents forcefully, without any prompts or confirmation.|
| `pwd`| Displays the present working directory.  |
| `ls [path]`  | Lists the contents of the specified directory.   |
| `ls` | Lists the contents of the current directory.|
| `tree [directory]`   | Displays the directory structure in a tree format.   |
| `touch [file]`   | Creates an empty file with the specified name.   |
| `git init`   | Initializes a new Git repository in the current directory.   |
| `git add .`  | Stages all changes in the current directory for the next commit. |
| `git commit -m [message]`| Creates a commit with the specified message. |

---

# Viewing File and Directory Details

In Linux, the `ls` command is used to list files and directories, but it can also provide detailed information about them when combined with different options. 

## Basic `ls` Command

The `ls` command by itself will simply list the files and directories in the current directory:
```bash
# Syntax
$ ls

# Example
sri@envy:~
$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  snap  Templates  Videos
sri@envy:~
$ 
```

### Using `ls -l` for Detailed Listings

The `ls -l` command provides a long listing format that shows detailed information about files and directories. 

```bash
# Syntax
$ ls -l

# Example
sri@envy:~
$ ls -l
total 36
drwxr-xr-x  2 sri sri 4096 Jan  1 12:11 Desktop
drwxr-xr-x 13 sri sri 4096 Dec 29 18:04 Documents
drwxr-xr-x  2 sri sri 4096 Dec 31 20:15 Downloads
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Music
drwxr-xr-x  3 sri sri 4096 Dec 23 15:41 Pictures
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Public
drwx------  8 sri sri 4096 Dec 31 18:07 snap
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Templates
drwxr-xr-x  2 sri sri 4096 Dec 21 16:45 Videos
sri@envy:~
$
```

### Breakdown of `ls -l` Output

Each line in the output contains several columns with specific information:

| **Field**  | **Description**  | **Example**|
|------------------------|----------------------------------------------------------|------------------------|
| **Permissions** | Indicates file type and access permissions. | `drwxr-xr-x`   |
| **Links**   | Number of hard links to the file or directory.  | `2`|
| **Owner**   | Name of the user who owns the file or directory.| `sri`  |
| **Group**   | Group associated with the file or directory.| `sri`  |
| **File Size**   | Size of the file in bytes.  | `4096` |
| **Modification Time**   | Last modification date and time.| `Jan  1 12:11` |
| **Name**| Name of the file or directory.  | `Desktop`  |

---

### Example Breakdown

For a specific file:
```bash
-rw-r--r-- 1 sri sri 512 Dec 31 21:00 shopping-list.txt
drwxr-xr-x 13 sri sri 4096 Dec 29 18:04 Documents

```

| **Field**  | **Value**   | **Explanation**  |
|------------------------|---------------------|-----------------------------------------------------|
| **Permissions** | `drwxr-xr-x`   | Regular directory with read/write/execute for owner, read and execute for group and others. |
| **Links**   | `13`| Single hard link.|
| **Owner**   | `sri`  | File is owned by the user `sri`.|
| **Group**   | `sri`  | Associated group is `sri`.|
| **File Size**   | `4096`  | File is 4096 bytes in size.|
| **Modification Time**| `Dec 29 18:04`| File was last modified on Dec 31 at 9:00 PM.|
| **Name**| `Document`| Name of the directory is `Document`.|

## Displaying Hidden Files

By default, `ls` does not show hidden files (files that begin with a dot `.`). To display hidden files, use the `-a` option:
```bash
# Syntax
$ ls -a

# Example
sri@envy:~
$ ls -a
.                 .cache      .gnupg    Public                     .vim
..                .config     .lesshst  .python_history            .viminfo
.aspell.en.prepl  Desktop     .local    snap                       .vimrc
.aspell.en.pws    Documents   Music     .ssh                       .vscode
.bash_history     .dotnet     Pictures  .sudo_as_admin_successful
.bash_logout      Downloads   .pki      Templates
.bashrc           .gitconfig  .profile  Videos
sri@envy:~
$ 
```

To list hidden files with details, use both the `-a` and `-l` options:

```bash
sri@envy:~
$ ls -al
total 164
drwxr-x--- 20 sri  sri   4096 Jan  1 11:58 .
drwxr-xr-x  3 root root  4096 Dec 30 14:41 ..
-rw-rw-r--  1 sri  sri     24 Dec 30 18:03 .aspell.en.prepl
-rw-rw-r--  1 sri  sri    183 Dec 30 18:03 .aspell.en.pws
-rw-------  1 sri  sri  25677 Jan  1 07:14 .bash_history
-rw-r--r--  1 sri  sri    220 Mar 31  2024 .bash_logout
-rw-r--r--  1 sri  sri   4316 Dec 29 18:48 .bashrc
drwx------ 19 sri  sri   4096 Dec 25 20:21 .cache
drwx------ 23 sri  sri   4096 Dec 31 16:12 .config
drwxr-xr-x  2 sri  sri   4096 Jan  1 12:11 Desktop
drwxr-xr-x 13 sri  sri   4096 Dec 29 18:04 Documents
drwxrwxr-x  3 sri  sri   4096 Dec 21 17:15 .dotnet
drwxr-xr-x  2 sri  sri   4096 Dec 31 20:15 Downloads
-rw-rw-r--  1 sri  sri    152 Dec 21 17:40 .gitconfig
drwx------  2 sri  sri   4096 Jan  1 11:50 .gnupg
-rw-------  1 sri  sri     90 Jan  1 11:58 .lesshst
drwx------  4 sri  sri   4096 Dec 21 16:45 .local
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Music
drwxr-xr-x  3 sri  sri   4096 Dec 23 15:41 Pictures
drwx------  3 sri  sri   4096 Dec 21 17:15 .pki
-rw-r--r--  1 sri  sri    807 Mar 31  2024 .profile
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Public
-rw-------  1 sri  sri    329 Dec 31 12:34 .python_history
drwx------  8 sri  sri   4096 Dec 31 18:07 snap
drwx------  2 sri  sri   4096 Dec 21 17:29 .ssh
-rw-r--r--  1 sri  sri      0 Dec 21 16:45 .sudo_as_admin_successful
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Templates
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Videos
drwxr-xr-x  2 sri  sri   4096 Dec 27 20:42 .vim
-rw-------  1 sri  sri  15521 Dec 31 11:22 .viminfo
-rw-rw-r--  1 sri  sri   1260 Dec 26 10:43 .vimrc
drwxrwxr-x  4 sri  sri   4096 Dec 21 17:15 .vscode
sri@envy:~
$ 
```

## Colorized Output with `--color`

To add color to the `ls` output, use the `--color` option. This is **present by default**. This helps differentiate file types:
```bash
# Syntax
$ ls --color
```

## File Type Indicators with `-F`

The `-F` option appends a symbol to each file or directory to indicate its type. Here's how it works:
```bash
# Syntax
$ ls -aF

# Example
sri@envy:~
$ ls -aF
./                .config/    .local/          .sudo_as_admin_successful
../               Desktop/    Music/           Templates/
a.out*            Documents/  Pictures/        Videos/
.aspell.en.prepl  .dotnet/    .pki/            .vim/
.aspell.en.pws    Downloads/  .profile         .viminfo
.bash_history     .gitconfig  Public/          .vimrc
.bash_logout      .gnupg/     .python_history  .vscode/
.bashrc           hello.c     snap/
.cache/           .lesshst    .ssh/
sri@envy:~
$ 
```

For a long listing with file type indicators:
```bash
# Syntax
$ ls -alf

sri@envy:~
$ ls -alF
total 184
drwxr-x--- 20 sri  sri   4096 Jan  1 13:20 ./
drwxr-xr-x  3 root root  4096 Dec 30 14:41 ../
-rwxrwxr-x  1 sri  sri  15960 Jan  1 13:20 a.out*
-rw-rw-r--  1 sri  sri     24 Dec 30 18:03 .aspell.en.prepl
-rw-rw-r--  1 sri  sri    183 Dec 30 18:03 .aspell.en.pws
-rw-------  1 sri  sri  25677 Jan  1 07:14 .bash_history
-rw-r--r--  1 sri  sri    220 Mar 31  2024 .bash_logout
-rw-r--r--  1 sri  sri   4316 Dec 29 18:48 .bashrc
drwx------ 19 sri  sri   4096 Dec 25 20:21 .cache/
drwx------ 23 sri  sri   4096 Dec 31 16:12 .config/
drwxr-xr-x  2 sri  sri   4096 Jan  1 12:11 Desktop/
drwxr-xr-x 13 sri  sri   4096 Dec 29 18:04 Documents/
drwxrwxr-x  3 sri  sri   4096 Dec 21 17:15 .dotnet/
drwxr-xr-x  2 sri  sri   4096 Dec 31 20:15 Downloads/
-rw-rw-r--  1 sri  sri    152 Dec 21 17:40 .gitconfig
drwx------  2 sri  sri   4096 Jan  1 11:50 .gnupg/
-rw-rw-r--  1 sri  sri     72 Jan  1 13:20 hello.c
-rw-------  1 sri  sri     90 Jan  1 11:58 .lesshst
drwx------  4 sri  sri   4096 Dec 21 16:45 .local/
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Music/
drwxr-xr-x  3 sri  sri   4096 Dec 23 15:41 Pictures/
drwx------  3 sri  sri   4096 Dec 21 17:15 .pki/
-rw-r--r--  1 sri  sri    807 Mar 31  2024 .profile
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Public/
-rw-------  1 sri  sri    329 Dec 31 12:34 .python_history
drwx------  8 sri  sri   4096 Dec 31 18:07 snap/
drwx------  2 sri  sri   4096 Dec 21 17:29 .ssh/
-rw-r--r--  1 sri  sri      0 Dec 21 16:45 .sudo_as_admin_successful
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Templates/
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Videos/
drwxr-xr-x  2 sri  sri   4096 Dec 27 20:42 .vim/
-rw-------  1 sri  sri  14641 Jan  1 13:20 .viminfo
-rw-rw-r--  1 sri  sri   1260 Dec 26 10:43 .vimrc
drwxrwxr-x  4 sri  sri   4096 Dec 21 17:15 .vscode/
sri@envy:~
$ 
```

Here's a list of file type indicators used in Linux with the `ls` command:

| **Symbol in Permission String** | **File Type**   | **Description**   | **Default Color**   |
|------------|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| `-`| Regular file | Standard files that contain data, such as text, images, videos, or executables.| Default (white) |
| `b`| Block special file   | Files that represent hardware devices capable of data storage, such as hard drives or USB drives, accessed in fixed-size blocks.   | Yellow with bold|
| `c`| Character special file   | Files that represent hardware devices, such as keyboards or terminals, accessed character by character. Interfaces with devices that transfer data in streams. | Yellow with bold|
| `d`| Directory| Containers for files and other directories, forming a hierarchical structure in the file system.   | Blue|
| `l`| Symbolic link| Special files that act as shortcuts, pointing to another file or directory.| Cyan (light blue)   |
| `p`| FIFO (named pipe)| Used in IPC. Files that act as conduits, allowing two processes to communicate by writing and reading data in a first-in, first-out (FIFO) order.   | Yellow (brown)  |
| `s`| Socket   | Special files used for inter-process communication (IPC), typically for network services or local socket connections. Enables bidirectional communication. | Magenta (purple)|
| `?`| Unknown file type| Files that do not match any recognized file type.  | N/A |
| `*`| Executable   | Files that can be executed as programs or scripts.| Green   |
| `/`| Directory (Indicator)| Indicates a directory in file listings.   | Blue|
| `@`| Symlink (Symbolic link)  | Indicates a symbolic link in file listings.   | Cyan (light blue)   |
| `=`| Socket (Indicator)   | Indicates a socket in file listings.  | Magenta (purple)|
| `\|`   | Named pipe (FIFO) (Indicator) | Indicates a named pipe in file listings.  | Yellow (brown)  |


### Notes
The colors shown above are defaults in most Linux distributions. These may vary based on user configuration (`~/.bashrc`, `~/.zshrc`) or terminal settings. - Colors can be customized using the `LS_COLORS` environment variable. To check the current configuration, run:
```bash
sri@envy:~
$ echo $LS_COLORS 
rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:
```
The `$LS_COLORS` variable defines the colors and styles for file types and extensions in `ls --color` output. It's a series of `key=value` pairs separated by colons (`:`):  

- **Keys**: File types (`di`=directory, `ln`=symlink, `pi`=pipe, etc.) or extensions (`*.tar`, `*.zip`).  
- **Values**: Style codes (`00`=default, `01`=bold) and colors (`31`=red, `34`=blue, `40`=black background, etc.).  

### Examples
- `di=01;34`: Directories are bold blue.  
- `ln=01;36`: Symlinks are bold cyan.  
- `*.tar=01;31`: `.tar` files are bold red.  

Customize with `dircolors` or directly export a new `LS_COLORS` value:
```bash
$ export LS_COLORS="di=01;32:ln=01;33"
```

## Symbolic Links

A **symbolic link** (also known as a symlink or soft link) is a special type of file in Linux that points to another file or directory. It acts as a shortcut, redirecting access to the original target file or directory.

### Characteristics of Symbolic Links:
- **Independent from the target:** If the target file or directory is moved or deleted, the symlink becomes "broken," but the symlink itself remains.
- **Flexible:** Can link to files or directories located anywhere in the file system, including remote locations.
- **Different inode:** The symlink has its own inode, separate from the target file.

### Creating a Symbolic Link
Use the `ln -s` command to create a symbolic link:
```bash
# Syntax:
$ ln -s [target] [symlink]

# Example:
sri@envy:~/Desktop
$ ln -s /home/sri/Documents/myfile.txt myfilelink
sri@envy:~/Desktop
$ ls -F
myfilelink@
sri@envy:~/Desktop
$
```
This creates a symbolic link `myfilelink` that points to `/home/sri/Documents/myfile.txt`.

### Viewing Symbolic Links
Use the `ls -l` command to identify symbolic links. The symlink is indicated with an `@` in `ls -F` or displayed with an arrow (`->`) pointing to the target:
```bash
# Syntax
$ ls -lF

# Example
sri@envy:~/Desktop
$ ls -alF
total 8
drwxr-xr-x  2 sri sri 4096 Jan  1 13:30 ./
drwxr-x--- 20 sri sri 4096 Jan  1 13:25 ../
lrwxrwxrwx  1 sri sri   30 Jan  1 13:30 myfilelink -> /home/sri/Documents/myfile.txt
sri@envy:~/Desktop
$ 
```

### Using a Symbolic Link
You can use a symbolic link just like the original file or directory. For example:
- **Open the linked file:**
  ```bash
  sri@envy:~/Desktop
  $ cat myfilelink
  This is myfile.txt
  sri@envy:~/Desktop
  $ 
  ```
- **Navigate to a linked directory:**
  ```bash
  $ cd mydirlink
  ```

### Managing Symbolic Links
- **Remove a symlink:** Use the `rm` command (this removes only the symlink, not the target):
  ```bash
  $ rm mylink
  ```
- **Edit or recreate a symlink:** Re-run the `ln -s` command with the desired target.

### Broken Symlinks
A symlink becomes "broken" if the target is moved or deleted. You can identify broken symlinks with:
```bash
$ ls -l
sri@envy:~/Desktop
$ ls -l
total 0
lrwxrwxrwx 1 sri sri 30 Jan  1 13:30 myfilelink -> /home/sri/Documents/myfile.txt (red font and highlighted)
```

Symbolic links are commonly used for tasks such as creating shortcuts, linking configuration files, or managing library paths efficiently.

## Sorting Files by Time

To list files sorted by their modification time, use the `-t` option:
```bash
# Syntax
$ ls -t

# Example
sri@envy:~
$ ls -alt
total 168
drwxr-xr-x  2 sri  sri   4096 Jan  1 13:36 Desktop
drwxr-xr-x 13 sri  sri   4096 Jan  1 13:35 Documents
drwxr-x--- 20 sri  sri   4096 Jan  1 13:25 .
-rw-------  1 sri  sri  16617 Jan  1 13:25 .viminfo
-rw-------  1 sri  sri     90 Jan  1 11:58 .lesshst
drwx------  2 sri  sri   4096 Jan  1 11:50 .gnupg
-rw-------  1 sri  sri  25677 Jan  1 07:14 .bash_history
drwxr-xr-x  2 sri  sri   4096 Dec 31 20:15 Downloads
drwx------  8 sri  sri   4096 Dec 31 18:07 snap
drwx------ 23 sri  sri   4096 Dec 31 16:12 .config
-rw-------  1 sri  sri    329 Dec 31 12:34 .python_history
-rw-rw-r--  1 sri  sri     24 Dec 30 18:03 .aspell.en.prepl
-rw-rw-r--  1 sri  sri    183 Dec 30 18:03 .aspell.en.pws
drwxr-xr-x  3 root root  4096 Dec 30 14:41 ..
-rw-r--r--  1 sri  sri   4316 Dec 29 18:48 .bashrc
drwxr-xr-x  2 sri  sri   4096 Dec 27 20:42 .vim
-rw-rw-r--  1 sri  sri   1260 Dec 26 10:43 .vimrc
drwx------ 19 sri  sri   4096 Dec 25 20:21 .cache
drwxr-xr-x  3 sri  sri   4096 Dec 23 15:41 Pictures
-rw-rw-r--  1 sri  sri    152 Dec 21 17:40 .gitconfig
drwx------  2 sri  sri   4096 Dec 21 17:29 .ssh
drwxrwxr-x  3 sri  sri   4096 Dec 21 17:15 .dotnet
drwxrwxr-x  4 sri  sri   4096 Dec 21 17:15 .vscode
drwx------  3 sri  sri   4096 Dec 21 17:15 .pki
-rw-r--r--  1 sri  sri      0 Dec 21 16:45 .sudo_as_admin_successful
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Music
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Public
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Templates
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Videos
drwx------  4 sri  sri   4096 Dec 21 16:45 .local
-rw-r--r--  1 sri  sri    220 Mar 31  2024 .bash_logout
-rw-r--r--  1 sri  sri    807 Mar 31  2024 .profile
sri@envy:~
$ 
```
To reverse the order (show the oldest files first), use `-r`:
```bash
# Syntax 
$ ls -lr

# Example
sri@envy:~
$ ls -altr
total 168
-rw-r--r--  1 sri  sri    807 Mar 31  2024 .profile
-rw-r--r--  1 sri  sri    220 Mar 31  2024 .bash_logout
drwx------  4 sri  sri   4096 Dec 21 16:45 .local
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Videos
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Templates
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Public
drwxr-xr-x  2 sri  sri   4096 Dec 21 16:45 Music
-rw-r--r--  1 sri  sri      0 Dec 21 16:45 .sudo_as_admin_successful
drwx------  3 sri  sri   4096 Dec 21 17:15 .pki
drwxrwxr-x  4 sri  sri   4096 Dec 21 17:15 .vscode
drwxrwxr-x  3 sri  sri   4096 Dec 21 17:15 .dotnet
drwx------  2 sri  sri   4096 Dec 21 17:29 .ssh
-rw-rw-r--  1 sri  sri    152 Dec 21 17:40 .gitconfig
drwxr-xr-x  3 sri  sri   4096 Dec 23 15:41 Pictures
drwx------ 19 sri  sri   4096 Dec 25 20:21 .cache
-rw-rw-r--  1 sri  sri   1260 Dec 26 10:43 .vimrc
drwxr-xr-x  2 sri  sri   4096 Dec 27 20:42 .vim
-rw-r--r--  1 sri  sri   4316 Dec 29 18:48 .bashrc
drwxr-xr-x  3 root root  4096 Dec 30 14:41 ..
-rw-rw-r--  1 sri  sri    183 Dec 30 18:03 .aspell.en.pws
-rw-rw-r--  1 sri  sri     24 Dec 30 18:03 .aspell.en.prepl
-rw-------  1 sri  sri    329 Dec 31 12:34 .python_history
drwx------ 23 sri  sri   4096 Dec 31 16:12 .config
drwx------  8 sri  sri   4096 Dec 31 18:07 snap
drwxr-xr-x  2 sri  sri   4096 Dec 31 20:15 Downloads
-rw-------  1 sri  sri  25677 Jan  1 07:14 .bash_history
drwx------  2 sri  sri   4096 Jan  1 11:50 .gnupg
-rw-------  1 sri  sri     90 Jan  1 11:58 .lesshst
-rw-------  1 sri  sri  16617 Jan  1 13:25 .viminfo
drwxr-x--- 20 sri  sri   4096 Jan  1 13:25 .
drwxr-xr-x 13 sri  sri   4096 Jan  1 13:35 Documents
drwxr-xr-x  2 sri  sri   4096 Jan  1 13:36 Desktop
sri@envy:~
$ 
```

## Recursive Listing with `-R`

To list all files and directories recursively, use the `-R` option:
```bash
# Syntax
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

## Working with Directories Using `-d`

If you want to list the **directory itself** (without showing its contents), use the `-d` option:
```bash
# Syntax
$ ls -d [Directory]

# Example
sri@envy:~
$ ls -d Music/
Music/
sri@envy:~
$ ls -ld Music/
drwxr-xr-x 2 sri sri 4096 Dec 21 16:45 Music/
sri@envy:~
$ 
```

## Escaping Special Characters in Filenames

Files or directories with spaces or special characters in their names require special handling. You can either **use quotes** or **escape the characters with a backslash** (`\ ` - escapes the whitespace).

```bash
# Syntax
$ ls "file name with space"
$ ls file\ name\ with\ space

# Example
sri@envy:~
$ touch "my to do list"
sri@envy:~
$ ls -b
Desktop    Downloads  my\ to\ do\ list  Public  Templates
Documents  Music      Pictures          snap    Videos
sri@envy:~
$ ls -l my\ to\ do\ list 
-rw-rw-r-- 1 sri sri 0 Jan  1 14:11 'my to do list'
sri@envy:~
$ ls -l "my to do list" 
-rw-rw-r-- 1 sri sri 0 Jan  1 14:11 'my to do list'
sri@envy:~
$ 
```

### Using `-b` to View Escaped Names:
```bash
# Syntax
$ ls -b

# Example
sri@envy:~
$ ls -b
Desktop    Downloads  my\ to\ do\ list  Public  Templates
Documents  Music      Pictures          snap    Videos
sri@envy:~
$
```


## Tree Command for Visual Directory Structure

The `tree` command provides a more visually appealing way to view directory structures. 

`tree` is not installed by default: 
```bash
$ sudo apt install tree
```

You can use it as follows:
```bash
# Syntax
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
# Syntax
$ tree -d
.
|-- Desktop
|-- Documents
|-- Downloads
|-- Music
|-- JohnColtrane
5 directories

# Example
sri@envy:~
$ tree -d
.
├── Desktop
├── Documents
│   ├── Git
│   ├── Introduction-to-Vedanta
│   │   ├── Audio
│   │   └── Summary
│   ├── Linux
│   ├── Markdown
│   ├── Nitya-Karma
│   │   ├── Sandhyavandanam
│   │   ├── Shlokas
│   │   └── Stotrams
│   │       ├── Hanuman_Chalisa
│   │       ├── Nama_Ramayanam
│   │       └── Vishnu_Sahasranamam
│   ├── Power-Of-Posture
│   ├── Python
│   ├── Python-DSA
│   │   ├── Chapter-01
│   │   │   └── Question-10
│   │   │       └── __pycache__
│   │   ├── Chapter-02
│   │   │   ├── Programming-Exercises
│   │   │   ├── Self-Check
│   │   │   └── TimeitExperiments
│   │   ├── Chapter-03
│   │   │   ├── Deque
│   │   │   │   └── __pycache__
```

To colorize the output, use `-C` (by deafult this option is used):
```bash
# Syntax
$ tree -C
```

## Summary of Viewing File and Directory Commands
| Command | Description  |
|---------------------------------|----------------------------------------------------------------------------------------------|
| `ls`  | Lists files and directories in the current directory.|
| `ls -l`   | Lists files and directories with detailed information (long format).|
| `ls -a`   | Lists all files, including hidden files (starting with `.`).|
| `ls --color`  | Displays files with color-coded output (for file types).|
| `ls -F`   | Appends indicators (e.g., `/` for directories, `*` for executables) to file names.  |
| `ls -t`   | Lists files sorted by modification time (most recent first).|
| `ls -r`   | Reverses the order of the file list.|
| `ls -R`   | Recursively lists all files and directories.|
| `ls -d [Directory]`   | Displays information about directories, not their contents. |
| `ls "file name with space"`   | Lists a file with spaces in its name by enclosing it in quotes. |
| `ls file\ name\ with\ space`  | Lists a file with spaces in its name by escaping spaces with a backslash (`\`). |
| `ls -b`   | Displays file names with non-printable characters as escape sequences.  |
| `ls -alf` | Combines options: lists all files, including hidden ones, in long format.   |
| `ls -altr`| Lists all files, including hidden ones, in long format, sorted by time in reverse order.|
| `echo $LS_COLORS` | Displays the current color settings for the `ls` command.   |
| `export LS_COLORS="di=01;32:ln=01;33"` | Customizes the `ls` color scheme (e.g., green for directories, yellow for links).  |
| `ln -s [target] [symlink]`| Creates a symbolic link named `[symlink]` pointing to `[target]`.   |
| `cat myfilelink`  | Displays the contents of the file pointed to by the symbolic link `myfilelink`. |
| `cd mydirlink`| Changes the current directory to the one pointed to by the symbolic link `mydirlink`.   |
| `tree`| Displays the directory structure as a tree.|
| `tree -d` | Displays only directories in the tree structure.   |
| `tree -C` | Displays the tree structure with color-coded output.   |

---

# Permissions 

In linux permissions are called **modes**. 

## Understanding File Types

The `ls -l` command displays long listings of files and directories, including the file types. 

```bash
sri@envy:~/Documents/Linux
$ ls -l
total 3248
-rw-rw-r-- 1 sri sri  236154 Jan  3 05:21 README.md
^
^
```
The first character of the permission string indicates the file type. Here are the common file types:

| **Symbol** | **File Type** | **Example** |
|------------|---------------|-------------|
| `-`| Regular file| `-rw-r--r-- 1 sri users 10400 Jun 14 09:31 sales.data`|
| `b`| Block special file  | `brw-rw---- 1 root disk 8, 0 Jan  1 00:00 sda`|
| `c`| Character special file | `crw-rw-rw- 1 root tty 4, 1 Jan  1 00:00 tty1`|
| `d`| Directory| `drwxr-xr-x 2 sri users 4096 Jun 14 09:31 documents`|
| `l`| Symbolic link| `lrwxrwxrwx 1 sri users   11 Jun 14 09:31 mylink -> /etc/hosts`|
| `p`| FIFO (named pipe)| `prw-r--r-- 1 sri users    0 Jun 14 09:31 mypipe`|
| `s`| Socket| `srw-rw-rw- 1 sri users    0 Jun 14 09:31 mysocket`|
| `?`| Unknown file type| `?-????????? ? ?    ?       ?            ? unknownfile`|

The remaining characters in the permission string represent three main types of permissions.

## Types of Permissions

Permissions are represented by three symbols: **read (`r`)**, **write (`w`)**, and **execute (`x`)**. Each permission grants specific abilities over files and directories.

| **Symbol** | **Permission** |
|------------|----------------|
| `r`        | Read           |
| `w`        | Write          |
| `x`        | Execute        |

### Permission Types for Directories

For files, the meanings of these permissions are straightforward:
- **Read** (`r`): Allows viewing the file's contents.
- **Write** (`w`): Allows modifying the file.
- **Execute** (`x`): Allows running the file as a program.

### Permission Types for Directories

For directories, the meanings differ slightly:
- **Read** (`r`): Allows viewing the names of files in the directory.
- **Write** (`w`): Allows modifying the directory's contents (creating, renaming, or deleting files).
- **Execute** (`x`): Allows entering the directory (`cd` command).

```bash
sri@envy:~
$ ls -ld /home/sri/Documents/
drwxr-xr-x 13 sri sri 4096 Jan  1 13:35 /home/sri/Documents/
```

In this case:
- `drwxr-xr-x`: Indicates a directory (`d` at the beginning).
- The permissions `rwxr-xr-x` mean that the owner (`sri`) can read, write, and execute; the group (`sri`) can read and execute, but not write; others can also read and execute but cannot write.

> **Note** the permission `r` for a directory allows an entity to view the entries of the directory, but to read the content of items present in the directory, they need appropriate file permissions. 

## User Categories for Permissions

All files in Linux are owned by a user and a group. This allows for unique permissions to be applied for three sets of users for managing file ownership and permissions:
1. **User** (`u`): The file owner.
2. **Group** (`g`): The group associated with the file.
3. **Other** (`o`): All other users.
4. **All** (`a`): Refers to all three categories (`u`, `g`, and `o`).

When modifying file permissions, these categories are referenced to define who gets which permission.

| **Symbol** | **Category** |
|------------|--------------|
| `u`| User |
| `g`| Group|
| `o`| Other|
| `a`| All  |

For example, 
```bash
$ ls -l sales.data
-rw-r--r-- 1 sri users 10400 Jun 14 09:31 sales.data
```

Here:
- **User** (`sri`) is the file owner.
- **Group** (`users`) is the group owner.
- **Others** are anyone else who is not the owner or part of the group.

### Group
Every user is a member of at least one group, called their primary group. However, users can be members of many groups. Groups bring in user organization, eg. group called "sales" can contain all the employees from sales department. 

To see which groups you belong to, you can run the following commands:

```bash
# Syntax
$ groups

# Example
sri@envy:~
$ groups
sri adm cdrom sudo dip plugdev users lpadmin
sri@envy:~
$ 

# Syntax
$ id
$ id -G
$ id -Gn

# Examples
sri@envy:~
$ id
uid=1000(sri) gid=1000(sri) groups=1000(sri),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),100(users),114(lpadmin)
sri@envy:~
$ id -G
1000 4 24 27 30 46 100 114
sri@envy:~
$ id -Gn
sri adm cdrom sudo dip plugdev users lpadmin
sri@envy:~
$ 
```

For another user:

```bash
# Syntax
$ groups [username]

# Example
sri@envy:~/Documents/Linux
$ groups root
root : root
sri@envy:~/Documents/Linux
$ groups sri
sri : sri adm cdrom sudo dip plugdev users lpadmin
sri@envy:~/Documents/Linux
$ 
```

These commands display the groups the user belongs to, which help in determining the permissions granted to each user category.


## Decoding Permissions

Linux file permissions are displayed using a **10-character string**, which can be decoded as follows:  

1. **File Type** (1st Character):  
- Indicates the type of file.  
  - `-` = Regular file  
  - `d` = Directory  
  - `l` = Symbolic link  

1. **Permissions** (Next 9 Characters):  
- Split into **user (owner)**, **group**, and **others**.  
- Each group has **read (r)**, **write (w)**, and **execute (x)** permissions.  
- If a permission is missing, it's represented by `-`.

1. **Trailing Characters in Permission Strings**  
* Sometimes, additional characters indicate special access control methods:  
  - **`.` (Trailing Period)**: Indicates an SELinux security context.  
  - **`+` (Trailing Plus)**: Indicates Access Control Lists (ACLs).

```bash
$ ls -l sales.data
-rw-r--r-- 1 sri users 10400 Jun 14 09:31 sales.data
```
- File type: `-` (regular file)  
- User (owner): `rw-` (read and write)  
- Group: `r--` (read-only)  
- Others: `r--` (read-only)  
- Owner: `sri`  
- Group: `users`  

```bash
$ ls -l sales.data.selinux
-rw-r--r--. 1 sri users 1040 Jun 14 09:31 sales.data.selinux
# SELinux context applied.

$ ls -l sales.data.acl
-rw-r--r--+ 1 sri users 1040 Jun 14 09:31 sales.data.acl
# ACLs are in use.
```

**Tips for Troubleshooting:**  
- If you notice a trailing character (`.` or `+`), additional investigation may be required, as these security mechanisms can affect file access.  

## Changing Permissions

Linux provides the `chmod` (**change mode**) command to modify file permissions. Permissions can be changed either using **symbolic** or **numeric (octal) modes**.

### 1. Symbolic Mode Permissions

In **symbolic mode**, you can modify file or directory permissions in a human-readable format. The symbolic notation allows you to specify **who** the change applies to, **what action** to perform, and **which permissions** to apply or remove.

```bash
# Syntax
$ chmod [user][operation][permissions] [file]
```

#### Components
1. **[user]:** Specifies which set of users the change applies to:
   - `u`: The owner of the file (user).
   - `g`: The group associated with the file.
   - `o`: All other users (others).
   - `a`: All users (shorthand for `u`, `g`, and `o`).

2. **[operation]:** Defines what action to take:
   - `+`: Add the specified permissions if not already present.
   - `-`: Remove the specified permissions if not already present.
   - `=`: Set the permissions **exactly** as specified, overriding existing ones.

3. **[permissions]:** The type of access being granted or removed:
   - `r`: Read permission (view file contents).
   - `w`: Write permission (modify file contents).
   - `x`: Execute permission (run the file as a program/script).

---

#### Examples

##### 1. Add execute permission for the user (owner):
```bash
# Syntax
$ chmod u+x myscript.sh

# Example
sri@envy:~/Desktop
$ ls afile.txt -l
-rw-rw-r-- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ chmod u+x afile.txt 
sri@envy:~/Desktop
$ ls -l afile.txt 
-rwxrw-r-- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 
```
- Adds execute (`x`) permission for the file's owner (`u`).
- After this, the owner can run the script as a program.

##### 2. Remove write permission for the group:
```bash
# Syntax
$ chmod g-w myscript.sh

# Example
sri@envy:~/Desktop
$ ls -l
total 0
-rwxrwxr-- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ chmod g-x afile.txt
sri@envy:~/Desktop
$ ls -l
total 0
-rwxrw-r-- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 

```
- Removes write (`w`) permission for the file's group (`g`).
- Members of the group can no longer modify the file.

##### 3. Set read-only permission for others:
```bash
# Syntax
$ chmod o=r file.txt

# Example
sri@envy:~/Desktop
$ ls -l
total 0
-rwxrw-rwx 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ chmod o=r afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
-rwxrw-r-- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 
```
- Sets the permission for others (`o`) to read-only (`r`).
- Removes any existing write or execute permissions for others.

##### 4. Allow all users to execute a file:
```bash
# Syntax
$ chmod a+x program.sh

# Example
sri@envy:~/Desktop
$ ls -l
total 0
---------- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ chmod a+x afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
---x--x--x 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 
```
- Adds execute permission for all users (`a`), including owner, group, and others.

##### 5. Set exact permissions for the group:
```bash
# Syntax
$ chmod g=rw myfile.txt

# Example
sri@envy:~/Desktop
$ ls -l
total 0
---x--x--x 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ chmod g=rw afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
---xrw---x 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 
```
- Sets the group (`g`) permissions to read (`r`) and write (`w`) only.
- Removes any execute or other permissions previously set for the group.

##### 6. Remove all permissions for others:
```bash
# Syntax
$ chmod o= mydoc.txt

# Example
sri@envy:~/Desktop
$ ls -l
total 0
---xrw---x 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ chmod o= afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
---xrw---- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 
```
- Removes all permissions for others (`o`), making the file inaccessible to them.
- Simiarly you can remove all the permission for others as well using `a=`.

##### 7. Multiple Changes in One Command:
You can modify permissions for different categories simultaneously. For example:
```bash
# Sytnax
$ chmod u+x,g-w,o=r file.txt

# Example
sri@envy:~/Desktop
$ chmod a= afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
---------- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ chmod a+x,g+r,u+rw afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
-rwxr-x--x 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 
```

##### 8. Explicit Permission Setting:
The equal sign (`=`) can be used to overwrite existing permissions for a user category:
```bash
# Syntax
$ chmod u=rwx file.txt

# Example
sri@envy:~/Desktop
$ chmod u=wx afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
--wxr-x--x 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 

```
This sets the user's permissions to read, write, and execute, overriding any existing permissions for the user category. 

---


### 2. Numeric Mode Permissions

In **numeric (octal) mode**, file permissions are represented using a three-digit number, where each digit specifies the permissions for a different category of users: **owner (user)**, **group**, and **others**. Each digit is the sum of the numeric values assigned to the permissions:

- `r` (read) = **4**
- `w` (write) = **2**
- `x` (execute) = **1**
- No permission = **0**

By adding these values together, you can represent any combination of permissions numerically.

---

#### Permissions Table

The following table shows how the numeric values correspond to permission combinations:

| **Permissions** | **Numeric Value** | **Description** |
|------------------|-------------------|-------------------------------------|
| `rwx`| 7 | Read, write, and execute|
| `rw-`| 6 | Read and write  |
| `r-x`| 5 | Read and execute|
| `r--`| 4 | Read only   |
| `-wx`| 3 | Write and execute   |
| `-w-`| 2 | Write only  |
| `--x`| 1 | Execute only|
| `---`| 0 | No permissions  |

---

#### How It Works

 For example, `chmod 754` assigns:
- **7** (rwx): Owner has full permissions (read, write, execute).
- **5** (r-x): Group can read and execute, but not write.
- **4** (r--): Others can only read.

1. **Structure of Permissions**:
   - The **first digit** applies to the file **owner**.
   - The **second digit** applies to the **group**.
   - The **third digit** applies to **others** (everyone else).

2. **Calculating the Numeric Value**:
   - Add the numeric values for the desired permissions.
   - Example: `rw-` (read + write) = `4 + 2 = 6`.

The below method of specification also works: 
```bash
sri@envy:~/Desktop
$ chmod 7 dir
sri@envy:~/Desktop
$ ls -ld dir
d------rwx 2 sri sri 4096 Jan  3 10:58 dir

sri@envy:~/Desktop
$ chmod 77 dir
sri@envy:~/Desktop
$ ls -ld dir
d---rwxrwx 2 sri sri 4096 Jan  3 10:58 dir

sri@envy:~/Desktop
$ chmod 777 dir 
sri@envy:~/Desktop
$ ls -ld dir
drwxrwxrwx 2 sri sri 4096 Jan  3 10:58 dir

sri@envy:~/Desktop
$ 
```


---


#### Examples of chmod in Numeric Mode

##### 0. Remove all permissions (lock a file):
```bash
$ chmod 000 secretfile.txt
```
- **0** (---): Owner, group, and others have no access.

##### 1. Give the owner full permissions, and the group and others read-only:
```bash
# Syntax
$ chmod 744 myfile.txt

# Example
sri@envy:~/Desktop
$ chmod 000 afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
---------- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ chmod 774 afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
-rwxrwxr-- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 

```
- **7** (rwx): Owner can read, write, and execute.
- **4** (r--): Group can only read.
- **4** (r--): Others can only read.

##### 2. Give the owner read and write permissions, and no permissions to the group and others:
```bash
# Syntax
$ chmod 600 myfile.txt

# Example
sri@envy:~/Desktop
$ chmod 000 afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
---------- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ chmod 600 afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
-rw------- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 

```
- **6** (rw-): Owner can read and write.
- **0** (---): Group has no permissions.
- **0** (---): Others have no permissions.

##### 3. Give everyone execute permission only:
```bash
# Syntax
$ chmod 111 script.sh

# Example
sri@envy:~/Desktop
$ chmod 000 afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
---------- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ chmod 111 afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
---x--x--x 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 

```
- **1** (--x): Owner can only execute.
- **1** (--x): Group can only execute.
- **1** (--x): Others can only execute.

##### 4. Set permissions for a shared script:
```bash
# Syntax
$ chmod 775 shared_script.sh

# Example
sri@envy:~/Desktop
$ chmod 000 afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
---------- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ chmod 775 afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
-rwxrwxr-x 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 
```
- **7** (rwx): Owner can read, write, and execute.
- **7** (rwx): Group can read, write, and execute.
- **5** (r-x): Others can read and execute, but not write.

##### 5. Make a file readable and writable by everyone:
```bash
# Syntax
$ chmod 666 openfile.txt

# Example
sri@envy:~/Desktop
$ chmod 000 afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
---------- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ chmod 666 afile.txt 
sri@envy:~/Desktop
$ ls -l
total 0
-rw-rw-rw- 1 sri sri 0 Jan  3 05:43 afile.txt
sri@envy:~/Desktop
$ 
```
- **6** (rw-): Owner can read and write.
- **6** (rw-): Group can read and write.
- **6** (rw-): Others can read and write.



#### Key Benefits of Numeric Mode
- **Precision**: Numeric mode explicitly defines all permissions at once.
- **Efficiency**: A single command can adjust permissions for all user categories.
- **Control**: You can quickly lock or open a file for specific users.

---

#### Common Octal Permissions

Here are some commonly used permission sets and their symbolic, binary, and octal representations:

| **Symbolic**   | **Octal** | **Meaning**  |
|----------------|-----------|------------------------------------------------------------------------------------------------------|
| `-rwx------`   | `700` | Owner has full control over the file; no one else has access. For confidential file|
| `-rwxr-xr-x`  | `755` | Owner has full control; everyone else can execute the file but only the owner can edit it.|
| `-rw-rw-r--`  | `664` | Owner and group members can modify the file; others can only read it.|
| `-rw-rw----`  | `660` | Owner and group members can modify the file; others have no access.  |
| `-rw-r--r--`  | `644` | Owner can modify the file; everyone else can only read it. For public document|


### Understanding Security Risks with Permissions

It's crucial to avoid overly permissive permissions, such as `777` and `666`. These allow anyone on the system to read, write, or execute the file, which poses significant security risks. Some of the potential issues include:

- **Accidental Changes**: If a file has `777` permissions, anyone on the system can modify it, which could lead to accidental changes.
- **Privilege Escalation**: Malicious users could modify a script or program, introduce harmful code, and cause it to execute when someone else runs the file.
- **Data Destruction**: With `777` or `666` permissions, malicious or careless users can delete or corrupt important data.

### Best Practice:
* Use appropriate permissions for different users and groups. 
* Limit access to sensitive files and make use of groups to provide controlled access. 
* Avoid using `777` or `666` permissions unless absolutely necessary. For example, if multiple users need write access, use groups and restrict permissions for others.

## Working with Groups

When multiple users need access to the same file, Linux group ownership and permissions are useful tools for managing file access.


#### To view existing Groups
```bash
# Syntax
$ cat /etc/group

# Example
sri@envy:~/Desktop
$ cat /etc/group
root:x:0:
daemon:x:1:
bin:x:2:
sys:x:3:
adm:x:4:syslog,sri
tty:x:5:
disk:x:6:
```
The output shows the contents of the `/etc/group` file, which defines the groups on a Linux system. Each line represents a group and follows this format:

```bash
GROUP_NAME:PASSWORD:GID:MEMBERS
```

- **GROUP_NAME**: The name of the group.  
- **PASSWORD**: Typically `x`, indicating that group passwords are stored in a shadow file (not commonly used anymore).  
- **GID**: The Group ID, a unique numeric identifier for the group.  
- **MEMBERS**: A comma-separated list of users who belong to the group.

---

#### Creating a Group
```bash
# Syntax
$ groupadd [options] GROUP_NAME

# Example
sri@envy:~/Desktop
$ groupadd a_new_group
groupadd: Permission denied.
groupadd: cannot lock /etc/group; try again later.
sri@envy:~/Desktop
$ sudo groupadd a_new_group
[sudo] password for sri: 
sri@envy:~/Desktop
$ cat /etc/group | grep a_new_
a_new_group:x:1001:
sri@envy:~/Desktop
$ 
```

---

### Adding Users to the Group 

To add a user (e.g., `sri`) to the group:  
```bash
# Syntax
$ sudo usermod -aG group userid

# Example
sri@envy:~/Desktop
$ sudo usermod -aG a_new_group sri
sri@envy:~/Desktop
$ groups sri | grep a_new
sri : sri adm cdrom sudo dip plugdev users lpadmin a_new_group
sri@envy:~/Desktop
$ 
```
---

### Creating a Group with a Specific GID
If you want to assign a specific Group ID (GID) to the group:  
```bash
# Syntax
$ sudo groupadd -g <number> <group_name>

# Example
sri@envy:~/Desktop
$ sudo groupadd another_new_group -g 2000 
sri@envy:~/Desktop
$ cat /etc/group | grep another
another_new_group:x:2000:
sri@envy:~/Desktop
$ 
```

---

### Deleting a Group
If you need to delete a group:  
```bash
# Syntax
$ sudo groupdel <group_name>

# Examples
sri@envy:~/Desktop
$ sudo groupdel another_new_group 
sri@envy:~/Desktop
$ sudo groupdel a_new_group 
sri@envy:~/Desktop
$ 
```

---

### Summary of group related commands

| **Command**   | **Description**  |
|---------------------------|----------------------------------------------|
| `sudo groupadd GROUP_NAME`| Create a group   |
| `cat /etc/group`  | List all groups  |
| `sudo usermod -aG GROUP_NAME USER_NAME` | Add a user to a group  |
| `groups USER_NAME`| Check user groups|
| `sudo groupdel GROUP_NAME`| Delete a group   |

---

### Changing Group Ownership

Use the `chgrp` command to change the group owner of a file. 

**Example:**  
First let's create a group called `sales`.
```bash
sri@envy:~/Desktop
$ sudo groupadd sales
sri@envy:~/Desktop
$ cat /etc/group | grep sal
sales:x:1001:
sri@envy:~/Desktop
$ 
```
Create a file, `sales.report`, with default group ownership:  
```bash
sri@envy:~/Desktop
$ touch sales.report
sri@envy:~/Desktop
$ ls -l sales.report 
-rw-rw-r-- 1 sri sri 0 Jan  3 06:53 sales.report
sri@envy:~/Desktop
$ 
```
- Default group: `sri` (sri's primary group).  

Change group ownership to `sales`:  
```bash
sri@envy:~/Desktop
$ ls -l sales.report 
-rw-rw-r-- 1 sri sri 0 Jan  3 06:53 sales.report
sri@envy:~/Desktop
$ chgrp sales sales.report
chgrp: changing group of 'sales.report': Operation not permitted
sri@envy:~/Desktop
$ sudo chgrp sales sales.report
sri@envy:~/Desktop
$ ls -l sales.report 
-rw-rw-r-- 1 sri sales 0 Jan  3 06:53 sales.report
sri@envy:~/Desktop
$ 
```
- New group: `sales`.  

---

#### Setting Permissions for Group Access

- Use `chmod` to grant appropriate permissions to the group.  
  - Recommended permissions for non-executable files:  
    - `664 (rw-rw-r--)`: User and group can read/write; others can read.  This is also the default option in Ubuntu 24.04.
    - `660 (rw-rw----)`: User and group can read/write; no access for others.  

**Example:**  
Set group read/write permissions (660):  
```bash
sri@envy:~/Desktop
$ chmod 660 sales.report 
sri@envy:~/Desktop
$ ls -l sales.report 
-rw-rw---- 1 sri sales 0 Jan  3 06:53 sales.report
sri@envy:~/Desktop
$ 

```
- Group members (`sales`) can now read and modify the file.

**Deleting a group**
```bash
sri@envy:~/Desktop
$ ls -l sales.report 
-rw-rw---- 1 sri sales 0 Jan  3 06:53 sales.report
sri@envy:~/Desktop
$ sudo groupdel sales
sri@envy:~/Desktop
$ ls -l sales.report 
-rw-rw---- 1 sri 1001 0 Jan  3 06:53 sales.report
                 ^^^^
sri@envy:~/Desktop
$
```

---

#### Sharing Files in a Common Directory

- **Shared Location**: It's more convenient to use a common directory for group files, such as `/usr/local/sales`.  
  - The directory group owner should be set to the relevant group (e.g., `sales`).  
  - Recommended directory permissions:  
    - `775 (rwxrwxr-x)`: User and group have full access; others can read/execute.  
    - `770 (rwxrwx---)`: Only user and group have full access.  

**Example:**  
Create a shared directory:  
```bash
$ ls -ld /usr/local/sales
drwxrwxr-x 2 root sales 4096 Jun 15 20:53 /usr/local/sales
```
- Group owner: `sales`.  
- Permissions: `775`.

Move the file to the shared directory:  
```bash
$ mv sales.report /usr/local/sales/
$ ls -l /usr/local/sales
total 4
-rw-rw-r-- 1 sri sales 6 Jun 15 20:41 sales.report
```
- `sales.report` is now accessible to all group members.

---

### Key Points
- Use `chgrp` to assign a file to a group.  
- Adjust file permissions (`chmod`) to control group access.  
- Shared directories simplify collaboration and should have appropriate group ownership and permissions.

## Directory Permissions

Directory permissions are critical in controlling access to files and subdirectories within the directory. While file permissions dictate how a file can be read, written, or executed, directory permissions determine how the files and subdirectories inside it are accessed, listed, or modified.

### Understanding Directory Permissions

The permissions for directories are interpreted differently compared to regular files. Here's what each permission means for a directory:

| **Permission** | **Effect on Directory** |
|----------------|-------------------------|
| `r` (read) | Allows viewing the names of the files and subdirectories inside the directory (e.g., `ls` command).  |
| `w` (write)| Allows creating, deleting, or renaming files and subdirectories within the directory.|
| `x` (execute)  | Allows entering the directory (e.g., `cd` command) and accessing files or subdirectories if permissions allow. |

Directory permission usually only contain **0s**, **5s**, and **7s**. Common directory permissions include **755**, **700**, **770**, and **750**.

---

### Permission Combinations for Directories

| **Permissions** | **Effect**   |
|-----------------|-------------------------------------------------------------------------------------------------------|
| `---`| No access to the directory.   |
| `--x`| Allows entering the directory but not listing its contents (you must know file names explicitly to access).|
| `r--`| Allows viewing the directory's contents but not accessing files or entering the directory.|
| `r-x`| Allows viewing and accessing files, but modifications (e.g., adding or deleting files) are not allowed.|
| `rw-`| Allows viewing and modifying the directory's contents but not entering it.|
| `rwx`| Full access: viewing, modifying, and entering the directory.  |
| `-w-`| Allows creating or deleting files in the directory but not listing or accessing them. |
| `-wx`| Allows modifying and entering the directory but not listing its contents. |

---

### Explanation of All Cases with Examples  

#### `---` (No Access)
Cannot list, enter, or modify the directory.  

```bash
# Syntax
$ chmod 000 dir
$ ls dir
ls: cannot open directory 'dir': Permission denied

# Example
sri@envy:~/Desktop
$ chmod 000 dir
sri@envy:~/Desktop
$ ls dir
ls: cannot open directory 'dir': Permission denied
sri@envy:~/Desktop
$ ./dir/a
bash: ./dir/a: Permission denied
sri@envy:~/Desktop
$ ./dir/subdir/b
bash: ./dir/subdir/b: Permission denied
sri@envy:~/Desktop
$ ./dir/c
bash: ./dir/c: Permission denied
sri@envy:~/Desktop
$ 

```

#### `--x` (Execute Only)
You can enter the directory, but you cannot list its contents. You must know file names to access them.  
```bash
# Syntax
$ chmod 111 dir
$ cd dir
$ ls
ls: cannot open directory '.': Permission denied
$ cat file.txt  # Works if the file name is known and permissions allow it.

# Example
sri@envy:~/Desktop
$ chmod 111 dir
sri@envy:~/Desktop
$ cd dir
sri@envy:~/Desktop/dir
$ ls
ls: cannot open directory '.': Permission denied
sri@envy:~/Desktop/dir
$ cat a.c
#include<stdio.h>
int main(){
	printf("Hello, world from Dir\n");
}
sri@envy:~/Desktop/dir
$ cat subdir/b.c
#include<stdio.h>
int main(){
	printf("Hello, world from Subdir\n");
}
sri@envy:~/Desktop/dir
$ ./a
Hello, world from Dir
sri@envy:~/Desktop/dir
$ ./subdir/b
Hello, world from Subdir
sri@envy:~/Desktop/dir
$ 

```

#### `r--` (Read Only) 
You can list the directory's contents but cannot enter or access files.  
```bash
# Syntax
$ chmod 444 dir
$ ls dir  # Lists the files.
$ cd dir
cd: Permission denied

# Example
sri@envy:~/Desktop
$ chmod 444 dir
sri@envy:~/Desktop
$ ls dir
ls: cannot access 'dir/a.c': Permission denied
ls: cannot access 'dir/subdir': Permission denied
ls: cannot access 'dir/a': Permission denied
a  a.c  subdir
sri@envy:~/Desktop
$ cd dir
bash: cd: dir: Permission denied
sri@envy:~/Desktop
$ ls /dir/subdir
ls: cannot access '/dir/subdir': No such file or directory
sri@envy:~/Desktop
$ ls dir/subdir
ls: cannot access 'dir/subdir': Permission denied
sri@envy:~/Desktop
$ cd dir
bash: cd: dir: Permission denied
sri@envy:~/Desktop
$ ./dir/a
bash: ./dir/a: Permission denied
sri@envy:~/Desktop
$ 

```

#### `r-x` (Read and Execute)
You can list the directory's contents and access files, but cannot modify (e.g., add or delete files).  
```bash
# Syntax
$ chmod 555 dir
$ ls dir  # Lists the files.
$ cd dir  # Allows entering the directory.
$ touch newfile
touch: cannot touch 'newfile': Permission denied

# Example
sri@envy:~/Desktop
$ chmod 555 dir
sri@envy:~/Desktop
$ ls dir
a  a.c  subdir
sri@envy:~/Desktop
$ cd dir
sri@envy:~/Desktop/dir
$ touch newfile
touch: cannot touch 'newfile': Permission denied
sri@envy:~/Desktop/dir
$ ./a
Hello, world from Dir
sri@envy:~/Desktop/dir
$ ./subdir/b
Hello, world from Subdir
sri@envy:~/Desktop/dir
$ 
```

#### `rw-` (Read and Write)
You can list and modify the directory's contents but cannot enter it.  
```bash
# Syntax
$ chmod 666 dir
$ ls dir  # Lists the files.
$ cd dir
cd: Permission denied

# Example
sri@envy:~/Desktop
$ chmod 666 dir
sri@envy:~/Desktop
$ ls dir
ls: cannot access 'dir/a.c': Permission denied
ls: cannot access 'dir/subdir': Permission denied
ls: cannot access 'dir/a': Permission denied
a  a.c  subdir
sri@envy:~/Desktop
$ cd dir
bash: cd: dir: Permission denied
sri@envy:~/Desktop
$ ./dir/a
bash: ./dir/a: Permission denied
sri@envy:~/Desktop
$ touch dir/afile
touch: cannot touch 'dir/afile': Permission denied
sri@envy:~/Desktop
$ 
```

#### `rwx` (Full Access)
You can list, access, modify, and enter the directory.  
```bash
# Syntax
$ chmod 777 dir
$ ls dir  # Lists the files.
$ cd dir  # Allows entering the directory.
$ touch newfile  # Creates a new file.

# Example
sri@envy:~/Desktop
$ chmod 777 dir
sri@envy:~/Desktop
$ cd dir
sri@envy:~/Desktop/dir
$ ls
a  a.c  subdir
sri@envy:~/Desktop/dir
$ ./a
Hello, world from Dir
sri@envy:~/Desktop/dir
$ touch new_file
sri@envy:~/Desktop
$ 
```

#### `-w-` (Write Only)
You can create or delete files in the directory but cannot list or access them.  
```bash
# Syntax
$ chmod 222 dir
$ ls dir
ls: cannot open directory '.': Permission denied
$ touch newfile  # Works to create files.

# Example
sri@envy:~/Desktop
$ chmod 222 dir
sri@envy:~/Desktop
$ ls
dir
sri@envy:~/Desktop
$ ls dir
ls: cannot open directory 'dir': Permission denied
sri@envy:~/Desktop
$ cd dir
bash: cd: dir: Permission denied
sri@envy:~/Desktop
$ touch dir/new_file
touch: cannot touch 'dir/new_file': Permission denied
sri@envy:~/Desktop
$ ./dir/a
bash: ./dir/a: Permission denied
sri@envy:~/Desktop
$ 
```

#### `-wx` (Write and Execute)
You can modify and enter the directory, but cannot list its contents.  
```bash
# Syntax
$ chmod 333 dir
$ ls dir
ls: cannot open directory '.': Permission denied
$ cd dir  # Allows entering the directory.
$ touch newfile  # Works to create files.

# Example
sri@envy:~/Desktop
$ chmod 333 dir
sri@envy:~/Desktop
$ ls dir
ls: cannot open directory 'dir': Permission denied
sri@envy:~/Desktop
$ cd dir
sri@envy:~/Desktop/dir
$ touch new_file
sri@envy:~/Desktop/dir
$ ./a
Hello, world from Dir
sri@envy:~/Desktop/dir
$ 
```

### Examples of Specific Directory Permission Scenarios

#### Scenario 1: A Public Directory
To make a directory accessible to everyone without allowing modifications:
```bash
sri@envy:~/Desktop
$ mkdir public
sri@envy:~/Desktop
$ chmod 755 public
sri@envy:~/Desktop
$ ls -ld public/
drwxr-xr-x 2 sri sri 4096 Jan  3 10:56 public/
sri@envy:~/Desktop
$ 
```
- **Owner**: Full control (read, write, execute).
- **Group and Others**: Can read and execute but not write.

---

#### Scenario 2: A Private Directory
To make a directory private to the owner:
```bash
sri@envy:~/Desktop
$ mkdir private
sri@envy:~/Desktop
$ chmod 700 private
sri@envy:~/Desktop
$ ls -ld private/
drwx------ 2 sri sri 4096 Jan  3 10:56 private/
sri@envy:~/Desktop
$ 
```
- Only the owner can list, modify, and access the directory.

---

#### Scenario 3: Locking a Directory
To lock a directory completely:
```bash
sri@envy:~/Desktop
$ mkdir locked
sri@envy:~/Desktop
$ chmod 000 locked
sri@envy:~/Desktop
$ ls -ld locked
d--------- 2 sri sri 4096 Jan  3 11:01 locked
sri@envy:~/Desktop
$ 
```
- No one, including the owner, can list, access, or modify the directory without changing its permissions.

### Default Permissions and the File Creation Mask

The file creation mask (`umask`) determines the default permissions for new files and directories. The `umask` value is subtracted from the base permissions (777 for directories and 666 for files).

#### Viewing the Umask
The `umask` command shows the current default settings:

```bash
# Syntax
$ umask
$ umask -S

# Example
sri@envy:~/Desktop
$ umask
0002
sri@envy:~/Desktop
$ 

sri@envy:~/Desktop
$ umask -S
u=rwx,g=rwx,o=rx
sri@envy:~/Desktop
$ 

```

A `umask` of `0|002` subtracts write permissions from the group and others, resulting in the following default permissions:
- Directories: `775`
- Files: `664`

**Demonstration**
```bash
sri@envy:~/Desktop
$ umask
0002
sri@envy:~/Desktop
$ mkdir dir
sri@envy:~/Desktop
$ ls -ld dir
drwxrwxr-x 2 sri sri 4096 Jan  3 11:05 dir
sri@envy:~/Desktop
$ touch file
sri@envy:~/Desktop
$ ls -l file
-rw-rw-r-- 1 sri sri 0 Jan  3 11:06 file
sri@envy:~/Desktop
$ 
```

#### Setting a Specific Umask
To allow members of your group to modify files, set the `umask` to `002`:

```bash
$ umask 022
$ umask u=,g=w,o=w
```
This results in:
- Directories: `755`
- Files: `644`

For a more restrictive `umask`, such as `007`, which grants no permissions to users outside the group:

```bash
$ umask 007
$ umask u=, g=, o=rwx
```
This results in:
- Directories: `770`
- Files: `660`

#### Estimating Creation Permissions
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

```bash
$ chmod 4755 /usr/bin/passwd
```
This enables `setuid` for the `passwd` command, allowing it to run with superuser privileges.

#### Setgid (Set Group ID)
The `setgid` permission allows a program to run with the group of the file instead of the executing user's group. Additionally, when `setgid` is used on a directory, all files created within that directory inherit the directory's group.

To enable `setgid`:
- Octal mode: Prepend `2`
- Symbolic mode: Use `g+s`

```bash
$ chmod 2755 /usr/bin/locate
```
This enables `setgid` on the `locate` command.

#### Setting Setgid on a Directory
```bash
$ chmod 2770 /usr/local/sales
```
This ensures that all new files created in `/usr/local/sales` will inherit the `sales` group.

#### Sticky Bit
The `sticky` bit **prevents users from deleting files owned by others**, even if they have write access to the directory. This is typically used in shared directories like `/tmp` to prevent file deletion by unauthorized users.

To enable the sticky bit:
- Octal mode: Prepend `1`
- Symbolic mode: Use `+t`

```bash
$ chmod 1777 /tmp
```
This allows everyone to write to `/tmp`, but only the owner of a file can delete it.

## Summary of Permissions Commands

| **Command**  | **Description**   |
|--------------------------------------|-------------------------------------------------------------------------------------------------------|
| `ls -l`| Lists detailed information about files and directories in the current directory.  |
| `ls -ld /home/sri/Documents/`  | Displays detailed information about the `/home/sri/Documents` directory itself.  |
| `groups`   | Lists the groups the current user belongs to.|
| `id`   | Displays user ID (UID), group ID (GID), and other group memberships. |
| `id -G`| Displays the numeric GIDs of all groups the user belongs to. |
| `id -Gn`   | Lists the group names of all groups the user belongs to. |
| `groups [username]`| Lists the groups a specified user belongs to.|
| `chmod [user][operation][permissions] [file]` | Changes permissions for a file or directory. |
| `chmod u+x myscript.sh`| Adds execute permission to the user for `myscript.sh`.   |
| `chmod g-w myscript.sh`| Removes write permission from the group for `myscript.sh`.   |
| `chmod o=r file.txt` | Sets read-only permission for others on `file.txt`.  |
| `chmod a+x program.sh` | Adds execute permission for all users on `program.sh`.   |
| `chmod o= mydoc.txt`   | Removes all permissions for others on `mydoc.txt`.   |
| `chmod a= afile.txt`   | Removes all permissions for all users on `afile.txt`.|
| `chmod u=rwx file.txt` | Grants read, write, and execute permissions to the user for `file.txt`.  |
| `chmod 7 dir`  | Grants full access (rwx) to the owner only for `dir`.|
| `chmod 77 dir` | Grants full access (rwx) to owner and group for `dir`.   |
| `chmod 777 dir`| Grants full access (rwx) to everyone for `dir`.  |
| `cat /etc/group`   | Displays the contents of the `/etc/group` file, showing group information.   |
| `groupadd [options] GROUP_NAME`| Creates a new group with the specified name. |
| `sudo usermod -aG group userid`| Adds a user to a specified group.|
| `sudo groupadd -g <number> <group_name>` | Creates a group with a specific GID. |
| `sudo groupdel <group_name>` | Deletes a specified group.   |
| `sudo chgrp sales sales.report`| Changes the group owner of `sales.report` to `sales`.|
| `umask`| Displays the current umask value.|
| `umask valid_octal`| Changes the current umask to the specified value.|
| `umask -S`| Displays the current umask in Symbolic form.|
| `umask u=rwx,g=rx,o=rx`| Changes the current umask to the specified value in Symbolic format|
| `chmod 4755 /usr/bin/passwd`   | Sets the setuid permission on `passwd`, allowing execution as the file's owner (root).   |
| `chmod 2755 /usr/bin/locate`   | Sets the setgid permission on `locate`, allowing execution as the file's group.  |
| `chmod 1777 /tmp`  | Sets the sticky bit on `/tmp`, ensuring only owners can delete their files within the directory.  |

---

# Viewing and Editing Files

## Viewing Files

### `cat` - Concatenate and Display the Entire File

The `cat` command displays the entire contents of a file in the command prompt itself. It is useful for smaller files but can be overwhelming for large files.

```bash
# Syntax
$ cat [file]

# Example
sri@envy:~/Documents/Linux
$ cat README.md 
# Table of Contents
* [Introduction](#Introduction)
* [Linux Directory Structure](#Linux-Directory-Structure)
  * [Summary](#Summary-of-Linux-Directory-Structure)
* [Command Line Interface](#Command-Line-Interface)
* [Basic Commands](#Basic-Commands)
...
```

---

### `more` - Browse Through a Text File

The more command is a **terminal pager program used**. It allows users to view the contents of a file one screen at a time, making it easier to read long files that don't fit within the terminal window. more is typically used for viewing large text files without loading the entire file into memory at once.

To open a file using `more`:
```bash
# Syntax
$ more file_name

# Example
sri@envy:~/Documents/Linux
$ more README.md 
```
Once you enter `more` pager program, you can use the following commands to navigate around:

| **Key** | **Action** |
|---------|------------|
| `<space>`| Display next k lines of text (current screen size)|
| `z`| Display next k lines of text (current screen size)|
| `<return>`| Display next k lines of text (1 line) |
| `d` or `ctrl-D`| Scroll k lines (current scroll size, initially 11)|
| `q` or `Q` or `<interrupt>`  | Exit from more|
| `s`| Skip forward k lines of text (1 line) |
| `f`| Skip forward k screenfuls of text (1 screenful)   |
| `b` or `ctrl-B`| Skip backwards k screenfuls of text (1 screenful) |
| `'`| Go to place where previous search started |
| `=`| Display current line number|
| `/<regular expression>`  | Search for kth occurrence of regular expression (1 occurrence) |
| `n`| Search for kth occurrence of last regular expression (1 occurrence) |
| `!<cmd>` or `:!<cmd>`| Execute `<cmd>` in a subshell  |
| `v`  | Start up '/usr/bin/vi' at current line|
| `ctrl-L` | Redraw screen|
| `:n` | Go to kth next file (1 file)|
| `:p`| Go to kth previous file (1 file)   |
| `:f`| Display current file name and line number  |
| `.`| Repeat previous command|

`more` is often contrasted with the less command, which offers more advanced features like scrolling backward and forward through a file more efficiently.

---

### `less` - Browse Backward and Search Within a File

The `less` command is similar to `more`, but it offers additional functionality like backward navigation and searching.

To open a file using `less`:
```bash
# Syntax
$ less file_name

# Example
sri@envy:~/Documents/Linux
$ less README.md 
```
You can scroll up and down through the file, search for patterns, and use other advanced features like following the file.

Here's a table summarizing the useful `less` commands:

| **Command**  | **Description**   |
|------------------------------|-----------------------------------------------------------------------|
| **Space** or **f**| Move forward one screen.  |
| **b** or **Ctrl-B**   | Move backward one screen. |
| **Enter** or **j**| Move forward one line.|
| **k** | Move backward one line.   |
| **g** | Go to the beginning of the file.  |
| **G** | Go to the end of the file.|
| **<number>g** | Go to a specific line number (e.g., `50g` goes to line 50).   |
| **/pattern**  | Search forward for the pattern.   |
| **?pattern**  | Search backward for the pattern.  |
| **n** | Go to the next occurrence of the search pattern.  |
| **N** | Go to the previous occurrence of the search pattern.  |
| **/pattern[Enter]**   | Find the next match of the pattern.   |
| **?pattern[Enter]**   | Find the previous match of the pattern.   |
| **{** | Jump to the previous search result.   |
| **}** | Jump to the next search result.   |
| **&pattern**  | Show only the lines matching the given pattern.   |
| **Ctrl-F**| Scroll forward by one screen. |
| **Ctrl-B**| Scroll backward by one screen.|
| **v** | Open the file in the `vi` editor at the current location. |
| **=** | Display the current line number.  |
| **:f**| Show the current filename and line number.|
| **:p**| Display the previous file (when viewing multiple files).  |
| **:n**| Display the next file (when viewing multiple files).  |
| **q** or **Ctrl-C**   | Exit `less`.  |
| **Ctrl-D**| Scroll down half a screen.|
| **Ctrl-U**| Scroll up half a screen.  |
| **h** | Show the help screen with all the commands.   |
| **m** | Mark the current location.|
| **`** | Jump back to the last marked location.|
| **s** | Sort the file (requires sorting support in `less`).   |
  

### Philosophy: *less is more*

---

### `head` - Display the Beginning of a File

The `head` command shows the first 10 lines of a file by default. You can also specify how many lines to display using `-N`, where `N` is the number of lines.

```bash
# Syntax
$ head file_name
$ head -N file_name

# Examples
sri@envy:~/Documents/Linux
$ head README.md 
# Table of Contents
* [Introduction](#Introduction)
* [Linux Directory Structure](#Linux-Directory-Structure)
  * [Summary](#Summary-of-Linux-Directory-Structure)
* [Command Line Interface](#Command-Line-Interface)
* [Basic Commands](#Basic-Commands)
  * [Summary](#Summary-of-Basic-Commands)
* [Directories](#Directories)
  * [Summary](#Summary-of-Directory-Commands)
* [Viewing File and Directory Details](#Viewing-File-and-Directory-Details)
sri@envy:~/Documents/Linux
$ 

sri@envy:~/Documents/Linux
$ head -5 README.md 
# Table of Contents
* [Introduction](#Introduction)
* [Linux Directory Structure](#Linux-Directory-Structure)
  * [Summary](#Summary-of-Linux-Directory-Structure)
* [Command Line Interface](#Command-Line-Interface)
sri@envy:~/Documents/Linux
$ 
```

---

### `tail` - Display the End of a File

The `tail` command shows the last 10 lines of a file by default. You can specify the number of lines with `-N`, where `N` is the number of lines you want to display.

```bash
# Syntax
$ tail file_name
$ tail -N file_name

# Examples
sri@envy:~/Documents/Linux
$ tail README.md 
| `sudo apt full-upgrade`| Perform an upgrade with more aggressive handlin...
| `dpkg -l`| List all installed packages.| `dpkg -l`|
| `dpkg -S /path/to/file`| Find the package that provides a specific file...
| `sudo dpkg -i package.deb`| Install a package from a `.deb` file.| ...
| Install a `.deb` package| Install a `.deb` file.| `sudo dpkg -i package.deb`|
| `dpkg -l`| List all installed packages.| `dpkg -l`|
| Fix broken dependencies| Fix unmet dependencies after installing a  ...
| Install a `.deb` package| Install a `.deb` file.| `sudo dpkg -i package.deb`|
| List installed files for a package | View which files a package has ...
| Find a package by file | Identify which package install ...

sri@envy:~/Documents/Linux
$ tail -5 README.md 
| **Example Workflow with `dpkg`** | **Description**| **Command**|
| Install a `.deb` package| Install a `.deb` file.| `sudo dpkg -i package.deb`|
| Fix broken dependencies| Fix unmet dependencies after installing a `.deb` package.| `sudo apt install -f`|
| List installed files for a package | View which files a package has installed.| `dpkg -L <package>`  |
| Find a package by file | Identify which package installed a specific file.  | `dpkg -S /path/to/file`   |sri@envy:~/Documents/Linux
$ 

```

---

### `tail -f` - Follow a File as It Grows

The `-f` flag with `tail` allows you to view a file as it is updated in real time. This is particularly useful for log files.

```bash
# Syntax
$ tail -f file_name

# Example
sri@envy:~/Documents/Linux
$ tail -f /var/log/syslog 
2025-01-01T15:21:43.811326+05:30 envy tracker-miner-fs-3[28389]: (tracker-extract-3:28389): GLib-GIO-WARNING **: 15:21:43.810: Error creating IO channel for /proc/self/mountinfo: Invalid argument (g-io-error-quark, 13)
2025-01-01T15:25:01.297920+05:30 envy CRON[28505]: (root) CMD (command -v debian-sa1 > /dev/null && debian-sa1 1 1)
2025-01-01T15:29:33.800610+05:30 envy tracker-miner-fs-3[28786]: (tracker-extract-3:28786): GLib-GIO-WARNING **: 15:29:33.799: Error creating IO channel for /proc/self/mountinfo: Invalid argument (g-io-error-quark, 13)
2025-01-01T15:30:01.255458+05:30 envy CRON[28803]: (root) CMD ([ -x /etc/init.d/anacron ] && if [ ! -d /run/systemd/system ]; then /usr/sbin/invoke-rc.d anacron start >/dev/null; fi)
2025-01-01T15:30:26.021481+05:30 envy systemd[1]: Starting sysstat-collect.service - system activity accounting tool...
2025-01-01T15:30:26.029645+05:30 envy systemd[1]: sysstat-collect.service: Deactivated successfully.
2025-01-01T15:30:26.029955+05:30 envy systemd[1]: Finished sysstat-collect.service - system activity accounting tool.
2025-01-01T15:33:26.086757+05:30 envy systemd[1]: anacron.service - Run anacron jobs was skipped because of an unmet condition check (ConditionACPower=true).
2025-01-01T15:35:01.270010+05:30 envy CRON[29102]: (root) CMD (command -v debian-sa1 > /dev/null && debian-sa1 1 1)
2025-01-01T15:37:18.046559+05:30 envy systemd-timesyncd[687]: Contacted time server [2620:2d:4000:1::3f]:123 (ntp.ubuntu.com).

```
This will show the contents of `syslog` as it gets updated.

**Alternatively**, after opening a file with **`less`**, you can **type `F`** to start following the file as it grows.

```bash
# Syntax
$ less file # Press 'f' after opening

# Example
2025-01-01T15:37:18.046559+05:30 envy systemd-timesyncd[687]: Contacted time server [2620:2d:4000:1::3f]:123 (ntp.ubuntu.com).
2025-01-01T15:39:39.969450+05:30 envy wpa_supplicant[1001]: wlo1: CTRL-EVENT-SIGNAL-CHANGE above=1 signal=-54 noise=9999 txrate=292500
2025-01-01T15:40:00.803620+05:30 envy wpa_supplicant[1001]: wlo1: WPA: Group rekeying completed with d8:07:b6:ec:8c:3f [GTK=CCMP]
2025-01-01T15:40:13.262665+05:30 envy systemd[1]: Starting sysstat-collect.service - system activity accounting tool...
2025-01-01T15:40:13.316440+05:30 envy systemd[1]: sysstat-collect.service: Deactivated successfully.
2025-01-01T15:40:13.316630+05:30 envy systemd[1]: Finished sysstat-collect.service - system activity accounting tool.

# below line is the status bar
Waiting for data... (interrupt to abort)
```

## Summary of Viewing files

| **Command**| **Description**| **Example**|
|------------|----------------|------------|
| `cat [file]`| Displays the entire contents of a file. Useful for smaller files.| `cat goals.txt`|
| `more [file]`| Displays a file one page at a time. Useful for larger files.| `more goals.txt`|
| `less [file]`| Allows backward navigation and searching within a file.| `less goals.txt`|
| `head [file]`| Displays the first 10 lines of a file.| `head goals.txt`|
| `head -N [file]`| Displays the first N lines of a file.| `head -5 goals.txt`|
| `tail [file]`| Displays the last 10 lines of a file.| `tail goals.txt`|
| `tail -N [file]`| Displays the last N lines of a file.| `tail -5 goals.txt`|
| `tail -f [file]`| Displays the last lines of a file and follows it as it grows (useful for logs).| `tail -f /var/log/syslog`|
| `less [file]` + `F`  | Follow a file as it grows in real-time within `less`.| `less goals.txt` then type `F`|

---
Here's a refined and well-structured version of the explanation for a better flow:

---

# The Vim Editor

Vim is a powerful and versatile text editor widely used in Linux and Unix systems. It is an enhanced version of the `vi` editor, offering advanced features like syntax highlighting, multi-level undo/redo, network file editing, and screen splitting. When you run `vi` on many systems, you are likely using Vim.

The core strength of Vim lies in its use of **modes**, which allow for efficient and intuitive navigation, editing, and command execution.

---

## Understanding Vim Modes

Vim operates in various modes, each designed for specific tasks:

### 1. Command Mode
Vim starts in **Command Mode**, where every keystroke is interpreted as a command rather than input text. In this mode, you can navigate, delete, copy, paste, and perform many editing actions.

#### Key Features in Command Mode:
| **Action**| **Command** |
|------------------------------------|-------------|
| Move up one line   | `k` |
| Move down one line | `j` |
| Move left one character| `h` |
| Move right one character   | `l` |
| Move right one word| `w` |
| Move left one word | `b` |
| Move to the beginning of the line  | `^` |
| Move to the end of the line| `$` |
| Move to the beginning of the file  | `gg`|
| Move to the end of the file| `G` |

**Examples**:
- Move 3 lines down: `3j`
- Go to the start of the file: `gg`
- Go to the end of the file: `G`

---

### 2. Insert Mode
Insert Mode allows you to input text directly into the file. You can enter Insert Mode from Command Mode using the following keys:
| **Action**| **Command** |
|------------------------------------|-------------|
| Insert at the current position | `i` |
| Insert at the beginning of the line | `I`|
| Append after the current position  | `a` |
| Append at the end of the line  | `A` |

Once you're done typing, press `Esc` to return to Command Mode.

**Examples**:
- Start typing at the current cursor: `i`
- Append text to the end of the line: `A`

---

### 3. Line Mode (Command Line Mode)
Line Mode is accessed by typing `:` in Command Mode. Here, you can execute commands for saving, quitting, searching, and more.

#### Common Commands in Line Mode:
| **Action**| **Command** |
|------------------------------------|-------------|
| Save the file  | `:w`|
| Quit the editor| `:q`|
| Save and quit  | `:wq` or `:x` |
| Quit without saving| `:q!`   |
| Go to line `n` | `:n`|
| Enable line numbers| `:set nu`   |
| Disable line numbers   | `:set nonu` |
| Access help| `:help` |

**Examples**:
- Save the file: `:w`
- Quit without saving changes: `:q!`
- Jump to line 20: `:20`
- Enable line numbering: `:set nu`

---

## Editing Commands in Command Mode

### 1. Deleting Text
| **Action**| **Command** |
|------------------------------------|-------------|
| Delete a character | `x` |
| Delete a word  | `dw`|
| Delete a line  | `dd`|
| Delete from cursor to line end | `D` |

**Examples**:
- Delete a character: `x`
- Delete a word: `dw`
- Delete an entire line: `dd`

---

### 2. Changing Text
| **Action**| **Command** |
|------------------------------------|-------------|
| Replace the current character  | `r` |
| Change the current word| `cw`|
| Change the current line| `cc`|
| Change to the line's end   | `c$`|

**Examples**:
- Replace a character with `d`: `rd`
- Change a word: `cw`, then type the new word.

---

### 3. Copying and Pasting Text
Vim uses the `yank` command to copy and `p` to paste.
| **Action**| **Command** |
|------------------------------------|-------------|
| Yank the current line  | `yy`|
| Yank a word| `yw`|
| Paste the yanked text  | `p` |

**Examples**:
- Yank a line: `yy`
- Paste it below the current line: `p`

---

### 4. Undo and Redo
| **Action**| **Command** |
|------------------------------------|-------------|
| Undo the last change   | `u` |
| Redo the last undone change| `Ctrl + r`  |

**Examples**:
- Undo: `u`
- Redo: `Ctrl + r`

---

### 5. Searching in Vim
Search for patterns in the text efficiently.
| **Action**| **Command** |
|------------------------------------|-------------|
| Search forward for a pattern   | `/pattern`  |
| Search backward for a pattern  | `?pattern`  |
| Move to the next occurrence| `n` |
| Move to the previous occurrence| `N` |

**Examples**:
- Search for "example": `/example`
- Search backward for "test": `?test`

---

## Advanced Actions

### Repeating Commands
Many commands can be repeated by prefixing them with a number.
- Delete 5 lines: `5dd`
- Insert "Hello" 10 times: `10iHello`, then press `Esc`.

---

## Case Manipulation
| **Action**| **Command** |
|------------------------------------|-------------|
| Toggle case of the current character | `~` |

---

## Summary of Vim Commands

| Action | Key |
|------------------------------------------------|---------|
| Move up one line   | `k` |
| Move down one line | `j` |
| Move left one character| `h` |
| Move right one character   | `l` |
| Move right one word| `w` |
| Move left one word | `b` |
| Move to the beginning of the line  | `^` |
| Move to the end of the line| `$` |
| Move to the beginning of the file  | `gg`|
| Move to the end of the file| `G` |
| Insert at the current position | `i` |
| Insert at the beginning of the line| `I` |
| Append text after the cursor position  | `a` |
| Append text at the end of the line | `A` |
| Save the file  | `:w`|
| Save the file even if permissions are not set  | `:w!`   |
| Quit the editor| `:q`|
| Quit without saving the file   | `:q!`   |
| Save and quit  | `:wq` or `:x` |
| Go to line `n` | `:n`|
| Go to the last line of the file| `:$`|
| Enable line numbering  | `:set nu` |
| Disable line numbering | `:set nonu` |
| Access the help documentation  | `:help` |
| Repeat a command with a number prefix (e.g., 3j to move down 3 lines) | `3j`, `20iText`, `80i_`  |
| Delete a character | `x` |
| Delete a word  | `dw`|
| Delete a line  | `dd`|
| Delete from the current position to the end of the line | `D` |
| Replace the current character  | `r` |
| Change the current word| `cw`|
| Change the current line| `cc`|
| Change from the current position to the end of the line | `c$`|
| Reverse the case of the current character  | `~` |
| Yank (copy) the current line   | `yy`|
| Yank a word| `yw`|
| Paste the most recent yanked text  | `p` |
| Undo the last change   | `u` |
| Redo the last undone change| `Ctrl + r` |
| Start a forward search for `<pattern>` | `/pattern` |
| Start a reverse search for `<pattern>` | `?pattern` |
| Reverse the case of the current character  | `~` |
| Move the cursor to the next word   | `w` |
| Move the cursor to the previous word   | `b` |
| Move the cursor to the beginning of the line   | `^` |
| Move the cursor to the end of the line | `$` |
| Move the cursor to the next match of a search  | `n` |
| Move the cursor to the previous match of a search | `N`   |

---

# Deleting, Moving, and Renaming Files and Directories

## Deleting Files and Directories

The `rm` command is used to remove files and directories. 

### Basic Usage

#### Remove a file:
```bash
# Syntax
rm file

# Example
sri@envy:~/Documents/Linux
$ rm temp_file 
sri@envy:~/Documents/Linux
$ 
```

#### Remove a directory:
The `-r` option is **required** to remove a directory. The option `-r` recursively removes the contents (files and subdirectories).
```bash
# Syntax
rm -r file_or_directory

# Example
sri@envy:~/Documents/Linux
$ ls
empty_dir  Linux_command_line_for_you_and_me_Release_0.1.pdf  Linux_Succinctly.pdf  README.md
sri@envy:~/Documents/Linux
$ rm -r empty_dir/
sri@envy:~/Documents/Linux
$ 
```


#### **Force remove a file or directory**:
The `-f` option forces the removal of a file or directory **without prompting for confirmation**, even if the file is write-protected.
```bash
# Syntax
rm -rf file_or_directory

# Example
sri@envy:~/Documents/Linux
$ touch write_protected_file
# Creating a touch protected file
sri@envy:~/Documents/Linux
$ chmod 444 write_protected_file 
sri@envy:~/Documents/Linux
$ rm write_protected_file 
rm: remove write-protected regular empty file 'write_protected_file'? ^C
sri@envy:~/Documents/Linux
$ rm -f write_protected_file 
sri@envy:~/Documents/Linux
$ 

```

### Using Wildcards with `rm`

Wildcards are useful for matching multiple files or directories at once.

#### Asterisk (`*`): 
Matches any string of characters, including none.
```bash
# Syntax
$ rm *.txt

# Example:
sri@envy:~/Documents/Linux
$ touch a.txt b.txt c.txt
sri@envy:~/Documents/Linux
$ ls
a.txt  c.txt                                              Linux_Succinctly.pdf
b.txt  Linux_command_line_for_you_and_me_Release_0.1.pdf  README.md
sri@envy:~/Documents/Linux
$ rm *.txt
sri@envy:~/Documents/Linux
$ ls
Linux_command_line_for_you_and_me_Release_0.1.pdf  Linux_Succinctly.pdf  README.md
sri@envy:~/Documents/Linux
$ 
```

Another example, deleting files and folders: 
```bash
sri@envy:~/Desktop
$ ls
adir  afile  bfile
sri@envy:~/Desktop
$ ls -R
.:
adir  afile  bfile

./adir:
afile
sri@envy:~/Desktop
$ rm * -r
sri@envy:~/Desktop
$ ls -R
.:
sri@envy:~/Desktop
$ 

```

#### Question mark (`?`): 
Matches exactly one character.
```bash
# Syntax
$ rm file?.txt

# Example
sri@envy:~/Documents/Linux
$ touch a.txt b.txt cc.txt
sri@envy:~/Documents/Linux
$ ls
a.txt  cc.txt                                             Linux_Succinctly.pdf
b.txt  Linux_command_line_for_you_and_me_Release_0.1.pdf  README.md
sri@envy:~/Documents/Linux
$ rm ?.txt
sri@envy:~/Documents/Linux
$ ls
cc.txt  Linux_command_line_for_you_and_me_Release_0.1.pdf  Linux_Succinctly.pdf  README.md
sri@envy:~/Documents/Linux
$ 
```

#### Hidden files: 
Files and directories that begin with a period (`.`) are considered hidden. To remove hidden files, **you need to specify the period in your search pattern**. The wild card character don't include hidden files unless explicity mentioned. 

```bash
# Syntax
$ rm .hidden_file_pattern

# Example
sri@envy:~/Documents/Linux
$ touch .a.txt .b.txt
sri@envy:~/Documents/Linux
$ ls -a
.   .a.txt  .git                                               Linux_Succinctly.pdf
..  .b.txt  Linux_command_line_for_you_and_me_Release_0.1.pdf  README.md
sri@envy:~/Documents/Linux
$ rm *.txt
rm: cannot remove '*.txt': No such file or directory
sri@envy:~/Documents/Linux
$ ls -a
.   .a.txt  .git                                               Linux_Succinctly.pdf
..  .b.txt  Linux_command_line_for_you_and_me_Release_0.1.pdf  README.md
sri@envy:~/Documents/Linux
$ rm .*.txt
sri@envy:~/Documents/Linux
$ ls -a
.   .git                                               Linux_Succinctly.pdf
..  Linux_command_line_for_you_and_me_Release_0.1.pdf  README.md
sri@envy:~/Documents/Linux
$ 
```

## Copying Files and Directories

The `cp` command is used to copy files and directories. You can create duplicates of files or move files to different locations without modifying the original.

### Basic Usage

#### Copy a file:
```bash
# Syntax
$ cp source_file destination_file_directory

# Examples
sri@envy:~/Desktop
$ ls
adir  afile
sri@envy:~/Desktop
$ cp afile bfile
sri@envy:~/Desktop
$ ls
adir  afile  bfile
sri@envy:~/Desktop
$ diff afile bfile        # no diff
sri@envy:~/Desktop
$ cp afile adir
sri@envy:~/Desktop
$ ls -R
.:
adir  afile  bfile

./adir:
afile
sri@envy:~/Desktop
$ diff afile adir/afile   # no diff
sri@envy:~/Desktop
$ 
```

#### Copy multiple files to a directory:
```bash
# Syntax
$ cp source_file1 [source_fileN ...] destination_directory

# Example
sri@envy:~/Desktop
$ ls -R
.:
a  b  c  dir

./dir:
sri@envy:~/Desktop
$ cp a b c dir
sri@envy:~/Desktop
$ ls -R
.:
a  b  c  dir

./dir:
a  b  c
sri@envy:~/Desktop
$ 
```
### Interactive Copy

Use the `-i` option to **prompt before overwriting** existing files.
```bash
# Syntax
$ cp -i source_file destination_file_folder

# Example
sri@envy:~/Desktop
$ ls -R
.:
a  b  c  dir

./dir:
a  b  c
sri@envy:~/Desktop
$ cp -i a b c dir 
cp: overwrite 'dir/a'? y
cp: overwrite 'dir/b'? n
cp: overwrite 'dir/c'? y
sri@envy:~/Desktop
$ 

```


### Copying Directories

Use the `-r` option to copy a directory and its contents.
```bash
# Syntax
$ cp -r source_directory destination_directory

# Example 1 - copying a directory into already existing directory
sri@envy:~/Desktop
$ ls -R
.:
adir  bdir

./adir:
a  b  c

./bdir:

# not mentioning -r
sri@envy:~/Desktop 
$ cp adir/ bdir/
cp: -r not specified; omitting directory 'adir/'

# mentioning -r
sri@envy:~/Desktop
$ cp -r adir/ bdir/
sri@envy:~/Desktop
$ ls -R
.:
adir  bdir

./adir:
a  b  c

./bdir:
adir

./bdir/adir:
a  b  c

# Example 2 - copying a directory to a new directory
sri@envy:~/Desktop
$ ls -R
.:
adir

./adir:
a  b  c
sri@envy:~/Desktop
$ cp -r adir/ bdir
sri@envy:~/Desktop
$ ls -R
.:
adir  bdir

./adir:
a  b  c

./bdir:
a  b  c
sri@envy:~/Desktop
$ 

```

## Moving and Renaming Files and Directories

The `mv` command is used to **move files and directories** from one location to another. It can also be used to **rename files and directories**.

### Basic Usage

#### Move a file:
```bash
# Syntax
$ mv source destination

# Example
sri@envy:~/Desktop
$ ls -R
.:
adir  d

./adir:
a  b  c
sri@envy:~/Desktop
$ mv d adir/
sri@envy:~/Desktop
$ ls -R
.:
adir

./adir:
a  b  c  d
sri@envy:~/Desktop
$ 
```

#### Move and rename a file:
```bash
# Syntax
$ mv old_name new_name

# Example
sri@envy:~/Desktop
$ touch f
sri@envy:~/Desktop
$ ls -R
.:
adir  f

./adir:
a  b  c  d
sri@envy:~/Desktop
$ mv f adir/e
sri@envy:~/Desktop
$ ls -R
.:
adir

./adir:
a  b  c  d  e
sri@envy:~/Desktop
$ 
```

### Interactive Mode

The `-i` option prompts for confirmation before overwriting an existing file.
```bash
# Syntax
$ mv -i source destination

# Example
sri@envy:~/Desktop
$ ls -R
.:
adir  e

./adir:
a  b  c  d  e
sri@envy:~/Desktop
$ mv -i e adir/
mv: overwrite 'adir/e'? n
sri@envy:~/Desktop
$ 
```

### Renaming a Directory

You can use `mv` to rename a directory in the same way you would rename a file.

```bash
# Syntax
$ mv old_directory_name new_directory_name

# Example
sri@envy:~/Desktop
$ ls -R
.:
adir

./adir:
a  b  c  d  e
sri@envy:~/Desktop
$ mv adir bdir
sri@envy:~/Desktop
$ ls -R
.:
bdir

./bdir:
a  b  c  d  e
sri@envy:~/Desktop
$ 

```
----

## Summary of Deleting, Moving, and Renaming Files and Directories Commands
Here's the updated table including the commands you provided:

| **Command**   | **Description** | **Example** |
|---------------------------------------|-----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| `rm file` | Remove a file.  | `rm test.txt` - Removes `test.txt`.|
| `rm -r file_or_directory` | Remove a directory or file recursively, including its contents. | `rm -r my_folder` - Removes the `my_folder` directory and all its contents.   |
| `rm -rf file_or_directory`| Forcefully remove a directory or file recursively without confirmation. | `rm -rf temp_folder` - Forces removal of `temp_folder` and its contents without prompts.   |
| `chmod 444 write_protected_file`  | Make a file write-protected (read-only for all users).  | `chmod 444 my_file` - Makes `my_file` read-only.   |
| `rm *.txt`| Use a wildcard to remove all `.txt` files in the current directory. | `rm *.txt` - Deletes all `.txt` files. |
| `rm * -r` | Remove all files and directories recursively in the current directory.  | `rm * -r` - Deletes everything in the current directory recursively.   |
| `rm file?.txt`| Remove files matching a single-character wildcard pattern.  | `rm file?.txt` - Deletes files like `file1.txt`, `file2.txt`, but not `file10.txt`.|
| `rm .hidden_file_pattern` | Remove hidden files matching a specific pattern.| `rm .myhiddenfile` - Removes the hidden file `.myhiddenfile`.  |
| `rm .*.txt`   | Remove hidden files with a `.txt` extension.| `rm .*.txt` - Deletes hidden `.txt` files. |
| `cp source_file destination_file_directory` | Copy a file to a specific directory.   | `cp report.pdf /documents/` - Copies `report.pdf` to the `/documents/` directory.  |
| `cp source_file1 [source_fileN ...] destination_directory` | Copy multiple files to a directory.   | `cp file1.txt file2.txt /backup/` - Copies `file1.txt` and `file2.txt` to `/backup/`.  |
| `cp -i source_file destination_directory` | Copy a file interactively, prompting before overwriting.   | `cp -i file1.txt /backup/` - Asks for confirmation before overwriting files in `/backup/`. |
| `cp -r source_directory destination_directory` | Recursively copy a directory and its contents.| `cp -r project_folder /backup/` - Copies `project_folder` and its contents to `/backup/`.  |
| `mv source destination`   | Move a file or directory to a new location.| `mv file.txt /home/user/documents/` - Moves `file.txt` to `/home/user/documents/`. |
| `mv old_name new_name`| Rename a file or directory.| `mv old_project new_project` - Renames `old_project` to `new_project`. |
| `mv -i source destination`| Move a file or directory interactively, prompting before overwriting.  | `mv -i file.txt /home/user/documents/` - Prompts before overwriting an existing file.  |

### Notes:
- The `rm` command is powerful; **use `-rf` cautiously** as it can delete critical files/directories without confirmation.
- The **`cp` and `mv` commands with the `-i` flag are highly recommended** to prevent accidental overwrites.

---

# Finding, Sorting, and Comparing Files and Directories

## Finding Files and Directories

### `find` Command
The `find` command is used to recursively search for files and directories based on different criteria, such as name, size, owner, or modification time.

```bash 
# Syntax
$ find [path...] [options] [expression]
```
- `path`: The directory path to start the search (defaults to the current directory if omitted).
- `options`: based on what should we find the file.
- `expression`: The condition used to filter the files.

### `find` Options

This table explains different variations of the `find` command in Linux, used to locate files and directories based on specific criteria. Here's a detailed explanation with examples:

---

#### 1. `find . -name pattern`
Searches for files or directories in the current directory (and subdirectories) whose names match a specific pattern. The search is case-sensitive.

```bash
# Syntax
$ find . -name name_pattern

# Example
sri@envy:~/Documents/Linux
$ find ~ -name a_file_in_linux_dir
/home/sri/Documents/Linux/a_file_in_linux_dir
sri@envy:~/Documents/Linux
$ 

```
---

#### 2. `find . -iname pattern`
Similar to `-name`, but performs a case-insensitive search.

```bash
# Syntax
$ find . -iname name_pattern

# Example
sri@envy:~/Documents/Linux
$ find ~ -name a_FiLe_iN_lInUx_DiR
sri@envy:~/Documents/Linux
$ find ~ -iname a_FiLe_iN_lInUx_DiR
/home/sri/Documents/Linux/a_file_in_linux_dir
sri@envy:~/Documents/Linux
$ 
```
---

#### 3. `find . -ls`
Executes an `ls` command for every item found, displaying detailed information like permissions, size, and timestamps.
```bash
# Syntax
$ find ~ -name name_pattern -ls

# Example
sri@envy:~/Documents/Linux
$ find ~ -name a_dir_in_linux_dir -ls
 18881987      4 drwxrwxr-x   2 sri      sri          4096 Jan  1 17:43 /home/sri/Documents/Linux/a_dir_in_linux_dir
sri@envy:~/Documents/Linux
$ 
```

In the output of the `find` command, the numbers **18881987** and **4** have specific meanings:

1. **18881987**: This number represents the **inode number** of the directory. An inode is a data structure on a filesystem that stores information about a file or directory, such as its size, owner, permissions, and location on disk. Each file and directory has a unique inode number within its filesystem, which is used by the operating system to manage files.

2. **4**: This number indicates the **number of blocks** allocated to the directory. In this context, it means that the directory `/home/sri/Documents/Linux/a_dir_in_linux_dir` occupies 4 blocks on disk. Given that many Linux filesystems use a block size of 4096 bytes (4 KB), this suggests that the directory uses approximately 16 KB of disk space.

---

#### 4. `find . -mtime number_of_days`
Searches for files that were last modified a specific number of days ago.
```bash
# Syntax
$ find . -mtime [+-]number_of_days

# Example
sri@envy:~/Documents/Linux
$ find ~/Documents/ -mtime 1
/home/sri/Documents/Nitya-Karma/README.md
/home/sri/Documents/Linux/.git/objects/b6
/home/sri/Documents/Linux/.git/objects/b6/f84a695e4cdfee5e278b2539fa04e2026777a0
...

sri@envy:~/Documents/Linux
$ find ~/Documents/ -mtime -1
/home/sri/Documents/
/home/sri/Documents/Linux
/home/sri/Documents/Linux/.git
/home/sri/Documents/Linux/.git/objects
/home/sri/Documents/Linux/.git/objects/ff
/home/sri/Documents/Linux/.git/objects/ff/b9ab4b04d3d9290a5c8d02536b35f2982b0fb5
...
```
Finds all files that were modified exactly 1 day ago. If you want files modified more than 7 days ago, use `+1`. For files modified less than 7 days ago, use `-1`.

---

#### 5. `find . -size number`
Searches for files based on their size.
```bash
# Syntax
$ find . -size [+-]size

# Example
sri@envy:~/Documents/Linux
$ find ~/Documents/ -size +10M
/home/sri/Documents/Git/.git/objects/pack/pack-352f1a32c1df039e3e03794f8f234b2e924294c0.pack
/home/sri/Documents/RIMADA/.git/objects/pack/pack-4da118e4df46c8ddf8c921dd3af165798d354ab2.pack
/home/sri/Documents/RIMADA/References/08-AIPA An Adversarial Imperceptible Patch Attack on Medical Datasets and its Interpretability.pdf
/home/sri/Documents/Introduction-to-Vedanta/.git/objects/pack/pack-18530d5e45ecc7bc0e5fbb9b66c100d02e162b2d.pack
/home/sri/Documents/Introduction-to-Vedanta/Audio/01-Purushaartha.mp3
/home/sri/Documents/Introduction-to-Vedanta/Audio/09-Sadhana_Chatusaya.mp3
/home/sri/Documents/Introduction-to-Vedanta/Audio/10-Sariratrayam.mp3
/home/sri/Documents/Introduction-to-Vedanta/Audio/08-Bhakthi.mp3
/home/sri/Documents/Introduction-to-Vedanta/Audio/11-Avasthatrayam_Pancakosa.mp3
/home/sri/Documents/Introduction-to-Vedanta/Audio/07-Jnana_Yoga.mp3
/home/sri/Documents/Introduction-to-Vedanta/Audio/03-Varna_Dharma.mp3
/home/sri/Documents/Introduction-to-Vedanta/Audio/04-Ashrama_Dharma.mp3
/home/sri/Documents/Introduction-to-Vedanta/Audio/06-Upasana_Yoga.mp3
/home/sri/Documents/Introduction-to-Vedanta/Audio/05-Karma_Yoga.mp3
/home/sri/Documents/Introduction-to-Vedanta/Audio/02-Shastram.mp3
/home/sri/Documents/Linux/.git/objects/pack/pack-125077c9ae94eb1ba567006b90b7f870c96e55d5.pack
sri@envy:~/Documents/Linux
$ 

```
Finds files larger than 10MB in size. Use `-10M` to find files smaller than 10MB or `10M` to find files exactly 10MB in size.

---

#### 6. `find . -newer file`
Finds files that were modified more recently than a specified file.
```bash
# Syntax
$ find . -newer file_or_directory

# Example
sri@envy:~/Documents/Linux
$ touch afile
sri@envy:~/Documents/Linux
$ echo hello > bfile
sri@envy:~/Documents/Linux
$ find ~/Documents -newer afile
/home/sri/Documents/Linux
/home/sri/Documents/Linux/bfile
sri@envy:~/Documents/Linux
$ 

```

---

#### 7. `find . -exec command {} \;`
Executes a specific command on each item found. The `{}` placeholder represents the found file, and `\;` indicates the end of the command.
```bash
# Syntax
$ find . -name name_pattern -exec some_commadns {} \;

# Example
sri@envy:~/Documents/Linux
$ find ~ -name bfile -exec cat {} \;
hello
sri@envy:~/Documents/Linux
$ 

```

---

### Combining `find` Options
You can combine multiple expressions to refine your search.
```bash
sri@envy:~/Documents/Linux
$ find ~ -name bfile -mtime -1 -exec cat {} \;
hello
sri@envy:~/Documents/Linux
$ 
```

### locate Command
The `locate` command is faster than `find` because it uses an **index database** updated by the `updatedb` process. However, it does not include recently created files. Also, worthy to mention the point that `find` **searches all the files in real time**, hence slower. For eg. `find ~` will run through every single file.  

```bash
# Syntax
$ locate pattern

# Example
$ locate example.txt
```
- Finds all instances of `example.txt` in the system based on the pre-built index.

**Note:** Since `locate` relies on an index, it won't find files created since the last `updatedb` run (**usually updated daily**).

---

## Sorting Files

The `sort` command is a versatile tool for sorting the contents of a file or input based on various criteria, such as by specific fields, in reverse order, or by removing duplicates. We'll demonstrate its usage using a generated table, `table.txt`.

---

### Creating a Demo Table

First, create the `table.txt` file using the following Python code:

```python
import random

with open("table.txt", "w") as f:
    rows = []
    for i in range(100): 
        row = f"{i:3}\t{random.randrange(1,100):3}\t{random.randrange(1,100):3}"
        rows.append(row)
    
    f.write("\n".join(rows))
```

Running this script generates `table.txt` with 100 rows of data. The file contains three columns, separated by tabs, as shown in the first 10 rows below:

```bash
$ head table.txt
  0	 88	 56
  1	 96	 53
  2	 71	 47
  3	 12	 59
  4	 56	 64
  5	 20	 14
  6	 45	 15
  7	 53	 57
  8	 40	 77
  9	 40	 48
```

We will use this `table.txt` for the examples below.

---

### Common `sort` Options and Examples:

| **Command**   | **Description**| **Option**   | **Example** |
|-----------------------------------------------|---------------------------------------------------|------------------|-----------------------------------------------------------------------------|
| `sort file`   | Sorts the contents of a file **line by line** | `file`   | `sort table.txt` - Sorts all rows in `table.txt` by their first column. |
| `sort -k FIELD_NUM`   | Sorts by a specific field/column | `-k FIELD_NUM`   | `sort -k 2 table.txt` - Sorts `table.txt` by the second column. |
| `sort -r` | Sorts in reverse order   | `-r` | `sort -r table.txt` - Sorts `table.txt` by the first column in descending order. |
| `sort -u` | Sorts uniquely (removing duplicates) | `-u` | `sort -u table.txt` - Removes duplicate rows while sorting `table.txt`. |

---

#### Basic Sort
The method sorts the file and returns ouptut into standard output. 
```bash
# Syntax
$ sort file

# Example
sri@envy:~/Desktop
$ sort table.txt 
  0	 88	 56
 10	 67	 99
 11	 52	 98
 12	 38	 49
 13	 24	 41
 14	 13	 54
 15	 65	 86
 16	 60	 25
 17	 18	 51
 18	 24	 79
  1	 96	 53
 19	 93	 89

```
Notice something different about the sorted output? The sort is considering the **rows as strings**.

To make it consier as number you need to use `-n` option. 
```bash
# Syntax
$ sort -n file

# Example
sri@envy:~/Desktop
$ sort -n table.txt
  0	 88	 56
  1	 96	 53
  2	 71	 47
  3	 12	 59
  4	 56	 64
  5	 20	 14
  6	 45	 15
  7	 53	 57
  8	 40	 77
  9	 40	 48
 10	 67	 99
 11	 52	 98
 12	 38	 49
 13	 24	 41
```

#### Sorting based on a column
```bash
# Syntax
$ sort -k column_number file

# Example
sri@envy:~/Desktop
$ sort -nk 2 table.txt 
 76	  1	 52
 43	  2	 96
 45	  2	 51
 65	  3	 53
 67	  5	 43
 83	  7	 79
 33	  9	 10
 61	  9	  1
 57	 11	 94
 23	 12	  9
  3	 12	 59
 14	 13	 54
 44	 13	  3
 28	 15	 22
 37	 15	 85
```

#### Sorting in Descending Order
By default sort is in **ascending** order. To sort in descending order, use `-r` option.

```bash
# Syntax
$ sort -r table.txt

sri@envy:~/Desktop # option order matters.
$ sort -nkr 2 table.txt 
sort: invalid number at field start: invalid count at start of ‘r'
sri@envy:~/Desktop
$ sort -nrk 2 table.txt 
 80	 99	 15
 31	 96	 18
  1	 96	 53
 81	 95	 44
 32	 95	 81
 21	 95	 81
 58	 94	 31
 52	 94	 22
 40	 93	 82
 39	 93	 26
 19	 93	 89
 53	 92	 54
 34	 92	 64

```

#### Sorting by Multiple Columns

To sort by multiple fields, use multiple `-k` options multiple times.

```bash
# Syntax
$ sort [-k number]+ filename

# Example
sri@envy:~/Desktop
$ sort -n -k 2 -k 1 table.txt 
 76	  1	 52
 43	  2	 96
 45	  2	 51
 65	  3	 53
 67	  5	 43
 83	  7	 79
 33	  9	 10
 61	  9	  1
 57	 11	 94
  3	 12	 59
 23	 12	  9

```
- This sorts the table first by the second column, then by the first column if there are ties in the second column.

#### Sorting rows uniquely

```bash
# Syntax
$ sort -n -u file_name

# Example - Uniquely sort based on column 2
sri@envy:~/Desktop
$ sort -n -k 2 -u table.txt
 76	  1	 52
 43	  2	 96
 65	  3	 53
 67	  5	 43
 83	  7	 79
 33	  9	 10
 57	 11	 94
  3	 12	 59
 14	 13	 54
 28	 15	 22
 59	 17	 63
 17	 18	 51
  5	 20	 14
 77	 22	 84
 13	 24	 41

```
- In the above example, we have **uniquely** sorted the table based column 2, i.e., we removed duplicate rows based on column 2. 

---


The `sort` command is highly flexible and powerful, making it an essential tool for working with structured text data.

## Comparing Files

The `diff`, `sdiff`, and `vimdiff` commands are used to compare files and directories, displaying differences in their contents.

### diff Command
The `diff` command shows the differences between two files or directories.


```bash
# Syntax
$ diff file_or_dir file_or_dir

# Example - directory
sri@envy:~/Desktop
$ ls -R
.:
a  b

./a:
f1  f2

./b:
f2  f3
sri@envy:~/Desktop
$ diff a b
Only in a: f1
Only in b: f3
sri@envy:~/Desktop
$ 

# Example - file
sri@envy:~/Desktop
$ cat a
This is line one

This is line three
sri@envy:~/Desktop
$ cat b
This is line one
This is line two
sri@envy:~/Desktop
$ diff a b
2,3c2
< 
< This is line three
---
> This is line two
sri@envy:~/Desktop
$ 

```
- The `<` symbol indicates the line from the first file, and `>` represents the line from the second file.
- `c` means "change" (line 2 was changed).

### sdiff Command
The `sdiff` command displays files side-by-side, highlighting differences.

```bash
# Syntax
$ sdiff file_or_dir file_or_dir

# Example - directory

# Example - file 
sri@envy:~/Desktop
$ sdiff a b
This is line one						This is line one
							      |	This is line two
This is line three					      <
sri@envy:~/Desktop
$ 

# Example - directory - not very intuitive
sri@envy:~/Desktop
$ ls -R
.:
adir  afile  bdir  bfile

./adir:
a  b

./bdir:
a  c
sri@envy:~/Desktop
$ sdiff adir/ bdir/
diff -y -- adir/a bdir/a
Only in adir/: b
Only in bdir/: c
sri@envy:~/Desktop
$ 

```
- Differences are shown in two columns with a pipe (`|`) separating them.

### vimdiff Command
The `vimdiff` command uses the `vim` editor to show the differences between files in a split screen.

**This is so cool!**
```bash
# Syntax
$ vimdiff file1 file2

# Example - file
sri@envy:~/Desktop
$ cat afile 
This is line one

This is line three
sri@envy:~/Desktop
$ cat bfile 
This is line one
This is line two
sri@envy:~/Desktop
$ vimdiff afile bfile 
2 files to edit
sri@envy:~/Desktop
$ 

# Example - directory
sri@envy:~/Desktop
$ cat afile 
This is line one

This is line three
sri@envy:~/Desktop
$ cat bfile 
This is line one
This is line two
sri@envy:~/Desktop
$ vimdiff afile bfile 
2 files to edit
sri@envy:~/Desktop
$ vimdiff adir/ bdir/
2 files to edit
sri@envy:~/Desktop
$ 

```

- The files will be displayed side by side within `vim`, with differences highlighted.

---

## Summary of Finding, Sorting, and Comparing Files and Directories

| **Command**   | **Description**  | **Example** |
|-----------------------------------------------|------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| `find [path...] [options] [expression]`   | General syntax of the `find` command. | `find . -name "*.txt"` - Finds all `.txt` files in the current directory.  |
| `find . -name name_pattern`   | Find files by name (case-sensitive).  | `find . -name "*.txt"` - Finds files named with a `.txt` extension.|
| `find . -iname name_pattern`  | Find files by name (case-insensitive).   | `find . -iname "*.jpg"` - Finds files named with a `.jpg` extension.   |
| `find ~ -name name_pattern -ls`   | Find files by name and list their details.| `find ~ -name "*.pdf" -ls` - Lists details for `.pdf` files in home directory. |
| `find . -mtime [+-]number_of_days`| Find files modified within a specific number of days. | `find . -mtime -7` - Finds files modified in the last 7 days.  |
| `find . -size [+-]size`   | Find files by size (e.g., +10M for files larger than 10MB).   | `find . -size +10M` - Finds files larger than 10MB. |
| `find . -newer file_or_directory` | Find files that are newer than a specific file or directory. | `find . -newer reference.txt` - Finds files modified after `reference.txt`. |
| `find . -name name_pattern -exec some_commands {} \;` | Execute a command on each found item.| `find . -name "*.log" -exec rm {} \;` - Deletes all `.log` files.  |
| `find ~ -name bfile -mtime -1 -exec cat {} \;` | Combine `find` options: find files modified in the last day and display their content. | `find ~ -name "*.txt" -mtime -1 -exec cat {} \;` - Displays contents of `.txt` files modified in the last day. |
| `locate pattern`  | Locate files by pattern using an indexed database.   | `locate myfile.txt` - Locates `myfile.txt` using the database. |
| `sort file`   | Sort the contents of a file line by line. | `sort table.txt` - Sorts rows in `table.txt` by the first column.  |
| `sort -n file`| Sort the contents of a file numerically. | `sort -n table.txt` - Sorts rows in `table.txt` numerically by the first column. |
| `sort -k column_number file`  | Sort by a specific column.   | `sort -k 2 table.txt` - Sorts `table.txt` by the second column.|
| `sort -r table.txt`   | Sort the contents of a file in reverse order.| `sort -r table.txt` - Sorts `table.txt` in reverse order.  |
| `sort [-k number]+ filename`  | Sort based on a specific column or columns.  | `sort -k 2 -k 3 table.txt` - Sorts by column 2, then column 3. |
| `sort -n -u file_name`| Sort uniquely by numeric order (removes duplicates). | `sort -n -u table.txt` - Removes duplicate rows while sorting numerically. |
| `sort -n -k 2 -u table.txt`   | Sort uniquely based on column 2 (numeric).   | `sort -n -k 2 -u table.txt` - Sorts `table.txt` uniquely by the second column. |
| `diff file_or_dir file_or_dir`| Compare two files or directories line by line.   | `diff file1.txt file2.txt` - Shows the differences between `file1.txt` and `file2.txt`. |
| `sdiff file_or_dir file_or_dir`   | Side-by-side comparison of files or directories. | `sdiff file1.txt file2.txt` - Displays a side-by-side comparison of the two files. |
| `vimdiff file1 file2` | Compare two files using `vimdiff` in Vim editor. | `vimdiff file1.txt file2.txt` - Opens a side-by-side diff view of `file1.txt` and `file2.txt`. |

---

# I/O Redirection

Linux uses a concept called **I/O streams** to handle input and output between commands and files. There are **three default I/O streams** in Linux:

- **Standard Input (stdin)**: File descriptor 0. Typically, this comes from your keyboard.
- **Standard Output (stdout)**: File descriptor 1. This is where the command output is displayed (typically on your screen).
- **Standard Error (stderr)**: File descriptor 2. This is where error messages are displayed.

Your keyboard and display are treated as files. As a matter of fact, your keyboard and display can be substituted for actual files. These streams abstract the communication between commands and files. For example, input can be taken from a file, output can be saved to a file, and error messages can be redirected to another file.

## Standard Streams Overview

| **Stream**  | **Abbreviation** | **File Descriptor** |
|---------------------|------------------|---------------------|
| Standard Input  | stdin| 0   |
| Standard Output | stdout   | 1   |
| Standard Error  | stderr   | 2   |

### File Descriptors and EOF

Many Linux commands allow you to provide input by specifying a file as an argument or by accepting standard input. In the absence of a file, many commands expect standard input. Input (like a file or standard input) is terminated by an **EOF (End of File)** marker. This can be generated by pressing `Ctrl-d` in the terminal.

If you provide a file to the `sort` command, it sorts the contents of the file:
```bash
$ sort file.txt
```
 you don't specify a file, you can provide standard input manually:
```bash
sri@envy:~/Documents/Linux
$ sort
zebra
banana
apple
watermelon
pineapple
alphabet
Newton
Alphabet
aLphabet 
^d # pressing CTRL + D
alphabet
aLphabet
Alphabet
apple
banana
Newton
pineapple
watermelon
zebra
sri@envy:~/Documents/Linux
$ 
```
(`sort`, then, type the text you want to sort. **Press `Ctrl-d` to indicate EOF**, and the text will be sorted).

## Pipes and Redirection

### Pipes
You can redirect the output of one command to be the input of another. This is done using the **pipe (`|`)** symbol.

```bash
# Syntax
$ command1 | command2 # o/p of command1 fed to command2

# Example
sri@envy:~/Documents/Linux
$ cat words
Newton
Apple
Fall
Banana
Word
Noun
Physics
Advaitam

sri@envy:~/Documents/Linux
$ cat words | sort
Advaitam
Apple
Banana
Fall
Newton
Noun
Physics
Word
sri@envy:~/Documents/Linux
$ 
```

### `grep` command

The `grep` command is a powerful and versatile text-search utility in Unix/Linux systems. It stands for **Global Regular Expression Print** and is used to search for specific patterns or strings within files or input streams. `grep` can process both simple text and more complex patterns defined by regular expressions, making it an essential tool for developers, system administrators, and anyone working with large text files or logs. `grep` is also used a lot with pipeline operator. 

```bash
# Syntax
$ grep [options] 'pattern' [file...]

# Exapmle
sri@envy:~/Documents/Linux
$ cat words
Banana
tic tac toe
Newton
Apple
tongue
Word
Kolkata
Advitam
sri@envy:~/Documents/Linux
$ grep "to" words
tic tac toe
Newton
tongue
sri@envy:~/Documents/Linux
$ 
```

- **`pattern`**: The text or regular expression to search for.
- **`file`**: The file(s) in which to search for the pattern.

#### Key Features
1. **Search for Patterns**: `grep` identifies lines containing the specified pattern.
2. **Regular Expressions**: Supports simple text matches and advanced regular expression patterns.
3. **Highlight Matches**: Displays lines containing matches and optionally highlights the matched text.
4. **Output Control**: Options to control the output format, including line numbers, file names, and match counts.

#### Common Options
- `-i`: Ignore case distinctions in the pattern and input.
- `-n`: Prefix each line of output with its line number.
- `-v`: Invert the match to display lines that do not contain the pattern.
- `-c`: Count the number of matching lines.
- `-l`: List only the names of files with matches.
- `-r` or `-R`: Recursively search through directories.
- `-E`: Use extended regular expressions (same as `egrep`).
- `-w`: Match whole words only.


##### Case-Insensitive Search
```bash
# Syntax
$ grep -i pattern file

# Example
sri@envy:~/Documents/Linux
$ grep -i ^a words
Apple
Advitam
sri@envy:~/Documents/Linux
$ 
```
Matches "hello", "Hello", or "HELLO".

##### Printing line number
```bash
# Syntax
$ grep -n pattern file

# Example
sri@envy:~/Documents/Linux
$ grep -n ^a -i words
4:Apple
8:Advitam
sri@envy:~/Documents/Linux
$ cat words
Banana
tic tac toe
Newton
Apple
tongue
Word
Kolkata
Advitam
sri@envy:~/Documents/Linux
$ 
```
Matches "hello", "Hello", or "HELLO".

##### Search Multiple Files
```bash
# Syntax
$ grep pattern file[s]

# Example
sri@envy:~/Documents/Linux
$ cat words
Banana
tic tac toe
Newton
Apple
tongue
Word
Kolkata
Advitam
sri@envy:~/Documents/Linux
$ cat words2
Advitam
Apple
Kolkata
Newton
Word
sri@envy:~/Documents/Linux
$ grep "to" words words2
words:tic tac toe
words:Newton
words:tongue
words2:Newton
sri@envy:~/Documents/Linux
$ 
```

##### Recursive Search
Searches for pattern in all files under the specified directory.

```bash
# Syntax
$ grep -r pattern fire_or_directory

# Example
sri@envy:~
$ grep -r "README.md" ~/Documents/
/home/sri/Documents/Git/git.md:echo "# Python-DSA" >> README.md
/home/sri/Documents/Git/git.md:README.md  names.txt
grep: /home/sri/Documents/Git/.git/index: binary file matches
grep: /home/sri/Documents/Nitya-Karma/.git/index: binary file matches
/home/sri/Documents/Nitya-Karma/.git/logs/HEAD:dc55b16f833efd61c211cc7b507a46359435227a 7209a19e2493a41279b298066b69d0e7edfa6e99 rnaveensrinivas <rnaveensrinivas@gmail.com> 1735209294 +0530	commit: updated README.md
/home/sri/Documents/Nitya-Karma/.git/logs/HEAD:7209a19e2493a41279b298066b69d0e7edfa6e99 ca450131a696ccade628fb2af533cd1c23a6bc18 rnaveensrinivas <rnaveensrinivas@gmail.com> 1735209366 +0530	commit: updated README.md
grep: /home/sri/Documents/Vim/.git/index: binary file matches
grep: /home/sri/Documents/Python-DSA/.git/index: binary file matches
/home/sri/Documents/Linux/README.md:Linux_command_line_for_you_and_me_Release_0.1.pdf  Linux_Succinctly.pdf  README.md
/home/sri/Documents/Linux/README.md:$ cat /home/sri/Documents/Linux/README.md 
/home/sri/Documents/Linux/README.md:$ tail -5 README.md 
/home/sri/Documents/Linux/README.md:empty_dir  Linux_command_line_for_you_and_me_Release_0.1.pdf  Linux_Succinctly.pdf  README.md
/home/sri/Documents/Linux/README.md:b.txt  Linux_command_line_for_you_and_me_Release_0.1.pdf  README.md
/home/sri/Documents/Linux/README.md:/home/sri/Documents/Nitya-Karma/README.md
grep: /home/sri/Documents/Python/.git/index: binary file matches

grep -r "function" /path/to/directory
```

##### Listing only filenames that match

```bash
# Syntax
$ grep -rl pattern fire_or_directory

# Example
sri@envy:~/Documents/Linux
$ grep -rl "README.md" ~/Documents/
/home/sri/Documents/Git/git.md
/home/sri/Documents/Git/.git/index
/home/sri/Documents/Nitya-Karma/.git/index
/home/sri/Documents/Nitya-Karma/.git/logs/HEAD
/home/sri/Documents/Nitya-Karma/.git/logs/refs/heads/main
/home/sri/Documents/Nitya-Karma/README.md
/home/sri/Documents/Vim/.git/index
/home/sri/Documents/Python-DSA/.git/index
/home/sri/Documents/RIMADA/.git/index
/home/sri/Documents/Introduction-to-Vedanta/.git/index
/home/sri/Documents/Introduction-to-Vedanta/.git/logs/HEAD
/home/sri/Documents/Introduction-to-Vedanta/.git/logs/refs/heads/main
/home/sri/Documents/Introduction-to-Vedanta/.git/COMMIT_EDITMSG
/home/sri/Documents/Markdown/.git/index
/home/sri/Documents/Power-Of-Posture/.git/index
/home/sri/Documents/Linux/.git/index
/home/sri/Documents/Linux/README.md
/home/sri/Documents/Python/.git/index
/home/sri/Documents/Vocabulary/.git/index
sri@envy:~/Documents/Linux
$ 
```


##### Exclude Lines
```bash
# Syntax
$ grep -v pattern file

# Example
sri@envy:~/Documents/Linux
$ grep -v a words
Newton
Apple
tongue
Word
sri@envy:~/Documents/Linux
$ grep -iv a words
Newton
tongue
Word
sri@envy:~/Documents/Linux
$ 
```
Displays all lines in `word` except those containing "a".

##### Count Matches
```bash
# Syntax
$ grep -c pattern file

# Example
sri@envy:~/Documents/Linux
$ grep ^a -i words
Apple
Advitam
sri@envy:~/Documents/Linux
$ grep -c ^a -i words
2
sri@envy:~/Documents/Linux
$ 
```
Counts the number of lines containing words starting with letter 'a'.

##### Match Whole words
```bash
# Syntax
$ grep -w pattern file

# Example
sri@envy:~/Documents/Linux
$ grep -w a words
sri@envy:~/Documents/Linux
$ grep -wi apple words
Apple
sri@envy:~/Documents/Linux
$ 
```

##### Using Extended Regular Expression
grep -E '[0-9]{4}-[0-9]{2}-[0-9]{2}' log.txt
```bash
# Syntax
$ grep -E pattern file

# Example - matching all dates
sri@envy:~/Documents/Linux
$ cat file
2025-01-02
Hi hello 
Bye
2025-01-01
It's 2025 already!
sri@envy:~/Documents/Linux
$ grep -E '[0-9]{4}-[0-9]{2}-[0-9]{2}' file 
2025-01-02
2025-01-01
sri@envy:~/Documents/Linux
$ grep -nE '[0-9]{4}-[0-9]{2}-[0-9]{2}' file 
1:2025-01-02
4:2025-01-01
sri@envy:~/Documents/Linux
$ 
```

#### Use Cases
- **Log Analysis**: Quickly find errors or specific events in log files.
- **Code Search**: Locate functions, variables, or comments in source code files.
- **Data Extraction**: Filter large datasets for specific records.
- **Configuration Management**: Check settings in configuration files.

### Redirecting Input and Output

#### Input Redirection 
To use the contents of a file as standard input, use the **less than sign (`<`)**:
```bash
# Syntax
$ command < file

# Example
sri@envy:~/Documents/Linux
$ sort < words
Advaitam
Apple
Banana
Fall
Newton
Noun
Physics
Word
sri@envy:~/Documents/Linux
$ 
```

#### Output Redirection 
To redirect the output of a command to a file, use the **greater than sign (`>`)**:
```bash
# Syntax
$ command > file

# Example
sri@envy:~/Documents/Linux
$ echo "hello, world" > output.txt
sri@envy:~/Documents/Linux
$ cat output.txt 
hello, world
sri@envy:~/Documents/Linux
$ 
```
If the file does not exist, it will be created. If it does exist, it will be overwritten.

#### Appending Output to a File
To append output to a file, use the **double greater than sign (`>>`)**:
```bash
# Syntax
$ Command >> file

sri@envy:~/Documents/Linux
$ echo "hello, world" > output.txt
sri@envy:~/Documents/Linux
$ cat output.txt 
hello, world
sri@envy:~/Documents/Linux
$ echo "hello, world" > output.txt
sri@envy:~/Documents/Linux
$ cat output.txt 
hello, world
sri@envy:~/Documents/Linux
$ echo "hello, world" >> output.txt
sri@envy:~/Documents/Linux
$ cat output.txt 
hello, world
hello, world
sri@envy:~/Documents/Linux
$ 
```

### Redirection with Specific File Descriptors

You can explicitly reference file descriptors when redirecting input or output. **Note**, `1>` is equivalent to `>`. 

The following example shows how to redirect standard error to a file:

```bash
# Syntax
$ command 2> error_file
$ command 1> output_file

# Examples - redirection of errors to error_file
sri@envy:~/Desktop
$ unkown_command 2> error_file
sri@envy:~/Desktop
$ cat error_file 
unkown_command: command not found
sri@envy:~/Desktop
$ 

sri@envy:~/Desktop # not providing redirection for errors, hence in stdout
$ unknown_command 1> output_file
unknown_command: command not found
sri@envy:~/Desktop
$ ls 1> output_file # redirecting output to output_file
sri@envy:~/Desktop
$ cat output_file 
adir
afile
bdir
bfile
error_file
output_file
sri@envy:~/Desktop
$ 

```

### Redirecting Both Standard Output and Standard Error

You can combine both **standard output** and **standard error** into one file. Use the **`2>&1`** syntax to redirect both streams to the same destination:

```bash
# syntax
$ command > file 2>&1
```
The above command has got three parts: 
1. `command` - when run, will generate errors and outputs. 
2. `> file` - tells that standard output to be redirected to `file`.
   * `> file` is equivalent to `1> file`
3. `2>&1`- tells that standard output to be redirected to `&1` **reference of 1**, which is `file`.

```bash
# Example
sri@envy:~/Desktop
$ ls >> output_file 2>&1
sri@envy:~/Desktop
$ cat output_file 
adir
afile
bdir
bfile
error_file
output_file

sri@envy:~/Desktop
$ ls -fsw >> output_file 2>&1

sri@envy:~/Desktop
$ cat output_file 
adir
afile
bdir
bfile
error_file
output_file
ls: option requires an argument -- 'w'
Try 'ls --help' for more information.
sri@envy:~/Desktop
$ 

```

### Redirecting to `/dev/null`

If you don't want to display the output or error of a command (or save it to a file), you can discard it by redirecting it to the **null device** (`/dev/null`). This "**bit bucket**" or "**black hole**" discards anything sent to it.

> In Linux, Black Hole and Bit Bucket are colloquial terms used to describe the special device file `/dev/null`. This file is used to discard any data sent to it. It acts as a data sink, meaning anything written to it is immediately and permanently discarded. 
>
> **How They Work**
> 
> **Black Hole**: The idea comes from the analogy of a black hole in space, which absorbs everything without letting anything escape. Similarly, `/dev/null` accepts any input and discards it without storing or processing.
> 
> **Bit Bucket**: Refers to a conceptual "bucket" where unwanted or unnecessary bits of data are dumped, never to be retrieved.

#### Redirecting standard output
```bash
# Syntax
$ command > /dev/null

# Example
sri@envy:~/Desktop
$ ls > /dev/null
sri@envy:~/Desktop
$ 
```

#### Redirecting standard error
```bash
# Syntax
$ command 2> /dev/null

# Example
sri@envy:~/Desktop
$ invalid_command 2> /dev/null
sri@envy:~/Desktop
$ 
```

#### Redirecting both output and error
```bash
# Syntax
$ command > /dev/null 2>&1

# Example
sri@envy:~/Desktop
$ invalid_command > /dev/null 2>&1
sri@envy:~/Desktop
$ 
```

### More Complex Examples

#### Reading from a file and redirecting output
```bash
# Syntax
$ command < file > command

# Example
sri@envy:~/Documents/Linux
$ vi words
sri@envy:~/Documents/Linux
$ sort < words
Advitam
Apple
Kolkata
Newton
Word
sri@envy:~/Documents/Linux
$ sort < words > sorted_words
sri@envy:~/Documents/Linux
$ cat sorted_words 
Advitam
Apple
Kolkata
Newton
Word
sri@envy:~/Documents/Linux
$ 
```


#### Using pipes and redirecting output
```bash
# Syntax
$ command | command > file

# Example
sri@envy:~/Documents/Linux
$ cat sorted_words | grep a
Advitam
Kolkata
sri@envy:~/Documents/Linux
$ cat sorted_words | grep -i a
Advitam
Apple
Kolkata
sri@envy:~/Documents/Linux
$ cat sorted_words | grep -i a > sorted_words_with_letter_a
sri@envy:~/Documents/Linux
$ cat sorted_words_with_letter_a 
Advitam
Apple
Kolkata
sri@envy:~/Documents/Linux
$ 
```

## Summary of I/O Redirection Commands


| Command| Description |
|----------------------------------------|-----------------------------------------------------------------------------|
| `sort`   | Sorts input lines alphabetically. Pressing `CTRL + D` acts as EOF.  |
| `command1 \| command2`   | Feeds the output of `command1` as input to `command2`.  |
| `grep [options] 'pattern' [file...]`   | Searches for a pattern in the given file(s).|
| `grep -i pattern file` | Performs a case-insensitive search for the pattern in the file. |
| `grep pattern file[s]` | Searches for the pattern in one or more files.  |
| `grep -i ^a words`   | Finds lines starting with `a` (case-insensitive) in the file `words`.   |
| `grep -n pattern file`   | Displays line numbers along with matching lines.|
| `grep -r pattern file_or_directory`  | Recursively searches for the pattern in files and subdirectories.   |
| `grep -rl pattern file_or_directory` | Lists file names containing the pattern (recursive search). |
| `grep -v pattern file` | Displays lines that do not match the pattern.   |
| `grep -c pattern file`   | Counts the number of lines matching the pattern.|
| `grep -w pattern file`   | Matches the whole word pattern in the file. |
| `grep -E pattern file`   | Uses extended regular expressions for pattern matching. |
| `command < file` | Redirects the content of `file` as input to `command`.  |
| `command > file`   | Redirects the output of `command` to `file` (overwriting if exists).|
| `command >> file`   | Appends the output of `command` to `file`|
| `command 2> error_file`  | Redirects standard error (stderr) to `error_file`.  |
| `command 1> output_file` | Redirects standard output (stdout) to `output_file`.|
| `command > file 2>&1`| Redirects both stdout and stderr to `file`. |
| `ls >> output_file 2>&1` | Appends both stdout and stderr of `ls` to `output_file`.|
| `ls -fsw >> output_file 2>&1`| Appends `ls` output with flags `-fsw` to `output_file`, including errors.   |
| `command > /dev/null`| Discards stdout by redirecting it to `/dev/null`.   |
| `command 2> /dev/null`   | Discards stderr by redirecting it to `/dev/null`.   |
| `command < file > command`   | Redirects `file` as input and outputs to another `command`. |
| `command \| command > file`   | Pipes output from one command and redirects it to a file.   |

---

# Additional Command Line Concepts

## Environment Variables
Environment variables are name-value pairs that provide information to processes about the environment in which they run. These variables help programs adjust their behavior based on the environment. They are **case-sensitive** and typically written in **uppercase letters separated by underscore**.

### Common Environment Variables
| **Variable** | **Description**  |
|--------------|------------------|
| `EDITOR` | The program used to edit files. |
| `HOME`   | The user's home directory. |
| `LOGNAME`| The user ID or login ID of the current user. |
| `MAIL`   | The location of the user's mailbox on the local system. |
| `OLDPWD` | The old, or previous, working directory. |
| `PATH`   | The search path for commands. |
| `PAGER`  | The program used for paging through a file. |
| `PS1`| The primary prompt string. |
| `PWD`| The present working directory. |

### Viewing Environment Variables

Use `echo $VAR_NAME` to view the value of a specific environment variable.

```bash
# Syntax
$ echo $ENVIRONMENT_VARIABLE

# Example
sri@envy:~/Documents/Linux
$ echo $OLDPWD 
/home/sri/Documents/Linux
sri@envy:~/Documents/Linux
$ 
```

Alternatively, you can use the `printenv` command: `printenv VAR_NAME` to print the value of the variable.

```bash
# Syntax
$ printenv ENVIRONMENT_VARIABLE

# Example
sri@envy:~/Documents/Linux
$ printenv OLDPWD 
/home/sri/Documents/Linux
sri@envy:~/Documents/Linux
$ 
```

- To display all environment variables, simply run `env` or `printenv` without arguments.

```bash
# Syntax
$ printev
$ env

# Examples
sri@envy:~/Documents/Linux
$ printenv
SHELL=/bin/bash
COLORTERM=truecolor
XDG_MENU_PREFIX=gnome-
DESKTOP_SESSION=ubuntu
PWD=/home/sri/Documents/Linux
LOGNAME=sri
XDG_SESSION_DESKTOP=ubuntu
sri@envy:~/Documents/Linux
$ env**case-sensitive**
...
```

### Setting and Exporting Variables
You can set an environment variable using:  
```bash
# Syntax
$ VAR_NAME=value

# Example
sri@envy:~/Documents/Linux
$ A_NEW_ENV_VAR="hello"
sri@envy:~/Documents/Linux
$ echo $A_NEW_ENV_VAR 
hello
sri@envy:~/Documents/Linux
$
```
Do not include `$` at the start. 

In Linux and Unix-like systems, variables set in a shell are by default **local to that shell** and are not available to subprocesses (child processes) or commands invoked from the shell. To make a variable accessible to subprocesses, you need to **export** it.

The `export` command marks a variable to be passed into the environment of subprocesses, ensuring they can access it.

```bash
# Syntax
$ export VAR_NAME=value
# OR
$ VAR_NAME=value
$ export VAR_NAME

# Example
sri@envy:~/Documents/Linux
$ A_NEW_ENV_VAR='hello'
sri@envy:~/Documents/Linux
$ echo $A_NEW_ENV_VAR 
hello
```

---

#### How It Works

##### Without `export`:
```bash
sri@envy:~/Documents/Linux
$ A_NEW_ENV_VAR='hello'
sri@envy:~/Documents/Linux
$ echo $A_NEW_ENV_VAR 
hello
sri@envy:~/Documents/Linux      # outputs nothing
$ bash -c 'echo $A_NEW_ENV_VAR'

sri@envy:~/Documents/Linux
$ 

```
The variable `VAR_NAME` is not available in the child `bash` process.

##### With `export`:
```bash
sri@envy:~/Documents/Linux
$ export A_NEW_ENV_VAR 
sri@envy:~/Documents/Linux      # outputs hello
$ bash -c 'echo $A_NEW_ENV_VAR'
hello
sri@envy:~/Documents/Linux
$ 

```
The `export` command ensures `VAR_NAME` is included in the environment of the child process.

---

#### Key Points
1. **Persistent in Child Processes**: Exported variables are available only to the child processes of the shell that set them. They are not automatically preserved across login sessions or new shells unless stored in shell configuration files like `.bashrc` or `.profile`.

2. **Environment Variables**: Exported variables become **environment variables**, accessible to scripts, commands, and other processes.

3. **Temporary for Session**: Exported variables exist only for the duration of the shell session unless added to configuration files.

---


### Removing Environment Variables
To remove an environment variable, use the `unset` command:
```bash
# Syntax
$ unset VAR_NAME

# Example
sri@envy:~/Documents/Linux
$ unset A_NEW_ENV_VAR 
sri@envy:~/Documents/Linux
$ printenv A_NEW_ENV_VAR
sri@envy:~/Documents/Linux
$ 
```

---

## Aliases
Aliases allow you to create shortcuts for commands that you frequently use, saving you time and reducing the need for long or complex commands.

### Creating and Managing Aliases

#### To create an alias
```bash
# Syntax
$ alias alias_name='command'

# Example
sri@envy:~/Documents/Linux
$ alias ll='ls -l'

sri@envy:~/Documents/Linux
$ ll
total 3248
-rw-rw-r-- 1 sri sri  734199 Dec 21 17:42 Linux_command_line_for_you_and_me_Release_0.1.pdf
-rw-rw-r-- 1 sri sri 2349921 Dec 21 17:42 Linux_Succinctly.pdf
-rw-rw-r-- 1 sri sri  237289 Jan  2 06:53 README.md
sri@envy:~/Documents/Linux
$ 
```

#### To list all current aliases:
```bash
# Syntax
alias

# Example
sri@envy:~/Documents/Linux
$ alias
alias calendar='open https://calendar.google.com/'
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias firefox='firefox & disown'
alias gpt='open https://chatgpt.com/'
alias grep='grep --color=auto'
alias ls='ls --color=auto'
alias python='python3'
sri@envy:~/Documents/Linux
$ 
```

#### To remove an alias:
```bash
# Syntax
$ unalias alias_name

# Example
sri@envy:~/Documents/Linux
$ unalias ll
sri@envy:~/Documents/Linux
$ ll
ll: command not found
sri@envy:~/Documents/Linux
$ 
```

#### To remove all aliases:
```bash
# Syntax
$ unalias -a

# Example
sri@envy:~/Documents/Linux
$ unalias -a
sri@envy:~/Documents/Linux
$ gpt
Command 'gpt' not found, but can be installed with:
sudo apt install gpt
sri@envy:~/Documents/Linux
$ 

```

### Persistent Aliases
Aliases are only available for the current session. To make them persistent, add them to your personal initialization files such as `~/.bashrc` or `~/.bash_profile`.

---

## Personal Initialization Files
Personal initialization files are used to save customizations to your shell environment. Personal initialization files are often referred to as "**dot files**."

### Files Used for Customization
- `~/.bash_profile`: Read and executed for login shells.
- `~/.bashrc`: Read and executed for non-login shells (like when opening a new terminal tab).

In recent verions of Linux Distros, `.bash_profile` is removed, and `.bashrc` is used. However, if you have both, you can make `~/.bash_profile` source `~/.bashrc`, by adding the following line to `~/.bash_profile`:
```bash
if [ -f ~/.bashrc ]; then
  . ~/.bashrc
fi
```

### Using the `source` Command
The `source` command allows you to load configurations or scripts into the current shell:
```bash
# Syntax
$ source ~/.bashrc

# Example
sri@envy:~/Documents/Linux
$ echo "la='ls -a'" >> ~/.bashrc
sri@envy:~/Documents/Linux
$ tail -1 ~/.bashrc
la='ls -a'
sri@envy:~/Documents/Linux
$ alias
alias l='ls -CF'
alias ll='ls -alF'
alias ls='ls --color=auto'
sri@envy:~/Documents/Linux
$ la
la: command not found
sri@envy:~/Documents/Linux
$ source ~/.bashrc
sri@envy:~/Documents/Linux
$ la
.git  Linux_command_line_for_you_and_me_Release_0.1.pdf  Linux_Succinctly.pdf  README.md
sri@envy:~/Documents/Linux
$ 

```
Alternatively, you can use a dot (`.`) as a shortcut for `source`:
```bash
$ . ~/.bashrc
```

---

## Shell History
Bash retains the commands you execute during a session in memory, saving them to `~/.bash_history` when the session ends. You can configure the number of commands stored by setting the `HISTSIZE` environment variable.

```bash
sri@envy:~/Documents/Linux
$ echo $HISTSIZE
1000
sri@envy:~/Documents/Linux
$ 
```

### Commands for Managing History
#### `history`
Displays the list of commands from your shell history.
```bash
# Syntax
$ history

# Example
sri@envy:~/Documents/Linux
$ history
 1042  jobs
 1043  sleep 30 &
 1044  jobs
 1045  clear
 1046  jobs
 ...
 2037  echo $HISTSIZE
 2038  history 
 2039  clear
 2040  ls -a
 2041  history
```

#### `!N`
Repeats the command from line number N in history. This will replace the prompt with that command in history, and then execution takes place. Since the prompt is replaced, that particular command will be registerd in history. 

```bash
# Syntax
$ !Number_from_history

# Example
sri@envy:~/Documents/Linux
$ history
...
 2035  printenv HISTSIZE 
 2036  echo $HIST
 2037  echo $HISTSIZE
 2038  history 
 2039  clear
 2040  ls -a
 2041  history
sri@envy:~/Documents/Linux
$ !2037
echo $HISTSIZE
1000
sri@envy:~/Documents/Linux
$ history
 ...
 2036  echo $HIST
 2037  echo $HISTSIZE
 2038  history 
 2039  clear
 2040  ls -a
 2041  history
 2042  echo $HISTSIZE # actual command stored instead of !2037
 2043  history

```

#### `!!`
Repeats the last command executed.

```bash
# Syntax
$ !!

# Example
sri@envy:~/Documents/Linux
$ echo $HISTSIZE
1000
sri@envy:~/Documents/Linux
$ !!
echo $HISTSIZE
1000
sri@envy:~/Documents/Linux
$ 
```

#### `!pattern` 
Repeats the most recent command that starts with the specified pattern.
```bash
# Syntax
$ !pattern

# Example
sri@envy:~/Documents/Linux
$ echo $HISTSIZE
1000
sri@envy:~/Documents/Linux
$ !!
echo $HISTSIZE
1000
sri@envy:~/Documents/Linux
$ !echo
echo $HISTSIZE
1000
sri@envy:~/Documents/Linux
$ 
```

### Searching Command History in Linux Shell

The Linux shell maintains a history of previously executed commands, allowing you to quickly recall and reuse them. One of the most efficient ways to search this history is using **reverse search** with `Ctrl-r`.

---

#### Reverse Search with `Ctrl-r`

##### 1. Initiate Reverse Search
Press `Ctrl-r` to start a reverse search. The prompt will change to:
```bash
(reverse-i-search)`':
```
This indicates that you are now in reverse search mode.

#### 2. Type Search Term
Begin typing a part of the command you want to find. For example, typing `grep` will search for the most recent command containing `grep`.

#### 3. Navigate Through Matches
If the first match isn't the desired command, press `Ctrl-r` again to search for the next match further back in history.

#### 4. Exit Reverse Search
Once you find the desired command:
- **Run the Command**: Press `Enter` to execute it immediately.
- **Edit Before Running**: Press `Esc` or the arrow keys to exit reverse search mode, allowing you to edit the command in the shell prompt before running it.

---

#### Key Tips
- **Stop Searching**: Press `Ctrl-g` or `Ctrl-c` to cancel the reverse search and return to the regular shell prompt.
- **Partial Search**: You don't need to type the entire command; even a few characters are sufficient to find a match.
- **Repeat Forward Search**: If you overshoot the command you wanted, use `Ctrl-s` to move forward in history (may require enabling with `stty -ixon`).

---

### Practical Example

Suppose you ran these commands earlier in the session:
```bash
$ ls -l /var/log
$ grep error log.txt
$ sudo apt update
$ cat /etc/passwd
```

Now you want to re-execute the `grep` command:
1. Press `Ctrl-r` and type `grep`.
   ```
   (reverse-i-search)`grep': grep error log.txt
   ```
2. If this is the desired command, press `Enter` to execute it. If it is not desired you can add more text by punching in some more keys, or press `Ctrl-r` for another match.
3. If you want to edit it (e.g., change `error` to `warning`), press `Esc` or an arrow key to modify it before running.

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
# Syntax 
$ echo "words .. \
more words "

# Example
sri@envy:~/Documents/Linux
$ echo "this is line one \
> this is line two \
> this is line three"
this is line one this is line two this is line three
sri@envy:~/Documents/Linux
$ 
```
This will be interpreted as a single command. The continued lines are prefixed with the greater-than symbol (`>`).

---

## Summary of Additional Command Line Concept Commands

| Command| Description |
|--------------------------------------------|-----------------------------------------------------------------------------|
| `echo $ENVIRONMENT_VARIABLE` | Displays the value of the specified environment variable.   |
| `printenv ENVIRONMENT_VARIABLE`  | Prints the value of the specified environment variable. |
| `printenv`   | Lists all environment variables and their values.   |
| `env`| Displays the current environment, including variables.  |
| `VAR_NAME=value` | Creates a shell variable `VAR_NAME` with the specified value.   |
| `export A_NEW_ENV_VAR`   | Marks `A_NEW_ENV_VAR` as an environment variable available to subprocesses. |
| `bash -c 'echo $A_NEW_ENV_VAR'`  | Runs a subshell and prints the value of `A_NEW_ENV_VAR` in it.  |
| `unset VAR_NAME` | Deletes the shell variable or environment variable `VAR_NAME`.  |
| `alias alias_name='command'` | Creates a shortcut (`alias_name`) for the specified command.|
| `alias`  | Lists all currently defined aliases.|
| `unalias alias_name` | Removes the specified alias.|
| `unalias -a` | Removes all aliases.|
| `source ~/.bashrc` or `. ~/.bashrc`  | Reloads the shell configuration file (`.bashrc`).   |
| `echo $HISTSIZE` | Displays the maximum number of commands stored in the shell history.|
| `history`| Lists the command history.  |
| `!Number_from_history`   | Re-executes the command at the specified history number.|
| `!!` | Re-executes the last command.   |
| `!pattern`   | Re-executes the most recent command matching the pattern.   |
| `Ctrl + r; pattern; Ctrl + r`  | Initiates reverse search in command history for a matching pattern. |
| `Ctrl + c` or `<esc>`  | Cancels or exits reverse search.|
| **Tab Completion** | Auto-completes commands or file names.  |
| `echo "words .. \ more words "`  | Concatenates lines using `\` for multiline command input.   |
---

# Processes and Jobs 

## Processes

### What is a Process?  

A **process** is a program that is being executed by the operating system. It has a unique **process ID (PID)** and represents the actual execution of code in the system. Processes are **managed by the Linux kernel, not the shell**. 

The `ps` command gives information about currently running processes. Other commands to monitor and manage processes are `top`, `htop`, and `pstree` .

---

## The `ps` Command

The `ps` (**process status**) command provides a snapshot of the currently running processes on your system. By default, `ps` shows processes associated with your current terminal session.

```bash
# Syntax
$ ps

# Example
sri@envy:~/Documents/Linux
$ ps
    PID TTY          TIME CMD
   3151 pts/0    00:00:00 bash
   3298 pts/0    00:00:08 firefox
   3458 pts/0    00:00:00 Socket Process
   3472 pts/0    00:00:03 Isolated Web Co
   3685 pts/0    00:00:02 WebExtensions
   3883 pts/0    00:00:00 Utility Process
   3890 pts/0    00:00:00 Web Content
   3892 pts/0    00:00:00 Web Content
   4066 pts/0    00:00:00 Web Content
   4592 pts/0    00:00:00 ps
```
* **`pts/0`** means, ***pseudo terminal 0***, which denotes a terminal session. 
* Open a new terminal tab and type the command `ps` again. 
  ```bash
  sri@envy:~/Documents/Linux
  $ ps
      PID TTY          TIME CMD
    4613 pts/1    00:00:00 bash
    4620 pts/1    00:00:00 ps
  sri@envy:~/Documents/Linux
  $ 
  ```
  * We have `pts/1` here, because this is a new terminal session. 

### Commonly Used Options with `ps`

The `ps` command has several options to control the level of detail displayed in its output.

| **Description** | **Option**   |
|-----------------------------------------|------------------|
| Display all processes   | `-e` |
| Use a full-format listing   | `-f` |
| Display processes for a specific user   | `-u <username>`  |
| Display processes by process ID (PID)   | `-p <PID>`   |
| Display processes in a hierarchical format (tree) | `-H` |
| Display processes in a tree format using ASCII art | `--forest` |

### Commonly Used `ps` Commands

| **Command** | **Description** |
|------------------|-------------------------------------------------------------|
| `ps -e`   | Display all processes.   |
| `ps -ef`  | Display all processes using a full format listing.   |
| `ps -eH`  | Display all processes in a tree format.  |
| `ps -e --forest`  | Display all processes in a tree format with ASCII art.   |
| `ps -u <username>` | Display processes running for username. |
| `ps -fp <PID>`| Display a full-format listing for process ID (PID).  |


#### Display every process running on the system:
To see all processes running on the system, regardless of the user or terminal, use:
```bash
# Syntax
$ ps -e

# Example
sri@envy:~
$ ps -e
    PID TTY          TIME CMD
      1 ?        00:00:01 systemd
      2 ?        00:00:00 kthreadd
      3 ?        00:00:00 pool_workqueue_release
      4 ?        00:00:00 kworker/R-rcu_g
      5 ?        00:00:00 kworker/R-rcu_p
      6 ?        00:00:00 kworker/R-slub_
      7 ?        00:00:00 kworker/R-netns

...
```

#### Display all processes with a full format listing:
```bash
# Syntax
$ ps -f

# Example
sri@envy:~
$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 16:44 ?        00:00:01 /sbin/init splash
root           2       0  0 16:44 ?        00:00:00 [kthreadd]
root           3       2  0 16:44 ?        00:00:00 [pool_workqueue_release]
root           4       2  0 16:44 ?        00:00:00 [kworker/R-rcu_g]
root           5       2  0 16:44 ?        00:00:00 [kworker/R-rcu_p]
root           6       2  0 16:44 ?        00:00:00 [kworker/R-slub_]
root           7       2  0 16:44 ?        00:00:00 [kworker/R-netns]
root           8       2  0 16:44 ?        00:00:00 [kworker/0:0-events]
root          10       2  0 16:44 ?        00:00:00 [kworker/0:0H-events_highpri]
...

```

#### Display all running processes for your user:
To display all processes running under your username, use the following command:
```bash
# Syntax
$ ps -u username

# Example
sri@envy:~
$ ps -u sri
    PID TTY          TIME CMD
   2105 ?        00:00:00 systemd
   2109 ?        00:00:00 (sd-pam)
   2121 ?        00:00:00 pipewire
   2122 ?        00:00:00 pipewire
   2125 ?        00:00:00 wireplumber
   2132 ?        00:00:00 pipewire-pulse
   2133 ?        00:00:00 gnome-keyring-d
   2140 ?        00:00:00 dbus-daemon
   2170 ?        00:00:00 xdg-document-po

```

#### Display information for a specific process ID (PID):
```bash
# Syntax
$ ps -p <pid>

# Example
sri@envy:~
$ ps -p 2105
    PID TTY          TIME CMD
   2105 ?        00:00:00 systemd


# Order of arguments matter
sri@envy:~
$ ps -p 2105
    PID TTY          TIME CMD
   2105 ?        00:00:00 systemd
sri@envy:~
$ ps -pf 2105
error: process ID list syntax error

Usage:
 ps [options]

 Try 'ps --help <simple|list|output|threads|misc|all>'
  or 'ps --help <s|l|o|t|m|a>'
 for additional help text.

For more details see ps(1).
sri@envy:~
$ ps -fp 2105
UID          PID    PPID  C STIME TTY          TIME CMD
sri         2105       1  0 16:48 ?        00:00:00 /usr/lib/systemd/systemd --user
sri@envy:~
$ 

```

#### Display processes in a hierarchical (tree) format:
```bash
# Syntax
$ ps -eH

# Example
sri@envy:~
$ ps -H -u sri
    PID TTY          TIME CMD
   2209 tty2     00:00:00 gdm-wayland-ses
   2217 tty2     00:00:00   gnome-session-b
   2105 ?        00:00:00 systemd
   2109 ?        00:00:00   (sd-pam)
   2121 ?        00:00:00   pipewire
   2122 ?        00:00:00   pipewire
   2125 ?        00:00:00   wireplumber
   2132 ?        00:00:00   pipewire-pulse
   2133 ?        00:00:00   gnome-keyring-d
   2140 ?        00:00:00   dbus-daemon
   2170 ?        00:00:00   xdg-document-po
   2178 ?        00:00:00   xdg-permission-
   2307 ?        00:00:00   gcr-ssh-agent

```

#### Display all processes in a tree format with ASCII art:
```bash
# Syntax
$ ps -e --forest

# Example
sri@envy:~
$ ps -u sri --forest
    PID TTY          TIME CMD
   2209 tty2     00:00:00 gdm-wayland-ses
   2217 tty2     00:00:00  \_ gnome-session-b
   2105 ?        00:00:00 systemd
   2109 ?        00:00:00  \_ (sd-pam)
   2121 ?        00:00:00  \_ pipewire
   2122 ?        00:00:00  \_ pipewire
   2125 ?        00:00:00  \_ wireplumber
   2132 ?        00:00:00  \_ pipewire-pulse
   2133 ?        00:00:00  \_ gnome-keyring-d
   2140 ?        00:00:00  \_ dbus-daemon
   2170 ?        00:00:00  \_ xdg-document-po
   2178 ?        00:00:00  \_ xdg-permission-
   2307 ?        00:00:00  \_ gcr-ssh-agent
   2308 ?        00:00:00  \_ gnome-session-c
   2327 ?        00:00:00  \_ gvfsd
   3098 ?        00:00:00  |   \_ gvfsd-trash
   3243 ?        00:00:00  |   \_ gvfsd-recent
   3291 ?        00:00:00  |   \_ gvfsd-http
   2335 ?        00:00:00  \_ gvfsd-fuse

```

## `pstree` Command

The `pstree` command is another tool that displays running processes in a tree-like format. It is **similar to the `ps -H` or `ps --forest`** command options but with a **more visually structured output**. Unlike `ps`, `pstree` **provides a continuous, updated process tree.**

To use `pstree`:
```bash
# Syntax
$ pstree

# Example
sri@envy:~
$ pstree -u sri
gdm-wayland-ses─┬─gnome-session-b───3*[{gnome-session-b}]
                └─3*[{gdm-wayland-ses}]

systemd─┬─(sd-pam)
        ├─at-spi2-registr───3*[{at-spi2-registr}]
        ├─chrome_crashpad───2*[{chrome_crashpad}]
        ├─code─┬─code
        │      ├─code───code───14*[{code}]
        │      ├─code───8*[{code}]
        │      ├─code───14*[{code}]
        │      ├─code─┬─code───7*[{code}]
        │      │      └─15*[{code}]
        │      ├─code───15*[{code}]
        │      ├─code───17*[{code}]
        │      └─34*[{code}]
        ├─dbus-daemon
        ├─dconf-service───3*[{dconf-service}]
        ├─evince───6*[{evince}]
        ├─evinced───3*[{evinced}]
        ├─evolution-addre───6*[{evolution-addre}]
        ├─evolution-calen───9*[{evolution-calen}]
        ├─evolution-sourc───4*[{evolution-sourc}]
        ├─firefox─┬─Isolated Web Co───23*[{Isolated Web Co}]
        │         ├─Socket Process───5*[{Socket Process}]
        │         ├─Utility Process───4*[{Utility Process}]

```

## Real-Time Process Monitoring with `top` and `htop`

While `ps` gives a snapshot of processes at a specific moment, `top` and `htop` display processes in real-time, refreshing periodically.

---

### The `top` Command

`top` is a command-line utility that provides an overview of the system's performance and real-time process monitoring.

#### Basic usage of `top`:
```bash
# Syntax
$ top

# Example
sri@envy:~
$ top
top - 17:03:03 up 18 min,  1 user,  load average: 0.69, 0.67, 0.45
Tasks: 279 total,   1 running, 278 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.5 us,  0.4 sy,  0.0 ni, 99.0 id,  0.0 wa,  0.0 hi,  0.1 si,  0.0 st 
MiB Mem :   7318.3 total,   3221.4 free,   2439.8 used,   1986.5 buff/cache     
MiB Swap:   4096.0 total,   4096.0 free,      0.0 used.   4878.6 avail Mem 

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND                
   2383 sri       20   0 5538112 336256 153032 S   2.7   4.5   0:32.88 gnome-shell            
   4684 sri       20   0  565244  55492  44632 S   1.0   0.7   0:04.22 gnome-terminal-        
    209 root     -51   0       0      0      0 S   0.7   0.0   0:03.31 irq/48-SYNA32A0:00     
    565 root     -51   0       0      0      0 S   0.7   0.0   0:08.29 irq/82-rtw88_pci       
     17 root      20   0       0      0      0 I   0.3   0.0   0:00.81 rcu_preempt            
     51 root      20   0       0      0      0 I   0.3   0.0   0:00.32 kworker/u33:0-events_+ 
   3472 sri       20   0 2614988 190872 100916 S   0.3   2.5   0:05.24 Isolated Web Co     
```

While `top` is running, you can press the following keys to interact with the process list:
- `P`: Sort processes by CPU usage.
- `M`: Sort processes by memory usage.
- `k`: Kill a process by specifying its PID.
- `q`: Quit `top`.

---

### The `htop` Command - too good!

`htop` is an improved, interactive version of `top` with a more user-friendly interface and additional features like color coding. However, it is not installed by default on all distributions, so you may need to install it first.

#### Install `htop`:
```bash
$ sudo apt install htop -y # For Ubuntu/Debian-based systems
```

#### Run `htop`:
```bash
# Sytnax
$ htop

# Example
sri@envy:~
$ htop

```
---

### Example Workflow for Process Management

1. **List all processes**:
   ```bash
   $ ps -e
   ```

2. **Get a detailed view of a specific process (e.g., PID 1234)**:
   ```bash
   $ ps -p 1234 -f
   ```

3. **Monitor processes in real-time**:
   ```bash
   $ htop
   ```

4. **Kill a process** (for example, PID 5678):
   ```bash
   $ kill 5678
   ```

---

## Jobs 

### What is a Job?  

In Linux, a **job** is a task or command initiated in the shell. By default, jobs run in the **foreground**, occupying the terminal session and **blocking further input until they complete**. However, you can also run jobs in the **background**, allowing you to continue using the terminal for other tasks. 

For instance, running a command like `sleep 10 &` starts the process in the background and assigns it a **job ID**, making it easier to manage.  

To handle tasks more efficiently, Linux offers **job control mechanisms**, enabling you to:  

- Run processes in the background.  
- Pause (suspend) and resume tasks.  
- Check the status of running jobs.  
- Bring background tasks to the foreground.  
- Terminate unwanted processes.  

---

### Key Differences Between a Job and a Process  

In Linux, a **job** is a shell-level abstraction for managing tasks initiated in the terminal, while a **process** is a broader system-level concept representing any program running on the system. **Jobs are specific to the shell** and are identified by job IDs, whereas **processes are independent of the shell** and are identified by PIDs.

While each job corresponds to one or more processes, not all processes are jobs. For example, system processes like `systemd` or `cron` are started by the operating system and are not initiated by the shell, so they aren't considered jobs.  


| **Aspect**| **Job**| **Process**|  
|------------------------|----------------------------------------|----------------------------------------|  
| **Scope** | Managed by the shell.  | Managed by the Linux kernel.   |  
| **Identifier** | Identified by a **job ID** (e.g., `[1]`). | Identified by a **process ID (PID)**. |  
| **Creation**  | Created when a command is run in the shell. | Created by the operating system for any executed program. |  
| **Context**   | Tied to the shell session. | Independent of the shell (can exist outside of a shell). |  
| **Examples**  | Background commands (`sleep 10 &`).| System processes (`cron`, `systemd`).  |  

---

### Running Jobs in the Background

When you start a command in the background, **the terminal immediately returns the prompt**, allowing you to continue executing other commands. To start a command in the background, you **append an ampersand (`&`)** to the command:

```bash
# Syntax
$ command &

# Example
sri@envy:~
$ sleep 30 &
[1] 5329
sri@envy:~
$ 

```
The `sleep` command makes the shell idle for given period of time. In the above example, the `sleep 30` command will run in the background for 30 seconds while you are free to use the terminal for other tasks.

When a command runs in the background, two pieces of information are displayed: the **job number** and the **process ID (PID)**. The job number is enclosed in square brackets, and the PID is shown next to it. In the example, `1` is the job number, and `25837` is the process ID of the background job.

#### When Does the Output of a Background Job Appear?

The shell ensures that background job output doesn't interrupt your work at the command prompt. **It only displays the output when a new prompt appears**, keeping the session organized. The `jobs` command will show job statuses just before the prompt is displayed. 

To check job status, press the **Enter** key. If any jobs are completed, their statuses will be shown before the new prompt.

### Job Control Table

| **Description**   | **Command**  |
|---------------------------------------------------|----------------------|
| Start command in the background   | `command &`  |
| Kill the foreground process   | `Ctrl-C` |
| Suspend(pause) the foreground process | `Ctrl-Z` |
| Background most recent suspended process  | `bg` |
| Background a suspended process| `bg [%num]`  |
| Foreground most recent backgrounded process   | `fg` |
| Foreground a backgrounded process | `fg [%num]`  |
| Kill a process by job number or PID   | `kill [%num]` or `kill <PID>` |
| List all jobs or a specific job by job number | `jobs [%num]`|
| List all the jobs with process id | `jobs -l`|

### Job Status

The `jobs` command lists all the jobs running in the background or suspended. The job numbers are displayed in square brackets. Jobs that are running or stopped are listed with their status.

Example output:
```bash
# Syntax
$ jobs
$ jobs -l # long list format

# Example
sri@envy:~
$ jobs
[1]+  12345 Running                 sleep 30 &
[2]-  12345 Stopped                 sleep 10 &

$ sleep 60 &
[1] 28633
$ jobs
[1]+  Running                 sleep 60 &
$ jobs -l
[1]+ 28633 Running                 sleep 60 &
$ 
```
- The job number `[1]` is running (`Running`).
- The job number `[2]` is stopped (`Stopped`).
- **`+`**: Indicates the current job.
- **`-`**: Indicates the previous job.


### Managing Jobs with `fg` and `bg`

You can control jobs that are running in the background or that have been suspended by bringing them to the foreground or resuming them in the background.

#### Foregrounding a Job

To bring a background job to the foreground, use the `fg` command followed by the job number, you can also specify `%%` or `%+`. 

```bash
# Syntax
$ fg %<job_number>
# bring the most recent bg job to fg
$ fg %%
$ fg %+
$ fg
# bring the previous bg job to fg
$ fg %-

# Examples
sri@envy:~
$ sleep 30 &
[1] 26056
sri@envy:~
$ fg %1
sleep 30

# bring the most recent bg job to fg

sri@envy:~
$ sleep 30 &
[1] 26056
sri@envy:~
$ fg %%
sleep 30

sri@envy:~
$ sleep 30 &
[1] 26056
sri@envy:~
$ fg %+
sleep 30

sri@envy:~
$ sleep 30 &
[1] 26056
sri@envy:~
$ fg
sleep 30

```

#### Backgrounding a Suspended Job

If a job is suspended (e.g., using `Ctrl-Z`), you can **resume** it in the background by using the `bg` command followed by the job number.

```bash
# Syntax
$ bg %1

# Example
sri@envy:~
$ sleep 10
^Z
[1]+  Stopped                 sleep 10
sri@envy:~
$ bg %1
[1]+ sleep 10 &
sri@envy:~
$ # after 10 seconds press <Enter> again
[1]+  Done                    sleep 10
sri@envy:~
$ 
```

If you want to resume the most recently suspended job in the background, simply use `bg` without specifying the job number:

```bash
# Syntax
$ bg

# Example
sri@envy:~
$ sleep 10
^Z
[1]+  Stopped                 sleep 10
sri@envy:~
$ bg
[1]+ sleep 10 &
sri@envy:~
$ # after 10seconds pressing <Enter>
[1]+  Done                    sleep 10
sri@envy:~
$ 
```

### Killing Jobs

To terminate a job, you can use the `kill` command. This command sends a signal to a process, and by default, the signal is `SIGTERM` (termination).

#### Killing Foreground Jobs

To kill a foreground job, you can simply press `Ctrl-C`. This sends the `SIGINT` signal (interrupt), which immediately stops the process.

#### Killing Background Jobs by Job Number or PID

To kill a background job, use the `kill` command followed by the job number or process ID (PID). 

To kill a job by job **number**:
```bash
# Syntax
$ kill %<job_number>

# Example
$ sleep 100000 &
[1] 26558
$ kill %1
$
```

To kill a job by its **PID**:
```bash
# Syntax
$ kill <process_id>

# Example
sri@envy:~
$ sleep 100000
^Z
[1]+  Stopped                 sleep 100000
sri@envy:~
$ bg
[1]+ sleep 100000 &
sri@envy:~
$ kill -15 %1 # -15                               is optional, it is SIGTERM
sri@envy:~
$ jobs
[1]+  Terminated              sleep 100000
sri@envy:~
$ 
```

You can also use `kill -l` to list all the available signals that can be sent to a process.
```bash
$ kill -l
 1) SIGHUP	 2) SIGINT	 3) SIGQUIT	 4) SIGILL	 5) SIGTRAP
 6) SIGABRT	 7) SIGBUS	 8) SIGFPE	 9) SIGKILL	10) SIGUSR1
11) SIGSEGV	12) SIGUSR2	13) SIGPIPE	14) SIGALRM	15) SIGTERM
16) SIGSTKFLT	17) SIGCHLD	18) SIGCONT	19) SIGSTOP	20) SIGTSTP
21) SIGTTIN	22) SIGTTOU	23) SIGURG	24) SIGXCPU	25) SIGXFSZ
26) SIGVTALRM	27) SIGPROF	28) SIGWINCH	29) SIGIO	30) SIGPWR
31) SIGSYS	34) SIGRTMIN	35) SIGRTMIN+1	36) SIGRTMIN+2	37) SIGRTMIN+3
38) SIGRTMIN+4	39) SIGRTMIN+5	40) SIGRTMIN+6	41) SIGRTMIN+7	42) SIGRTMIN+8
43) SIGRTMIN+9	44) SIGRTMIN+10	45) SIGRTMIN+11	46) SIGRTMIN+12	47) SIGRTMIN+13
48) SIGRTMIN+14	49) SIGRTMIN+15	50) SIGRTMAX-14	51) SIGRTMAX-13	52) SIGRTMAX-12
53) SIGRTMAX-11	54) SIGRTMAX-10	55) SIGRTMAX-9	56) SIGRTMAX-8	57) SIGRTMAX-7
58) SIGRTMAX-6	59) SIGRTMAX-5	60) SIGRTMAX-4	61) SIGRTMAX-3	62) SIGRTMAX-2
63) SIGRTMAX-1	64) SIGRTMAX	
```

#### Sending Specific Signals

The `kill` command can send different types of signals. By default, `kill` sends `SIGTERM` (signal 15) to gracefully terminate the process. If the process does not terminate after receiving `SIGTERM`, you can forcefully terminate it by sending `SIGKILL` (signal 9).

To send `SIGTERM` (default):
```bash
# Syntax
$ kill %1
```

To send `SIGKILL` to forcefully kill a job:
```bash
# Syntax
$ kill -9 %1
```

## Summary of Processes and Jobs Control Commands

| **Command** | **Description** | **Example** |
|-------------|-----------------|-------------|
| `ps` | Lists running processes on the system.  | `ps`  |
| `ps -e`  | Displays all processes running on the system.   | `ps -e`   |
| `ps -ef` | Displays all processes with a full format listing.  | `ps -ef`  |
| `ps -eH` | Displays processes in a hierarchical (tree) format. | `ps -eH`  |
| `ps -e --forest` | Displays processes in a tree format using ASCII art.| `ps -e --forest`  |
| `ps -u <username>`   | Displays processes running for a specific user. | `ps -u john`  |
| `ps -p <PID>`| Displays information for a specific process ID (PID).   | `ps -p 1234`  |
| `pstree` | Displays processes in a hierarchical tree format.   | `pstree`  |
| `top`| Displays a real-time process list with system performance information.  | `top` |
| `htop`   | Interactive and improved version of `top` with a user-friendly interface.   | `htop`|
| `sudo apt install htop`  | Installs `htop` on a Debian-based system.   | `sudo apt install htop`   |
| `kill <PID>` | Terminates a running process using its process ID (PID).| `kill 5678`   |
| `command &`  | Starts a command in the background. | `sleep 60 &`  |
| `Ctrl-C` | Kills the foreground process.  | (Press `Ctrl-C` while the job is in the foreground)   |
| `Ctrl-Z` | Suspends the foreground process.   | (Press `Ctrl-Z` while the job is running) |
| `bg [%num]`  | Resumes a suspended job in the background.  | `bg %1`   |
| `bg` | Resumes the most recently suspended job in the background.  | `bg`  |
| `fg [%num]`  | Brings a backgrounded job to the foreground.| `fg %1`   |
| `fg` | Brings the most recent background job to the foreground.| `fg`  |
| `kill [%num]` or `kill <PID>`| Kills a job by job number or PID.   | `kill %1` or `kill 12345` |
| `jobs` or `jobs [%num]`  | Lists all jobs or a specific job by job number.| `jobs` or `jobs %1`|
| `kill -l`| Lists available signals.| `kill -l`|
| `kill -<signal> %num` or `kill -<signal> <PID>` | Sends a specific signal to a job. | `kill -9 %1` or `kill -9 12345`|
| `kill -9`| Force kills a job using the SIGKILL signal.| `kill -9 %1`|
| `kill -15`| Kills a job using the SIGTERM signal.| `kill -15 %1`|

---

# Switching Users

In Linux, switching between users or performing administrative tasks requires specific commands: `su` (Switch User) and `sudo` (Super User Do).

## Switching Users with `su` (Switch User)

The `su` command is used to switch between users in a Linux system. By default, `su` switches to the superuser (root). You can also use `su` to switch to any specific user by providing their username as an argument.

### Common `su` Usage

#### Switch to Root:  
The `su` command without any arguments switches to the root user.
```bash
# Syntax
$ su

# Example
sri@envy:~/Documents/Linux
$ su
```
The above command may give error: 

```bash
sri@envy:~/Documents/Linux
$ su
Password: 
su: Authentication failure
```
On many modern Linux distributions, the root account is disabled by default for security reasons. In this case, you might need to use sudo to gain root privileges instead of su. Ensure to enter the current user's password and not the superuser.

```bash
# Syntax
$ sudo su

# Example
sri@envy:~/Documents/Linux
$ sudo su
root@envy:/home/sri/Documents/Linux# 
```

#### Switch to a Specific User:  
To switch to a specific user, use the command `su [username]`. Enter the **switching user**'s password and not current user's password. 

In the below example you will have to enter switching user, `ram`'s passowrd. 
```bash
# Syntax
$ sudo username

# Example
sri@envy:~/Documents/Linux
$ su ram
Password: 
ram@envy:/home/sri/Documents/Linux$ 
```
Also notice that you are still the same directory as before. 

**To quit** from this user (`ram`) account: 
```bash
# Syntax
$ exit

# Example
ram@envy:/home/sri/Documents/Linux$ exit
exit
sri@envy:~/Documents/Linux
$ 

# logout doesn't work
sri@envy:~/Documents/Linux
$ sudo su
[sudo] password for sri: 
root@envy:/home/sri/Documents/Linux# logout
bash: logout: not login shell: use `exit'
root@envy:/home/sri/Documents/Linux# exit
exit
sri@envy:~/Documents/Linux
$ 

```
  
Another way of logging to another user is through `sudo su [username]`, use the **current user**'s password. If the current user is in sudoers group, they will be able to login to another user's account.

In the below example you will have to enter current user, `sri`'s password. 
```bash
# Syntax
$ sudo su username

# Example
sri@envy:~/Documents/Linux
$ sudo su ram
[sudo] password for sri: 
ram@envy:/home/sri/Documents/Linux$ 
```

#### Simulate Logging In as a User:  
By adding a hyphen (`-`), you simulate logging in directly as that user. This changes your environment variables and your working directory to the user's home directory. **While the previous method don't change the working directory.** 
```bash
# Syntax
$ su - username
$ sudo su - username

# Example
sri@envy:~/Documents/Linux
$ sudo su - ram
[sudo] password for sri: 
ram@envy:~$ 
```

#### Excuting command as another user: 
By using `-c` option with `su` we can execute command as another user. 
```bash
# Syntax
$ su -c command
$ sudo su -c command
$ sudo -u command

# Example
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
# haven't switched to ram, still in sri
sri@envy:~/Documents/Linux
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
# Syntax
$ whoami

# Example
sri@envy:~/Documents/Linux
$ whoami
# Output: sri
```
After switching to another user with `su`, `whoami` will show the new user:
```bash
sri@envy:~/Documents/Linux
$ su ram
Password:
ram@envy:/home/sri/Documents/Linux$ whoami
# Output: ram
```

---

## `sudo` (Super User Do)

The `sudo` command allows a **permitted user** to execute a command as another user, typically the root user, without switching users entirely. It's often used for administrative tasks, such as installing software or managing system services, that require superuser privileges.

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
| `sudo -u user command`| Run a command as a specific user (other than root) similar to `sudo su user -c "command"` | `sudo -u ram whoami`|
| `sudo su`| Switch to the superuser account (root)| `sudo su`|
| `sudo su -`| Switch to the **superuser account (root)** with the user's environment| `sudo su -`|
| `sudo su - username`| Switch to a **specific user's account** with that user's environment| `sudo su - ram`|

---

### Example of Using `sudo`

1. **Run a Command as Root**:
   ```bash
   sudo /etc/init.d/apache2 start
   # Output: Starting web server apache2
   ```

2. **Run a Command as Another User**:
   ```bash
   sudo -u ram /opt/ramsApp/bin/start
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

| Feature | `su`| `sudo` |
|---------------------|------------------------------------------------------|----------------------------------------------------|
| **Password Prompt**  | Requires the target user's password (e.g., root).| Requires the current user's password.  |
| **Command Scope**| Changes the current shell to the target user's shell. | Runs a single command as the specified user.   |
| **Security**sudo su ram | Requires sharing of passwords for different users.   | Provides better control and logging of commands.   |
| **Usage**| Best for switching users to run multiple commands.   | Best for executing one-off commands with elevated privileges. |

`sudo` is generally preferred over `su` for security reasons, as it reduces the risk of exposing root passwords and provides better auditing and control over user actions.

## Summary of Switching User Commands

| Command | Description | Example Usage |
|---------|-------------|---------------|
| `su`| Switch to the root user account. Prompts for the root password. | `su`   |
| `su [user]` | Switch to the specified user account. Prompts for the user's password.  | `su john`  |
| `su -`  | Switch to the root user and simulate a fresh login shell.   | `su -` |
| `su - [user]`   | Switch to the specified user and simulate a fresh login shell.  | `su - alice`   |
| `su -c [command]`   | Execute a single command as the root user.  | `su -c "ls /root"` |
| `sudo command`  | Execute a command as the root user. Prompts for the user's password.| `sudo apt update`  |
| `sudo -l`   | List the commands the user is allowed to execute with `sudo`.   | `sudo -l`  |
| `sudo su`   | Switch to the root user using `sudo`.   | `sudo su`  |
| `sudo su -` | Switch to the root user and simulate a fresh login shell using `sudo`.  | `sudo su -`|
| `sudo su [user]`| Switch to another user using `sudo`.| `sudo su alice`|
| `sudo su - [user]`  | Switch to another user and simulate a fresh login shell using `sudo`.   | `sudo su - alice`  |
| `sudo su user -c [command]` | Execute a command as another user using `sudo`.  | `sudo su alice -c "ls ~"`  |
| `sudo -u user [command]` | Execute a command as the specified user using `sudo`.| `sudo -u alice ls /home/alice` |
| `whoami`| Display the current user's username.| `whoami`   |
| `exit`| Exit the current shell or logout of the current user session.| `exit`|

---

# Installing Software

Software installation on Linux is commonly done through packages, which contain both the software files and additional metadata (such as installation scripts, version info, dependencies, and more). A package manager handles the installation, upgrading, and removal of software and maintains a database of installed packages and their dependencies.

## DEB-Based Distributions

Linux distributions based on Debian use the DEB package format. Popular Debian-based distributions include **Debian**, **Ubuntu**, **Linux Mint**, and **Elementary OS**. The package manager used is **APT** (Advanced Packaging Tool). 

### Common APT Commands

Here's the table converted to use only `sudo apt` commands:

| Command  | Description | Example  |
|------------------------------|-------------------------------------------------------------------------------------|----------------------------------|
| `sudo apt update` | Update package list and metadata from repositories| `sudo apt update`|
| `sudo apt upgrade`| Upgrade all installed packages to the latest available versions   | `sudo apt upgrade`   |
| `sudo apt autoremove` | Remove unnecessary packages that were installed as dependencies but are no longer needed | `sudo apt autoremove` |
| `sudo apt clean`  | Clear the local repository cache to free up space | `sudo apt clean` |
| `sudo apt search search-pattern` | Search for packages matching the search pattern   | `sudo apt search web browser`|
| `sudo apt install package`| Install a package| `sudo apt install firefox`   |
| `sudo apt install -y package` | Install a package and automatically answer "yes" to prompts   | `sudo apt install -y firefox`|
| `sudo apt remove package` | Remove a package, leaving behind configuration files  | `sudo apt remove firefox`|
| `sudo apt purge package`  | Remove a package, including its configuration files   | `sudo apt purge firefox` |
| `sudo apt show package`   | Display detailed information about a package  | `sudo apt show firefox`  |
| `sudo apt full-upgrade`   | Perform an upgrade with more aggressive handling of dependencies   | `sudo apt full-upgrade`  |

### Example Workflow: Installing and Managing GIMP (GNU Image Manipulation Program)

**Update package list**:  
Before installing or managing any package, ensure the package list is up to date:
```bash
sri@envy:~/Documents/Linux
$ sudo apt update
[sudo] password for sri: 
Get:1 http://security.ubuntu.com/ubuntu noble-security InRelease [126 kB]
Hit:2 http://in.archive.ubuntu.com/ubuntu noble InRelease
Get:3 http://in.archive.ubuntu.com/ubuntu noble-updates InRelease [126 kB]
Get:4 http://in.archive.ubuntu.com/ubuntu noble-backports InRelease [126 kB]
...
Get:20 http://in.archive.ubuntu.com/ubuntu noble-backports/multiverse amd64 Components [212 B]
Fetched 2,533 kB in 3s (902 kB/s)                                         
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
All packages are up to date.
sri@envy:~/Documents/Linux
$ 

sri@envy:~/Documents/Linux
$ sudo apt upgrade -y
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Calculating upgrade... Done
Get more security updates through Ubuntu Pro with 'esm-apps' enabled:
  libcjson1 libpostproc57 libavcodec60 libavutil58 libswscale7 libswresample4
  libavformat60 libavfilter9
Learn more about Ubuntu Pro at https://ubuntu.com/pro
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
sri@envy:~/Documents/Linux
$ 

```

**Search for a package**:  
To search for packages related to "image editor":
```bash
sri@envy:~/Documents/Linux
$ sudo apt search image editor
Sorting... Done
Full Text Search... Done
android-platform-tools-base/noble 2.2.2-4ubuntu1 all
  base tools for developing applications for the Android system

briquolo-data/noble 0.5.7-11build2 all
  data files for the fast paced 3d Breakout game Briquolo

charactermanaj/noble 0.998+git20190331.e45260e3-3 all
  avatar editor application

chntpw/noble 140201-1 amd64
  NT SAM password recovery utility

...

zim/noble 0.75.2-1 all
  graphical text editor based on wiki technologies

sri@envy:~/Documents/Linux
$
```

**Display package details**:  
To view detailed information about the GIMP package:
```bash
sri@envy:~/Documents/Linux
$ sudo apt show gimp
Package: gimp
Version: 2.10.36-3ubuntu0.24.04.1
Priority: optional
Section: universe/graphics
Origin: Ubuntu
Maintainer: Ubuntu Developers <ubuntu-devel-discuss@lists.ubuntu.com>
...
sri@envy:~/Documents/Linux
$ 
```

**Install a package**:  
To install GIMP:
```bash
sri@envy:~/Documents/Linux
$ sudo apt install gimp -y 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  fonts-liberation2 gimp-data graphviz libamd3 libann0 libbabl-0.1-0 libcamd3 libccolamd3
  libcdt5 libcgraph6 libcholmod5 libcolamd3 libgegl-0.4-0t64 libgegl-common libgimp2.0t64
  libgts-0.7-5t64 libgts-bin libgvc6 libgvpr2 libimath-3-1-29t64 liblab-gamut1 libmng2
  libmypaint-1.5-1 libmypaint-common libopenexr-3-1-30 libpathplan4 libraw23t64
  libsuitesparseconfig7 libumfpack6
...
Processing triggers for libc-bin (2.39-0ubuntu8.3) ...
Processing triggers for man-db (2.12.0-4build2) ...
Processing triggers for desktop-file-utils (0.27-2build1) ...
sri@envy:~/Documents/Linux
$ 
```

**Upgrade installed packages**:  
To upgrade all installed packages to their latest versions:
```bash
sri@envy:~/Documents/Linux
$ sudo apt upgrade
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Calculating upgrade... Done
Get more security updates through Ubuntu Pro with 'esm-apps' enabled:
  libcjson1 libpostproc57 libavcodec60 libavutil58 libswscale7 libswresample4
  libavformat60 libavfilter9
Learn more about Ubuntu Pro at https://ubuntu.com/pro
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
sri@envy:~/Documents/Linux
$ 
```

**Full upgrade (handle dependencies)**:  
To perform an upgrade with more aggressive dependency handling:
```bash
sri@envy:~/Documents/Linux
$ sudo apt full-upgrade
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Calculating upgrade... Done
Get more security updates through Ubuntu Pro with 'esm-apps' enabled:
  libcjson1 libpostproc57 libavcodec60 libavutil58 libswscale7 libswresample4
  libavformat60 libavfilter9
Learn more about Ubuntu Pro at https://ubuntu.com/pro
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
sri@envy:~/Documents/Linux
$ 
```

**Remove a package**:  
To remove GIMP while keeping its configuration files:
```bash
sri@envy:~/Documents/Linux
$ sudo apt remove gimp -y
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  fonts-liberation2 gimp-data graphviz libamd3 libann0 libbabl-0.1-0 libcamd3 libccolamd3
  libcdt5 libcgraph6 libcholmod5 libcolamd3 libgegl-0.4-0t64 libgegl-common libgimp2.0t64
  libgts-0.7-5t64 libgts-bin libgvc6 libgvpr2 libimath-3-1-29t64 liblab-gamut1 libmng2
  libmypaint-1.5-1 libmypaint-common libopenexr-3-1-30 libpathplan4 libraw23t64
  libsuitesparseconfig7 libumfpack6
Use 'sudo apt autoremove' to remove them.
The following packages will be REMOVED:
  gimp
0 upgraded, 0 newly installed, 1 to remove and 0 not upgraded.
After this operation, 20.0 MB disk space will be freed.
(Reading database ... 162947 files and directories currently installed.)
Removing gimp (2.10.36-3ubuntu0.24.04.1) ...
Processing triggers for gnome-menus (3.36.0-1.1ubuntu3) ...
Processing triggers for man-db (2.12.0-4build2) ...
Processing triggers for desktop-file-utils (0.27-2build1) ...
sri@envy:~/Documents/Linux
$ 
```

**Purge a package**:  
To completely remove GIMP along with its configuration files:
```bash
sri@envy:~/Documents/Linux
$ sudo apt purge gimp
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Package 'gimp' is not installed, so not removed
The following packages were automatically installed and are no longer required:
  fonts-liberation2 gimp-data graphviz libamd3 libann0 libbabl-0.1-0 libcamd3 libccolamd3
  libcdt5 libcgraph6 libcholmod5 libcolamd3 libgegl-0.4-0t64 libgegl-common libgimp2.0t64
  libgts-0.7-5t64 libgts-bin libgvc6 libgvpr2 libimath-3-1-29t64 liblab-gamut1 libmng2
  libmypaint-1.5-1 libmypaint-common libopenexr-3-1-30 libpathplan4 libraw23t64
  libsuitesparseconfig7 libumfpack6
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
sri@envy:~/Documents/Linux
$ 
```

**Clean up unnecessary packages**:  
To remove packages that are no longer needed as dependencies:
```bash
sri@envy:~/Documents/Linux
$ sudo apt autoremove -y
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages will be REMOVED:
  fonts-liberation2 gimp-data graphviz libamd3 libann0 libbabl-0.1-0 libcamd3 libccolamd3
  libcdt5 libcgraph6 libcholmod5 libcolamd3 libgegl-0.4-0t64 libgegl-common libgimp2.0t64
  libgts-0.7-5t64 libgts-bin libgvc6 libgvpr2 libimath-3-1-29t64 liblab-gamut1 libmng2
  libmypaint-1.5-1 libmypaint-common libopenexr-3-1-30 libpathplan4 libraw23t64
  libsuitesparseconfig7 libumfpack6
0 upgraded, 0 newly installed, 29 to remove and 0 not upgraded.
After this operation, 129 MB disk space will be freed.
(Reading database ... 162663 files and directories currently installed.)
Removing fonts-liberation2 (1:2.1.5-3) ...
Removing gimp-data (2.10.36-3ubuntu0.24.04.1) ...
Processing triggers for libc-bin (2.39-0ubuntu8.3) ...
Processing triggers for man-db (2.12.0-4build2) ...
Processing triggers for hicolor-icon-theme (0.17-2) ...
sri@envy:~/Documents/Linux
$ 
```

**Clear the package cache**:  
To free up disk space by clearing the local repository cache:
```bash
sri@envy:~/Documents/Linux
$ sudo apt clean
sri@envy:~/Documents/Linux
$ 

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

| **Feature** | **`apt`** | **`apt-get`**|
|---------------------------|---------------------------------------|--------------------------------------|
| **User Focus**| Designed for end-users with a simpler and cleaner interface. | Designed for scripts and advanced users. |
| **Default Output**| Provides a more user-friendly and colored output. | Outputs detailed but less formatted information. |
| **Commands**  | Combines commands like `install`, `remove`, `update`, `upgrade`, etc. | Requires separate commands for some actions, like `apt-get` and `apt-cache`. |
| **Introduced In** | Ubuntu 16.04+ / Debian 8+ | Older tool, part of APT package manager since inception. |
| **Use Case**  | Recommended for interactive use.   | Recommended for scripting and backward compatibility. |

#### **Key Commands Comparison**

| Task | `apt` Command  | `apt-get` Command |
|--------------------------|------------------------|-----------------------|
| Install a package| `sudo apt install` | `sudo apt-get install` |
| Remove a package | `sudo apt remove`  | `sudo apt-get remove` |
| Update package list  | `sudo apt update`  | `sudo apt-get update` |
| Upgrade installed packages | `sudo apt upgrade`   | `sudo apt-get upgrade` |
| Full system upgrade  | `sudo apt full-upgrade` | `sudo apt-get dist-upgrade` |

**Summary**: Use `apt` for day-to-day tasks and `apt-get` for scripting or advanced operations.

---

### Managing DEB Packages Directly with `dpkg`

While `apt` is the most common tool for package management, you can interact directly with the **DEB package manager** using `dpkg`.  

| Command | Description |
|-----------------------------|-----------------------------------------------------------------|
| `dpkg -l`  | List all installed packages.|
| `dpkg -S /path/to/file`| Find the package that provides a specific file. |
| `sudo dpkg -i package.deb` | Install a package from a `.deb` file.  |
| `dpkg -L <package>` | List all files installed by a package. |

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

| **Feature**   | **`apt`** | **`dpkg`** |
|---------------------------|-------------------------------------------|---------------------------------------|
| **Purpose**   | High-level package manager for managing packages (installing, upgrading, searching, etc.) with dependency resolution. | Low-level package manager for installing, removing, and inspecting `.deb` packages without resolving dependencies. |
| **Dependency Handling**   | Automatically handles dependencies during package installation and removal. | Does not manage dependencies; errors occur if dependencies are missing. |
| **Interface** | User-friendly commands like `install`, `update`, `upgrade`, etc. | Requires direct interaction with `.deb` files using precise commands. |
| **Use Case**  | Used for managing packages from repositories and performing system-wide package management. | Used for manual installation or troubleshooting specific `.deb` files. |
| **Example Commands**  | `sudo apt install firefox`| `sudo dpkg -i firefox.deb`   |

**Summary**: Use `apt` for general package management and `dpkg` for direct `.deb` file manipulation or troubleshooting.

## Summary of Installing Software Commands

| **Command** | **Description** | **Example**  |
|-------------|-----------------|--------------|
| `sudo apt update`| Update package list and metadata from repositories | `sudo apt update`   |
| `sudo apt upgrade`   | Upgrade all installed packages to the latest available versions| `sudo apt upgrade`  |
| `sudo apt autoremove`| Remove unnecessary packages that were installed as dependencies but are no longer needed | `sudo apt autoremove`|
| `sudo apt clean` | Clear the local repository cache to free up space  | `sudo apt clean`|
| `sudo apt search search-pattern` | Search for packages matching the search pattern| `sudo apt search web browser`   |
| `sudo apt install package`   | Install a package  | `sudo apt install firefox`  |
| `sudo apt install -y package`| Install a package and automatically answer "yes" to prompts| `sudo apt install -y firefox`   |
| `sudo apt remove package`| Remove a package, leaving behind configuration files   | `sudo apt remove firefox`   |
| `sudo apt purge package` | Remove a package, including its configuration files| `sudo apt purge firefox`|
| `sudo apt show package`  | Display detailed information about a package   | `sudo apt show firefox` |
| `sudo apt full-upgrade`  | Perform an upgrade with more aggressive handling of dependencies| `sudo apt full-upgrade` |
| `-y` |  'yes' to all the upcoming download requests | `sudo apt install gimp -y` | 
| `dpkg -l`| List all installed packages.   | `dpkg -l`   |
| `dpkg -S /path/to/file`  | Find the package that provides a specific file.| `dpkg -S /path/to/file` |
| `sudo dpkg -i package.deb`   | Install a package from a `.deb` file.  | `sudo dpkg -i package.deb`  |
| `dpkg -L <package>`  | List all files installed by a package. | `dpkg -L <package>` |
| **Example Workflow with `dpkg`** | **Description**| **Command**  |
| Install a `.deb` package | Install a `.deb` file. | `sudo dpkg -i package.deb`  |
| Fix broken dependencies  | Fix unmet dependencies after installing a `.deb` package.  | `sudo apt install -f`   |
| List installed files for a package | View which files a package has installed.  | `dpkg -L <package>` |
| Find a package by file   | Identify which package installed a specific file.  | `dpkg -S /path/to/file` |

---

# Cheat Sheet

| Commands  | Description   |
|-----------------------------------|-------------------------------------------------------------------|
| **Basic Commands** | --- |
| `ls [dir]`| Lists the contents of a directory.|
| `whereis -b [command]`| Searches for the binary (executable) file of a command.   |
| `whereis -m [command]`| Searches for the manual page of a command.|
| `whereis -s [command]`| Searches for the source code of a command.|
| `whereis -u [command]`| Finds unlinked files (files not listed in the system's database). |
| `whereis -B <path> [command]` | Specifies a directory to search for binaries. |
| `whereis -M <path> [command]` | Specifies a directory to search for manual pages. |
| `whereis -S <path> [command]` | Specifies a directory to search for source files. | 
| `pwd`  | Displays the present working directory. |
| `cd [directory]`   | Changes the current directory to the specified directory. |
| `cd -` | Changes to the previous directory. |
| `cd`   | Changes to the user's home directory. |
| `cd ~` | Changes to the user's home directory. |
| `cd ~user`  | Changes to the home directory of the user `user`. |
| `cd /home/user` | Changes to the directory `/home/user`. |
| `ls [path]`| Lists the contents of the specified path. |
| `ls`   | Lists the contents of the current directory. |
| `cat [file]`   | Displays the contents of a specified file. |
| `cat`  | Reads from the standard input and displays the input. |
| `exit` | Exits the current shell. |
| `logout`   | Exits the current login session (not available in all shells). |
| `^D` or `^d`   | Exits the shell using the shortcut `CTRL+D`. |
| `man command`| Displays the manual page for a command. |
| `man -k keyword` | Returns all man pages containing the specified keyword. |
| `apropos keyword`| Searches for the keyword in the manual page descriptions. |
| `[command] --help` | Displays a help message for the specified command. |
| `whatis [command]`| Display one-line manual page descriptions |
| `clear`| Clears the entire terminal screen. |
| `^L` or `^l`   | Clears the terminal window (history still accessible via scroll). |
| `touch file(s)`  | Creates empty file(s). |
| --- | --- |
| **Man Page Commands** | **Description** |
| Enter, Down Arrow | Move down one line. |
| Up Arrow, `k` | Move up one line. |
| Spacebar, Page Down | Move down one page. |
| `g` | Go to the start or top. |
| `G` | Go to the end or bottom. |
| `h` | Display help. |
| `j` | Move down one line. |
| `k` | Move up one line. |
| `l` | Move right (scroll horizontally). |
| `q` | Quit. |
| --- | --- |
| **Directory Commands** | --- |
| `cd [directory]` | Changes the current directory to the specified directory.|
| `cd -`   | Returns to the previous directory.   |
| `cd` | Changes to the home directory.   |
| `cd ~`   | Changes to the home directory (shortcut).|
| `cd ~[username]` | Changes to the home directory of the specified user. |
| `cd /home/[username]`| Changes to the absolute path of the specified user's home directory. |
| `cd .`   | Stays in the current directory.  |
| `cd ..`  | Moves up one level to the parent directory.  |
| `mkdir [directory]`  | Creates a new directory with the specified name. |
| `mkdir -p [path]`| Creates nested directories, including intermediate ones, if they don't exist.|
| `rmdir [directory]`  | Removes an empty directory.  |
| `rm -r [directory]`  | Removes a directory and its contents recursively, prompting for confirmation for protected files.|
| `rm -rf [directory]` | Removes a directory and its contents forcefully, without any prompts or confirmation.|
| `pwd`| Displays the present working directory.  |
| `ls [path]`  | Lists the contents of the specified directory.   |
| `ls` | Lists the contents of the current directory.|
| `tree [directory]`   | Displays the directory structure in a tree format.   |
| `touch [file]`   | Creates an empty file with the specified name.   |
| `git init`   | Initializes a new Git repository in the current directory.   |
| `git add .`  | Stages all changes in the current directory for the next commit. |
| `git commit -m [message]`| Creates a commit with the specified message. |
| --- | --- |
| **Summary of Viewing File and Directory Commands** | --- |
| `ls`  | Lists files and directories in the current directory.|
| `ls -l`   | Lists files and directories with detailed information (long format).|
| `ls -a`   | Lists all files, including hidden files (starting with `.`).|
| `ls --color`  | Displays files with color-coded output (for file types).|
| `ls -F`   | Appends indicators (e.g., `/` for directories, `*` for executables) to file names.  |
| `ls -t`   | Lists files sorted by modification time (most recent first).|
| `ls -r`   | Reverses the order of the file list.|
| `ls -R`   | Recursively lists all files and directories.|
| `ls -d [Directory]`   | Displays information about directories, not their contents. |
| `ls "file name with space"`   | Lists a file with spaces in its name by enclosing it in quotes. |
| `ls file\ name\ with\ space`  | Lists a file with spaces in its name by escaping spaces with a backslash (`\`). |
| `ls -b`   | Displays file names with non-printable characters as escape sequences.  |
| `ls -alf` | Combines options: lists all files, including hidden ones, in long format.   |
| `ls -altr`| Lists all files, including hidden ones, in long format, sorted by time in reverse order.|
| `echo $LS_COLORS` | Displays the current color settings for the `ls` command.   |
| `export LS_COLORS="di=01;32:ln=01;33"` | Customizes the `ls` color scheme (e.g., green for directories, yellow for links).  |
| `ln -s [target] [symlink]`| Creates a symbolic link named `[symlink]` pointing to `[target]`.   |
| `cat myfilelink`  | Displays the contents of the file pointed to by the symbolic link `myfilelink`. |
| `cd mydirlink`| Changes the current directory to the one pointed to by the symbolic link `mydirlink`.   |
| `tree`| Displays the directory structure as a tree.|
| `tree -d` | Displays only directories in the tree structure.   |
| `tree -C` | Displays the tree structure with color-coded output.   |
| --- | --- |
| **Permissions Commands** | --- |
| `ls -l`| Lists detailed information about files and directories in the current directory.  |
| `ls -ld /home/sri/Documents/`  | Displays detailed information about the `/home/sri/Documents` directory itself.  |
| `groups`   | Lists the groups the current user belongs to.|
| `id`   | Displays user ID (UID), group ID (GID), and other group memberships. |
| `id -G`| Displays the numeric GIDs of all groups the user belongs to. |
| `id -Gn`   | Lists the group names of all groups the user belongs to. |
| `groups [username]`| Lists the groups a specified user belongs to.|
| `chmod [user][operation][permissions] [file]` | Changes permissions for a file or directory. |
| `chmod u+x myscript.sh`| Adds execute permission to the user for `myscript.sh`.   |
| `chmod g-w myscript.sh`| Removes write permission from the group for `myscript.sh`.   |
| `chmod o=r file.txt` | Sets read-only permission for others on `file.txt`.  |
| `chmod a+x program.sh` | Adds execute permission for all users on `program.sh`.   |
| `chmod o= mydoc.txt`   | Removes all permissions for others on `mydoc.txt`.   |
| `chmod a= afile.txt`   | Removes all permissions for all users on `afile.txt`.|
| `chmod u=rwx file.txt` | Grants read, write, and execute permissions to the user for `file.txt`.  |
| `chmod 7 dir`  | Grants full access (rwx) to the owner only for `dir`.|
| `chmod 77 dir` | Grants full access (rwx) to owner and group for `dir`.   |
| `chmod 777 dir`| Grants full access (rwx) to everyone for `dir`.  |
| `cat /etc/group`   | Displays the contents of the `/etc/group` file, showing group information.   |
| `groupadd [options] GROUP_NAME`| Creates a new group with the specified name. |
| `sudo usermod -aG group userid`| Adds a user to a specified group.|
| `sudo groupadd -g <number> <group_name>` | Creates a group with a specific GID. |
| `sudo groupdel <group_name>` | Deletes a specified group.   |
| `sudo chgrp sales sales.report`| Changes the group owner of `sales.report` to `sales`.|
| `umask`| Displays the current umask value.|
| `umask valid_octal`| Changes the current umask to the specified value.|
| `umask -S`| Displays the current umask in Symbolic form.|
| `umask u=rwx,g=rx,o=rx`| Changes the current umask to the specified value in Symbolic format|
| `chmod 4755 /usr/bin/passwd`   | Sets the setuid permission on `passwd`, allowing execution as the file's owner (root).   |
| `chmod 2755 /usr/bin/locate`   | Sets the setgid permission on `locate`, allowing execution as the file's group.  |
| `chmod 1777 /tmp`  | Sets the sticky bit on `/tmp`, ensuring only owners can delete their files within the directory.  |
| --- | --- |
| **Viewing Files Commands** | --- |
| `cat [file]` | Displays the entire contents of a file. Useful for smaller files. |
| `more [file]` | Displays a file one page at a time. Useful for larger files. |
| `less [file]` | Allows backward navigation and searching within a file. |
| `head [file]` | Displays the first 10 lines of a file. |
| `head -N [file]` | Displays the first N lines of a file. |
| `tail [file]` | Displays the last 10 lines of a file. |
| `tail -N [file]` | Displays the last N lines of a file. |
| `tail -f [file]` | Displays the last lines of a file and follows it as it grows (useful for logs). |
| `less [file]` + `F` | Follow a file as it grows in real-time within `less`. |
| ---| ---|
| **Vim Commands** | **Description** |
| `k` | Move up one line |
| `j` | Move down one line |
| `h` | Move left one character |
| `l` | Move right one character |
| `w` | Move right one word |
| `b` | Move left one word |
| `^` | Move to the beginning of the line |
| `$` | Move to the end of the line |
| `gg` | Move to the beginning of the file |
| `G` | Move to the end of the file |
| `i` | Insert at the current position |
| `I` | Insert at the beginning of the line |
| `a` | Append text after the cursor position |
| `A` | Append text at the end of the line |
| `:w` | Save the file |
| `:w!` | Save the file even if permissions are not set |
| `:q` | Quit the editor |
| `:q!` | Quit without saving the file |
| `:wq` or `:x` | Save and quit |
| `:n` | Go to line `n` |
| `:$` | Go to the last line of the file |
| `:set nu` | Enable line numbering |
| `:set nonu` | Disable line numbering |
| `:help` | Access the help documentation |
| `3j`, `20iText`, `80i_` | Repeat a command with a number prefix (e.g., 3j to move down 3 lines) |
| `x` | Delete a character |
| `dw` | Delete a word |
| `dd` | Delete a line |
| `D` | Delete from the current position to the end of the line |
| `r` | Replace the current character |
| `cw` | Change the current word |
| `cc` | Change the current line |
| `c$` | Change from the current position to the end of the line |
| `~` | Reverse the case of the current character |
| `yy` | Yank (copy) the current line |
| `yw` | Yank a word |
| `p` | Paste the most recent yanked text |
| `u` | Undo the last change |
| `Ctrl + r` | Redo the last undone change |
| `/pattern` | Start a forward search for `<pattern>` |
| `?pattern` | Start a reverse search for `<pattern>` |
| `n` | Move the cursor to the next match of a search |
| `N` | Move the cursor to the previous match of a search |
| --- | --- |
| **Deleting, Moving, and Renaming Files & Directories Commands** | --- |
| `rm file` | Remove a file. |
| `rm -r file_or_directory` | Remove a directory or file recursively, including its contents. |
| `rm -rf file_or_directory` | Forcefully remove a directory or file recursively without confirmation. |
| `chmod 444 write_protected_file` | Make a file write-protected (read-only for all users). |
| `rm *.txt` | Use a wildcard to remove all `.txt` files in the current directory. |
| `rm * -r` | Remove all files and directories recursively in the current directory. |
| `rm file?.txt` | Remove files matching a single-character wildcard pattern. |
| `rm .hidden_file_pattern` | Remove hidden files matching a specific pattern. |
| `rm .*.txt` | Remove hidden files with a `.txt` extension. |
| `cp source_file destination_file_directory` | Copy a file to a specific directory. |
| `cp source_file1 [source_fileN ...] destination_directory` | Copy multiple files to a directory. |
| `cp -i source_file destination_directory` | Copy a file interactively, prompting before overwriting. |
| `cp -r source_directory destination_directory` | Recursively copy a directory and its contents. |
| `mv source destination` | Move a file or directory to a new location. |
| `mv old_name new_name` | Rename a file or directory. |
| `mv -i source destination` | Move a file or directory interactively, prompting before overwriting. |
| --- | --- |
| **Finding, Sorting, and Comparing Files & Directories Commands** | --- |
| `find [path...][options] [expression]` | General syntax of the `find` command. |
| `find . -name name_pattern` | Find files by name (case-sensitive). |
| `find . -iname name_pattern` | Find files by name (case-insensitive). |
| `find ~ -name name_pattern -ls` | Find files by name and list their details. |
| `find . -mtime [+-]number_of_days` | Find files modified within a specific number of days. |
| `find . -size [+-]size` | Find files by size (e.g., +10M for files larger than 10MB). |
| `find . -newer file_or_directory` | Find files that are newer than a specific file or directory. |
| `find . -name name_pattern -exec some_commands {} \;` | Execute a command on each found item. |
| `find ~ -name bfile -mtime -1 -exec cat {} \;` | Combine `find` options: find files modified in the last day and display their content. |
| `locate pattern` | Locate files by pattern using an indexed database. |
| `sort file` | Sort the contents of a file line by line. |
| `sort -n file` | Sort the contents of a file numerically. |
| `sort -k column_number file` | Sort by a specific column. |
| `sort -r table.txt` | Sort the contents of a file in reverse order. |
| `sort [-k number]+ filename` | Sort based on a specific column or columns. |
| `sort -n -u file_name` | Sort uniquely by numeric order (removes duplicates). |
| `sort -n -k 2 -u table.txt` | Sort uniquely based on column 2 (numeric). |
| `diff file_or_dir file_or_dir` | Compare two files or directories line by line. |
| `sdiff file_or_dir file_or_dir` | Side-by-side comparison of files or directories. |
| `vimdiff file1 file2` | Compare two files using `vimdiff` in Vim editor. |
| --- | --- |
| **I/O Redirection Commands** | --- |
| `sort`   | Sorts input lines alphabetically. Pressing `CTRL + D` acts as EOF.  |
| `command1 \| command2`   | Feeds the output of `command1` as input to `command2`.  |
| `grep [options] 'pattern' [file...]`   | Searches for a pattern in the given file(s).|
| `grep -i pattern file` | Performs a case-insensitive search for the pattern in the file. |
| `grep pattern file[s]` | Searches for the pattern in one or more files.  |
| `grep -i ^a words`   | Finds lines starting with `a` (case-insensitive) in the file `words`.   |
| `grep -n pattern file`   | Displays line numbers along with matching lines.|
| `grep -r pattern file_or_directory`  | Recursively searches for the pattern in files and subdirectories.   |
| `grep -rl pattern file_or_directory` | Lists file names containing the pattern (recursive search). |
| `grep -v pattern file` | Displays lines that do not match the pattern.   |
| `grep -c pattern file`   | Counts the number of lines matching the pattern.|
| `grep -w pattern file`   | Matches the whole word pattern in the file. |
| `grep -E pattern file`   | Uses extended regular expressions for pattern matching. |
| `command < file` | Redirects the content of `file` as input to `command`.  |
| `command > file`   | Redirects the output of `command` to `file` (overwriting if exists).|
| `command >> file`   | Appends the output of `command` to `file`|
| `command 2> error_file`  | Redirects standard error (stderr) to `error_file`.  |
| `command 1> output_file` | Redirects standard output (stdout) to `output_file`.|
| `command > file 2>&1`| Redirects both stdout and stderr to `file`. |
| `ls >> output_file 2>&1` | Appends both stdout and stderr of `ls` to `output_file`.|
| `ls -fsw >> output_file 2>&1`| Appends `ls` output with flags `-fsw` to `output_file`, including errors.   |
| `command > /dev/null`| Discards stdout by redirecting it to `/dev/null`.   |
| `command 2> /dev/null`   | Discards stderr by redirecting it to `/dev/null`.   |
| `command < file > command`   | Redirects `file` as input and outputs to another `command`. |
| `command \| command > file`   | Pipes output from one command and redirects it to a file.   |
| --- | --- |
| **Additional Command Line Concepts Commands** | --- |
| `echo $ENVIRONMENT_VARIABLE` | Displays the value of the specified environment variable.   |
| `printenv ENVIRONMENT_VARIABLE`  | Prints the value of the specified environment variable. |
| `printenv`   | Lists all environment variables and their values.   |
| `env`| Displays the current environment, including variables.  |
| `VAR_NAME=value` | Creates a shell variable `VAR_NAME` with the specified value.   |
| `export A_NEW_ENV_VAR`   | Marks `A_NEW_ENV_VAR` as an environment variable available to subprocesses. |
| `bash -c 'echo $A_NEW_ENV_VAR'`  | Runs a subshell and prints the value of `A_NEW_ENV_VAR` in it.  |
| `unset VAR_NAME` | Deletes the shell variable or environment variable `VAR_NAME`.  |
| `alias alias_name='command'` | Creates a shortcut (`alias_name`) for the specified command.|
| `alias`  | Lists all currently defined aliases.|
| `unalias alias_name` | Removes the specified alias.|
| `unalias -a` | Removes all aliases.|
| `source ~/.bashrc` or `. ~/.bashrc`  | Reloads the shell configuration file (`.bashrc`).   |
| `echo $HISTSIZE` | Displays the maximum number of commands stored in the shell history.|
| `history`| Lists the command history.  |
| `!Number_from_history`   | Re-executes the command at the specified history number.|
| `!!` | Re-executes the last command.   |
| `!pattern`   | Re-executes the most recent command matching the pattern.   |
| `Ctrl + r; pattern; Ctrl + r`  | Initiates reverse search in command history for a matching pattern. |
| `Ctrl + c` or `<esc>`  | Cancels or exits reverse search.|
| **Tab Completion** | Auto-completes commands or file names.  |
| `echo "words .. \ more words "`  | Concatenates lines using `\` for multiline command input.   |
| --- | --- |
| **Processes & Job Control Commands** | --- |
| `ps` | Lists running processes on the system.  | `ps`  |
| `ps -e`  | Displays all processes running on the system.   | `ps -e`   |
| `ps -ef` | Displays all processes with a full format listing.  | `ps -ef`  |
| `ps -eH` | Displays processes in a hierarchical (tree) format. | `ps -eH`  |
| `ps -e --forest` | Displays processes in a tree format using ASCII art.| `ps -e --forest`  |
| `ps -u <username>`   | Displays processes running for a specific user. | `ps -u john`  |
| `ps -p <PID>`| Displays information for a specific process ID (PID).   | `ps -p 1234`  |
| `pstree` | Displays processes in a hierarchical tree format.   | `pstree`  |
| `top`| Displays a real-time process list with system performance information.  | `top` |
| `htop`   | Interactive and improved version of `top` with a user-friendly interface.   | `htop`|
| `sudo apt install htop`  | Installs `htop` on a Debian-based system.   | `sudo apt install htop`   |
| `kill <PID>` | Terminates a running process using its process ID (PID).| `kill 5678`   |
| `command &`  | Starts a command in the background. | `sleep 60 &`  |
| `Ctrl-C` | Kills the foreground process.  | (Press `Ctrl-C` while the job is in the foreground)   |
| `Ctrl-Z` | Suspends the foreground process.   | (Press `Ctrl-Z` while the job is running) |
| `bg [%num]`  | Resumes a suspended job in the background.  | `bg %1`   |
| `bg` | Resumes the most recently suspended job in the background.  | `bg`  |
| `fg [%num]`  | Brings a backgrounded job to the foreground.| `fg %1`   |
| `fg` | Brings the most recent background job to the foreground.| `fg`  |
| `kill [%num]` or `kill <PID>`| Kills a job by job number or PID.   | `kill %1` or `kill 12345` |
| `jobs` or `jobs [%num]`  | Lists all jobs or a specific job by job number.| `jobs` or `jobs %1`|
| `kill -l`| Lists available signals.| `kill -l`|
| `kill -<signal> %num` or `kill -<signal> <PID>` | Sends a specific signal to a job. | `kill -9 %1` or `kill -9 12345`|
| `kill -9`| Force kills a job using the SIGKILL signal.| `kill -9 %1`|
| `kill -15`| Kills a job using the SIGTERM signal.| `kill -15 %1`|
| --- | --- |
| **Switching Users Commands** | --- |
| `su`          | Switch to the root user account. Prompts for the root password. |
| `su [user]`   | Switch to the specified user account. Prompts for the user's password. |
| `su -`        | Switch to the root user and simulate a fresh login shell. |
| `su - [user]` | Switch to the specified user and simulate a fresh login shell. |
| `su -c [command]` | Execute a single command as the root user. |
| `sudo command` | Execute a command as the root user. Prompts for the user's password. |
| `sudo -l`     | List the commands the user is allowed to execute with `sudo`. |
| `sudo su`     | Switch to the root user using `sudo`. |
| `sudo su -`   | Switch to the root user and simulate a fresh login shell using `sudo`. |
| `sudo su [user]` | Switch to another user using `sudo`. |
| `sudo su - [user]` | Switch to another user and simulate a fresh login shell using `sudo`. |
| `sudo su user -c [command]` | Execute a command as another user using `sudo`. |
| `sudo -u user [command]` | Execute a command as the specified user using `sudo`. |
| `whoami`      | Display the current user's username. |
| `exit`        | Exit the current shell or logout of the current user session. |
| --- | --- |
| **Software Installation Commands** | --- |
| `sudo apt update` | Update package list and metadata from repositories |
| `sudo apt upgrade` | Upgrade all installed packages to the latest available versions |
| `sudo apt autoremove` | Remove unnecessary packages that were installed as dependencies but are no longer needed |
| `sudo apt clean` | Clear the local repository cache to free up space |
| `sudo apt search search-pattern` | Search for packages matching the search pattern |
| `sudo apt install package` | Install a package |
| `sudo apt install -y package` | Install a package and automatically answer "yes" to prompts |
| `sudo apt remove package` | Remove a package, leaving behind configuration files |
| `sudo apt purge package` | Remove a package, including its configuration files |
| `sudo apt show package` | Display detailed information about a package |
| `sudo apt full-upgrade` | Perform an upgrade with more aggressive handling of dependencies |
| `-y` | 'yes' to all the upcoming download requests |
| `dpkg -l` | List all installed packages. |
| `dpkg -S /path/to/file` | Find the package that provides a specific file. |
| `sudo dpkg -i package.deb` | Install a package from a `.deb` file. |
| `dpkg -L <package>` | List all files installed by a package. |
| `sudo dpkg -i package.deb` | Install a `.deb` file. |
| `sudo apt install -f` | Fix unmet dependencies after installing a `.deb` package. |
| `dpkg -L <package>` | View which files a package has installed. |
| `dpkg -S /path/to/file` | Identify which package installed a specific file. |

---