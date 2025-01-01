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
  * [Summary](#Summary-of-Permissions-Commands)
* [Permissions](#Permissions)
* [Viewing and Editing Files](#Viewing-and-Editing-Files)
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

| **Distribution**        | **Primary Usage** | **Support Model**    | **Notes**                                                                 |
|--------------------------|-------------------|-----------------------|---------------------------------------------------------------------------|
| **Linux Mint**           | Desktop           | Community             | User-friendly, ideal for beginners.                                       |
| **Ubuntu**               | Both              | Community             | Widely used with LTS versions for stability.                              |
| **Debian**               | Both              | Community             | Stable and reliable, popular for servers.                                 |
| **Fedora**               | Both              | Community             | Cutting-edge features, upstream for RHEL.                                 |
| **openSUSE**             | Both              | Community/Corporate   | Offers Leap (stable) and Tumbleweed (rolling release) versions.           |
| **Arch Linux**           | Desktop           | Community             | Minimalist and highly customizable.                                       |
| **CentOS**               | Server            | Community             | RHEL-based, stable, enterprise-ready.                                     |
| **RHEL**                 | Server            | Corporate             | Commercial support for enterprise environments.                           |
| **Manjaro**              | Desktop           | Community             | Arch-based with user-friendly tools.                                      |
| **Elementary OS**        | Desktop           | Community             | Aesthetic design, excellent for newcomers.                                |
| **Kali Linux**           | Desktop           | Community             | Specialized for penetration testing and security tasks.                   |
| **Zorin OS**             | Desktop           | Community             | Perfect for users transitioning from Windows.                             |
| **Pop!_OS**              | Desktop           | Community             | Developer- and gamer-friendly, based on Ubuntu.                           |
| **AlmaLinux**            | Server            | Community             | RHEL clone, focused on enterprise users.                                  |
| **Slackware**            | Both              | Community             | Traditional UNIX-like experience.                                         |
| **MX Linux**             | Desktop           | Community             | Lightweight and efficient for older hardware.                             |

**Legend**:  
- **Desktop**: Tailored for personal or workstation use.  
- **Server**: Designed for stability, often used in enterprise or hosting environments.  
- **Community**: Developed and maintained by volunteers.  
- **Corporate**: Backed by companies providing commercial support.  

---

## Why Learn Linux?  
The core principles and functionalities of Linux remain consistent across distributions, making it a universal skill for tech enthusiasts and professionals. Linux powers:  
- **90% of the world’s supercomputers**,  
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
   These are collections of compiled object files that are embedded directly into the executable at compile time. When a program links to a static library, the library’s code becomes part of the program itself, making the executable larger but eliminating the need for the library to be present at runtime.

#### Dynamic Libraries (`.so` files):  
   These libraries are loaded into memory at runtime when the program is executed. They are not part of the program's executable file but are instead shared by multiple programs. This reduces memory usage because the library is only loaded into memory once. Dynamic libraries can be updated independently of the programs using them, providing greater flexibility.
)**:
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

### Notes:
1. Some directories like `/media` or `/mnt` might not have content unless specifically used.
2. On modern systems, certain directories like `/bin` and `/sbin` may be symlinks to `/usr/bin` and `/usr/sbin`.
3. The layout and contents of these directories can vary slightly between Linux distributions.

| Commands                          | Description                                                       |
|-----------------------------------|-------------------------------------------------------------------|
| `ls [dir]`                        | Lists the contents of a directory.                                |
| `whereis -b [command]`            | Searches for the binary (executable) file of a command.           |
| `whereis -m [command]`            | Searches for the manual page of a command.                        |
| `whereis -s [command]`            | Searches for the source code of a command.                        |
| `whereis -u [command]`            | Finds unlinked files (files not listed in the system's database). |
| `whereis -B <path> [command]`     | Specifies a directory to search for binaries.                     |
| `whereis -M <path> [command]`     | Specifies a directory to search for manual pages.                 |
| `whereis -S <path> [command]`     | Specifies a directory to search for source files.                 | 

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

The terms **terminal** and **shell** are often used interchangeably, but they refer to different components of a Linux or Unix-based system. Here’s the distinction:

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
  - It’s a window or program that allows interaction with the system.
  
- **Shell**:  
  - The **program** that interprets and executes commands typed into the terminal.
  - It’s the command processor that runs inside the terminal and interacts with the operating system.

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

| Key                   | Action                      |
|-----------------------|-----------------------------|
| Enter, Down Arrow     | Move down one line.         |
| Up Arrow              | Move up one line.           |
| Spacebar, Page Down   | Move down one page.         |
| Page Up               | Move up one page.           |
| `g`                   | Go to the start or top.     |
| `G`                   | Go to the end or bottom.    |
| `h`                   | Display help.               |
| `j`                   | Move down one line.         |
| `k`                   | Move up one line.           |
| `q`                   | Quit.                       |


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

| Command                | Description |
|------------------------|-------------|
| `pwd`                  | Displays the present working directory. |
| `cd [directory]`       | Changes the current directory to the specified directory. |
| `cd -`                 | Changes to the previous directory. |
| `cd`                   | Changes to the user's home directory. |
| `cd ~`                 | Changes to the user's home directory. |
| `cd ~user`              | Changes to the home directory of the user `user`. |
| `cd /home/user`         | Changes to the directory `/home/user`. |
| `ls [path]`            | Lists the contents of the specified path. |
| `ls`                   | Lists the contents of the current directory. |
| `cat [file]`           | Displays the contents of a specified file. |
| `cat`                  | Reads from the standard input and displays the input. |
| `exit`                 | Exits the current shell. |
| `logout`               | Exits the current login session (not available in all shells). |
| `^D` or `^d`           | Exits the shell using the shortcut `CTRL+D`. |
| `man command`        | Displays the manual page for a command. |
| `man -k keyword`     | Returns all man pages containing the specified keyword. |
| `apropos keyword`    | Searches for the keyword in the manual page descriptions. |
| `[command] --help`     | Displays a help message for the specified command. |
| `whatis [command]`    | Display one-line manual page descriptions |
| `clear`                | Clears the entire terminal screen. |
| `^L` or `^l`           | Clears the terminal window (history still accessible via scroll). |
| `touch file(s)`      | Creates empty file(s). |

### Navigating man pages

| Key                  | Action                               |
|----------------------|--------------------------------------|
| Enter, Down Arrow     | Move down one line.                 |
| Up Arrow, `k`         | Move up one line.                   |
| Spacebar, Page Down   | Move down one page.                 |
| `g`                   | Go to the start or top.             |
| `G`                   | Go to the end or bottom.            |
| `h`                   | Display help.                       |
| `j`                   | Move down one line.                 |
| `k`                   | Move up one line.                   |
| `l`                   | Move right (scroll horizontally).   |
| `q`                   | Quit.                               |

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
```
The loop happens because `cd -` toggles between the current directory and the last visited directory. When you use `cd .`, it doesn’t change the directory, so the "previous directory" remains the same. Repeatedly using `cd -` in the same location keeps toggling to the same directory, causing the apparent loop.

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
mkdir: cannot create directory ‘dir/sub-dir/sub-sub-dir’: No such file or directory
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

| Command                  | Description                                                                                           |
|--------------------------|-------------------------------------------------------------------------------------------------------|
| `cd [directory]`         | Changes the current directory to the specified directory.                                            |
| `cd -`                   | Returns to the previous directory.                                                                   |
| `cd`                     | Changes to the home directory.                                                                       |
| `cd ~`                   | Changes to the home directory (shortcut).                                                            |
| `cd ~[username]`         | Changes to the home directory of the specified user.                                                 |
| `cd /home/[username]`    | Changes to the absolute path of the specified user’s home directory.                                 |
| `cd .`                   | Stays in the current directory.                                                                      |
| `cd ..`                  | Moves up one level to the parent directory.                                                          |
| `mkdir [directory]`      | Creates a new directory with the specified name.                                                     |
| `mkdir -p [path]`        | Creates nested directories, including intermediate ones, if they don’t exist.                        |
| `rmdir [directory]`      | Removes an empty directory.                                                                          |
| `rm -r [directory]`      | Removes a directory and its contents recursively, prompting for confirmation for protected files.    |
| `rm -rf [directory]`     | Removes a directory and its contents forcefully, without any prompts or confirmation.                |
| `pwd`                    | Displays the present working directory.                                                              |
| `ls [path]`              | Lists the contents of the specified directory.                                                       |
| `ls`                     | Lists the contents of the current directory.                                                        |
| `tree [directory]`       | Displays the directory structure in a tree format.                                                   |
| `touch [file]`           | Creates an empty file with the specified name.                                                       |
| `git init`               | Initializes a new Git repository in the current directory.                                           |
| `git add .`              | Stages all changes in the current directory for the next commit.                                     |
| `git commit -m [message]`| Creates a commit with the specified message.                                                         |

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

| **Field**              | **Description**                                          | **Example**            |
|------------------------|----------------------------------------------------------|------------------------|
| **Permissions**         | Indicates file type and access permissions.             | `drwxr-xr-x`           |
| **Links**               | Number of hard links to the file or directory.          | `2`                    |
| **Owner**               | Name of the user who owns the file or directory.        | `sri`                  |
| **Group**               | Group associated with the file or directory.            | `sri`                  |
| **File Size**           | Size of the file in bytes.                              | `4096`                 |
| **Modification Time**   | Last modification date and time.                        | `Jan  1 12:11`         |
| **Name**                | Name of the file or directory.                          | `Desktop`              |

---

### Example Breakdown

For a specific file:
```bash
-rw-r--r-- 1 sri sri 512 Dec 31 21:00 shopping-list.txt
drwxr-xr-x 13 sri sri 4096 Dec 29 18:04 Documents

```

| **Field**              | **Value**           | **Explanation**                                      |
|------------------------|---------------------|-----------------------------------------------------|
| **Permissions**         | `drwxr-xr-x`       | Regular directory with read/write/execute for owner, read and execute for group and others. |
| **Links**               | `13`                | Single hard link.|
| **Owner**               | `sri`              | File is owned by the user `sri`.|
| **Group**               | `sri`              | Associated group is `sri`.|
| **File Size**           | `4096`              | File is 4096 bytes in size.|
| **Modification Time**| `Dec 29 18:04`| File was last modified on Dec 31 at 9:00 PM.|
| **Name**                | `Document`| Name of the directory is `Document`.|

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

Here’s a list of file type indicators used in Linux with the `ls` command:

| **Symbol in Permission String** | **File Type**           | **Description**                                                                                                                                           | **Default Color**   |
|------------|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| `-`        | Regular file             | Standard files that contain data, such as text, images, videos, or executables.                                                                            | Default (white)     |
| `b`        | Block special file       | Files that represent hardware devices capable of data storage, such as hard drives or USB drives, accessed in fixed-size blocks.                           | Yellow with bold    |
| `c`        | Character special file   | Files that represent hardware devices, such as keyboards or terminals, accessed character by character. Interfaces with devices that transfer data in streams. | Yellow with bold    |
| `d`        | Directory                | Containers for files and other directories, forming a hierarchical structure in the file system.                                                           | Blue                |
| `l`        | Symbolic link            | Special files that act as shortcuts, pointing to another file or directory.                                                                                | Cyan (light blue)   |
| `p`        | FIFO (named pipe)        | Used in IPC. Files that act as conduits, allowing two processes to communicate by writing and reading data in a first-in, first-out (FIFO) order.           | Yellow (brown)      |
| `s`        | Socket                   | Special files used for inter-process communication (IPC), typically for network services or local socket connections. Enables bidirectional communication. | Magenta (purple)    |
| `?`        | Unknown file type        | Files that do not match any recognized file type.                                                                                                          | N/A                 |
| `*`        | Executable               | Files that can be executed as programs or scripts.                                                                                                        | Green               |
| `/`        | Directory (Indicator)    | Indicates a directory in file listings.                                                                                                                   | Blue                |
| `@`        | Symlink (Symbolic link)  | Indicates a symbolic link in file listings.                                                                                                               | Cyan (light blue)   |
| `=`        | Socket (Indicator)       | Indicates a socket in file listings.                                                                                                                      | Magenta (purple)    |
| `\|`       | Named pipe (FIFO) (Indicator) | Indicates a named pipe in file listings.                                                                                                                  | Yellow (brown)      |


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
ls -lF

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

## Summary of File and Directory Commands
| Command                         | Description                                                                                  |
|---------------------------------|----------------------------------------------------------------------------------------------|
| `$ ls`                          | Lists files and directories in the current directory.                                        |
| `$ ls -l`                       | Lists files and directories with detailed information (long format).                        |
| `$ ls -a`                       | Lists all files, including hidden files (starting with `.`).                                |
| `$ ls --color`                  | Displays files with color-coded output (for file types).                                    |
| `$ ls -F`                       | Appends indicators (e.g., `/` for directories, `*` for executables) to file names.          |
| `$ ls -t`                       | Lists files sorted by modification time (most recent first).                                |
| `$ ls -r`                       | Reverses the order of the file list.                                                        |
| `$ ls -R`                       | Recursively lists all files and directories.                                                |
| `$ ls -d [Directory]`           | Displays information about directories, not their contents.                                 |
| `$ ls "file name with space"`   | Lists a file with spaces in its name by enclosing it in quotes.                             |
| `$ ls file\ name\ with\ space`  | Lists a file with spaces in its name by escaping spaces with a backslash (`\`).             |
| `$ ls -b`                       | Displays file names with non-printable characters as escape sequences.                      |
| `$ ls -alf`                     | Combines options: lists all files, including hidden ones, in long format.                   |
| `$ ls -altr`                    | Lists all files, including hidden ones, in long format, sorted by time in reverse order.    |
| `$ echo $LS_COLORS`             | Displays the current color settings for the `ls` command.                                   |
| `$ export LS_COLORS="di=01;32:ln=01;33"` | Customizes the `ls` color scheme (e.g., green for directories, yellow for links).      |
| `$ ln -s [target] [symlink]`    | Creates a symbolic link named `[symlink]` pointing to `[target]`.                           |
| `$ cat myfilelink`              | Displays the contents of the file pointed to by the symbolic link `myfilelink`.             |
| `$ cd mydirlink`                | Changes the current directory to the one pointed to by the symbolic link `mydirlink`.       |
| `$ tree`                        | Displays the directory structure as a tree.                                                |
| `$ tree -d`                     | Displays only directories in the tree structure.                                           |
| `$ tree -C`                     | Displays the tree structure with color-coded output.                                       |


# Permissions 

## Understanding File Types

The `ls -l` command displays long listings of files and directories, including the file types. The first character of the permission string indicates the file type. Here are the common file types:

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
sri@envy:~
$ ls -ld /home/sri/Documents/
drwxr-xr-x 13 sri sri 4096 Jan  1 13:35 /home/sri/Documents/
```

In this case:
- `drwxr-xr-x`: Indicates a directory (`d` at the beginning).
- The permissions `rwxr-xr-x` mean that the owner (`sri`) can read, write, and execute; the group (`users`) can read and execute, but not write; others can also read and execute but cannot write.

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
-rw-r--r-- 1 sri users 10400 Jun 14 09:31 sales.data
```

Here:
- **User** (`sri`) is the file owner.
- **Group** (`users`) is the group owner.
- **Others** are anyone else who is not the owner or part of the group.

### Viewing Group Memberships

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
$ groups [username]
```

These commands display the groups the user belongs to, which help in determining the permissions granted to each user category.

## Changing Permissions

Linux provides the `chmod` (**change mode**) command to modify file permissions. Permissions can be changed either using **symbolic** or **numeric (octal) modes**.
Certainly! Here's an elaboration on **symbolic mode** for changing file permissions using the `chmod` command:

---

### Symbolic Mode Permissions

In **symbolic mode**, you can modify file or directory permissions in a human-readable format. The symbolic notation allows you to specify **who** the change applies to, **what action** to perform, and **which permissions** to apply or remove.

#### Syntax
```bash
$ chmod [user][operation][permissions] [file]
```

#### Components
1. **[user]:** Specifies which set of users the change applies to:
   - `u`: The owner of the file (user).
   - `g`: The group associated with the file.
   - `o`: All other users (others).
   - `a`: All users (shorthand for `u`, `g`, and `o`).

2. **[operation]:** Defines what action to take:
   - `+`: Add the specified permissions.
   - `-`: Remove the specified permissions.
   - `=`: Set the permissions exactly as specified, overriding existing ones.

3. **[permissions]:** The type of access being granted or removed:
   - `r`: Read permission (view file contents).
   - `w`: Write permission (modify file contents).
   - `x`: Execute permission (run the file as a program/script).

---

#### Examples

##### 1. Add execute permission for the user (owner):
```bash
$ chmod u+x myscript.sh
```
- Adds execute (`x`) permission for the file's owner (`u`).
- After this, the owner can run the script as a program.

##### 2. Remove write permission for the group:
```bash
$ chmod g-w myscript.sh
```
- Removes write (`w`) permission for the file's group (`g`).
- Members of the group can no longer modify the file.

##### 3. Set read-only permission for others:
```bash
$ chmod o=r file.txt
```
- Sets the permission for others (`o`) to read-only (`r`).
- Removes any existing write or execute permissions for others.

##### 4. Allow all users to execute a file:
```bash
$ chmod a+x program.sh
```
- Adds execute permission for all users (`a`), including owner, group, and others.

##### 5. Set exact permissions for the group:
```bash
$ chmod g=rw myfile.txt
```
- Sets the group (`g`) permissions to read (`r`) and write (`w`) only.
- Removes any execute or other permissions previously set for the group.

##### 6. Remove all permissions for others:
```bash
$ chmod o= mydoc.txt
```
- Removes all permissions for others (`o`), making the file inaccessible to them.


#### Advanced Permissions Modifications:

##### Multiple Changes in One Command:
You can modify permissions for different categories simultaneously. For example:
```bash
chmod u+x,g-w,o=r file.txt
```
This command adds execute permission for the user, removes write permission for the group, and sets read-only permission for others. The resulting permissions string will look like:
```bash
-rwxr--r-- 
```

##### Explicit Permission Setting:
The equal sign (`=`) can be used to overwrite existing permissions for a user category:
```bash
chmod u=rwx file.txt
```
This sets the user’s permissions to read, write, and execute, overriding any existing permissions for the user category. The resulting permissions string will look like:
```bash
-rwxr--r-- 
```

---

#### Practical Usage

Symbolic mode is especially helpful for fine-tuning permissions without needing to know the numeric representation (e.g., `chmod 755`). You can use it to incrementally modify permissions, such as granting temporary access to a script or restricting access to sensitive files.


### Numeric Mode Permissions

In **numeric (octal) mode**, file permissions are represented using a three-digit number, where each digit specifies the permissions for a different category of users: **owner (user)**, **group**, and **others**. Each digit is the sum of the numeric values assigned to the permissions:

- `r` (read) = **4**
- `w` (write) = **2**
- `x` (execute) = **1**
- No permission = **0**

By adding these values together, you can represent any combination of permissions numerically.

---

#### Permissions Table

The following table shows how the numeric values correspond to permission combinations:

| **Permissions** | **Numeric Value** | **Description**                     |
|------------------|-------------------|-------------------------------------|
| `rwx`            | 7                 | Read, write, and execute            |
| `rw-`            | 6                 | Read and write                      |
| `r-x`            | 5                 | Read and execute                    |
| `r--`            | 4                 | Read only                           |
| `-wx`            | 3                 | Write and execute                   |
| `-w-`            | 2                 | Write only                          |
| `--x`            | 1                 | Execute only                        |
| `---`            | 0                 | No permissions                      |

---

#### How It Works

1. **Structure of Permissions**:
   - The **first digit** applies to the file **owner**.
   - The **second digit** applies to the **group**.
   - The **third digit** applies to **others** (everyone else).

   For example:
   - `chmod 754` assigns:
     - **7** (rwx): Owner has full permissions (read, write, execute).
     - **5** (r-x): Group can read and execute, but not write.
     - **4** (r--): Others can only read.

2. **Calculating the Numeric Value**:
   - Add the numeric values for the desired permissions.
   - Example: `rw-` (read + write) = `4 + 2 = 6`.

---

#### Examples of chmod in Numeric Mode

##### 1. Give the owner full permissions, and the group and others read-only:
   ```bash
   chmod 744 myfile.txt
   ```
   - **7** (rwx): Owner can read, write, and execute.
   - **4** (r--): Group can only read.
   - **4** (r--): Others can only read.

##### 2. Give the owner read and write permissions, and no permissions to the group and others:
   ```bash
   chmod 600 myfile.txt
   ```
   - **6** (rw-): Owner can read and write.
   - **0** (---): Group has no permissions.
   - **0** (---): Others have no permissions.

##### 3. Give everyone execute permission only:
   ```bash
   chmod 111 script.sh
   ```
   - **1** (--x): Owner can only execute.
   - **1** (--x): Group can only execute.
   - **1** (--x): Others can only execute.

##### 4. Set permissions for a shared script:
   ```bash
   chmod 775 shared_script.sh
   ```
   - **7** (rwx): Owner can read, write, and execute.
   - **7** (rwx): Group can read, write, and execute.
   - **5** (r-x): Others can read and execute, but not write.

##### 5. Make a file readable and writable by everyone:
   ```bash
   chmod 666 openfile.txt
   ```
   - **6** (rw-): Owner can read and write.
   - **6** (rw-): Group can read and write.
   - **6** (rw-): Others can read and write.

##### 6. Remove all permissions (lock a file):
   ```bash
   chmod 000 secretfile.txt
   ```
   - **0** (---): Owner, group, and others have no access.

#### Key Benefits of Numeric Mode
- **Precision**: Numeric mode explicitly defines all permissions at once.
- **Efficiency**: A single command can adjust permissions for all user categories.
- **Control**: You can quickly lock or open a file for specific users.

---

#### Common Octal Permissions

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
$ chmod 755 filename
```
**Set permissions to `700`**: Only the owner can read, write, and execute the file; others have no access.
```bash
chmod 700 confidential_file
```
**Set permissions to `644`**: The owner can read and write the file, while everyone else can only read it.
```bash
chmod 644 public_document
```

## Understanding Security Risks with Permissions

It's crucial to avoid overly permissive permissions, such as `777` and `666`. These allow anyone on the system to read, write, or execute the file, which poses significant security risks. Some of the potential issues include:

- **Accidental Changes**: If a file has `777` permissions, anyone on the system can modify it, which could lead to accidental changes.
- **Privilege Escalation**: Malicious users could modify a script or program, introduce harmful code, and cause it to execute when someone else runs the file.
- **Data Destruction**: With `777` or `666` permissions, malicious or careless users can delete or corrupt important data.

### Best Practice:
* Use appropriate permissions for different users and groups. 
* Limit access to sensitive files and make use of groups to provide controlled access. 
* Avoid using `777` or `666` permissions unless absolutely necessary. For example, if multiple users need write access, use groups and restrict permissions for others.

## Working with Groups and Special Modes

### Working with Groups

When multiple users need to access and modify a file, the `chgrp` command can be used to change the file's group ownership. This allows members of a group to share access to the file.

#### Example 1: Changing the Group Ownership of a File
If a file `sales.report` needs to be shared by a sales team, you can change the group ownership of the file to the `sales` group:

```bash
$ chgrp sales sales.report
```

#### Example 2: Setting Permissions for Group Access
To allow the members of the `sales` group to read and write the file, while others on the system should have read-only access, set the file permissions to `664`:

```bash
$ chmod 664 sales.report
```
This translates to:
- Owner: `rw-`
- Group: `rw-`
- Others: `r--`

If no access should be granted to users outside the `sales` group, set permissions to `660`:

```bash
$ chmod 660 sales.report
```
This means:
- Owner: `rw-`
- Group: `rw-`
- Others: `---`

#### Example 3: Sharing Files in a Common Directory
If you want all team members to access files from a common location, create a shared directory and set appropriate permissions. Assuming you have superuser privileges, create a directory `/usr/local/sales`:

```bash
mkdir /usr/local/sales
$ chgrp sales /usr/local/sales
$ chmod 770 /usr/local/sales
```

This gives full access to the sales team, while no access is granted to others. Permissions are:
- Owner: `rwx`
- Group: `rwx`
- Others: `---`

### Directory Permissions: An In-depth Explanation

Directory permissions are critical in controlling access to files and subdirectories within the directory. While file permissions dictate how a file can be read, written, or executed, directory permissions determine how the files and subdirectories inside it are accessed, listed, or modified.

#### Understanding Directory Permissions

The permissions for directories are interpreted differently compared to regular files. Here's what each permission means for a directory:

| **Permission** | **Effect on Directory** |
|----------------|-------------------------|
| `r` (read)     | Allows viewing the names of the files and subdirectories inside the directory (e.g., `ls` command).          |
| `w` (write)    | Allows creating, deleting, or renaming files and subdirectories within the directory.                        |
| `x` (execute)  | Allows entering the directory (e.g., `cd` command) and accessing files or subdirectories if permissions allow. |

---

#### **Permission Combinations for Directories**

| **Permissions** | **Effect** |
|-----------------|------------|
| `---`            | No access to the directory.|
| `--x`            | Allows entering the directory but not listing its contents (you must know file names explicitly to access).   |
| `r--`            | Allows viewing the directory's contents but not accessing files or entering the directory.                   |
| `r-x`            | Allows viewing and accessing files, but modifications (e.g., adding or deleting files) are not allowed.      |
| `rw-`            | Allows viewing and modifying the directory's contents but not entering it.|
| `rwx`            | Full access: viewing, modifying, and entering the directory.|

---

#### Examples of Directory Permissions in Action

##### 1. Checking Directory Permissions

Use `ls -ld` to view the permissions of a directory:
```bash
ls -ld directory/
drwxr-xr-x 2 sri users 4096 Sep 29 22:02 directory/
```

- `drwxr-xr-x`: 
  - `d`: Indicates it's a directory.
  - `rwx` (user): The owner can read, write, and execute (full control).
  - `r-x` (group): Group members can read and execute but not write.
  - `r-x` (others): Others can read and execute but not write.

Use `ls -l` to view the contents and their permissions:
```bash
ls -l directory/
-rwxr--r-- 1 sri users 0 Sep 29 22:02 testprog
```

---

##### 2. Removing Read and Execute Permissions

If you remove read (`r`) and execute (`x`) permissions for the directory, access to its contents becomes restricted:
```bash
chmod 300 directory/
ls -ld directory/
d-wx------ 2 sri users 4096 Sep 29 22:02 directory/
```

- The owner can write to the directory (e.g., delete files) but cannot list its contents or enter it.

Trying to list the contents will fail:
```bash
ls directory/
ls: cannot open directory: Permission denied
```

---

##### **3. Restricting Access with No Execute Permission

When the execute (`x`) permission is missing:
```bash
chmod 600 directory/
ls -ld directory/
drw------- 2 sri users 4096 Sep 29 22:02 directory/
```

- **Read-only without execute:** You can view the directory contents but cannot enter it or access individual files:
  ```bash
  ls directory/
  file1 file2 file3
  cd directory/
  bash: cd: directory: Permission denied
  ```

---

##### 4. Changing Permissions to Grant Access

To allow viewing and accessing the directory contents, you need to grant both read (`r`) and execute (`x`) permissions:
```bash
chmod 500 directory/
ls -ld directory/
dr-x------ 2 sri users 4096 Sep 29 22:02 directory/
```

- The owner can now list (`ls`) and access (`cd`) the directory but cannot modify its contents.

---

### **Examples of Specific Directory Permission Scenarios**

#### **Scenario 1: A Public Directory**
To make a directory accessible to everyone without allowing modifications:
```bash
chmod 755 public/
ls -ld public/
drwxr-xr-x 2 sri users 4096 Sep 29 22:02 public/
```
- **Owner**: Full control (read, write, execute).
- **Group and Others**: Can read and execute but not write.

---

#### **Scenario 2: A Private Directory**
To make a directory private to the owner:
```bash
chmod 700 private/
ls -ld private/
drwx------ 2 sri users 4096 Sep 29 22:02 private/
```
- Only the owner can list, modify, and access the directory.

---

#### **Scenario 3: Locking a Directory**
To lock a directory completely:
```bash
chmod 000 locked/
ls -ld locked/
d--------- 2 sri users 4096 Sep 29 22:02 locked/
```
- No one, including the owner, can list, access, or modify the directory without changing its permissions.

---

### **Common Commands for Managing Directory Permissions**

1. **Grant execute permission for the owner:**
   ```bash
   chmod u+x directory/
   ```

2. **Remove write permission for group and others:**
   ```bash
   chmod go-w directory/
   ```

3. **Set permissions to read-only for all users:**
   ```bash
   chmod 555 directory/
   ```

4. **Restore full permissions for the owner and restrict others:**
   ```bash
   chmod 700 directory/
   ```

---

### **Important Notes**
- **Removing execute permission** prevents entering the directory even if read permission is granted.
- **Removing write permission** prevents modifications to the directory but allows viewing or accessing files.
- Always carefully manage directory permissions to avoid accidentally locking yourself out of important directories.

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
$ chmod 4755 /usr/bin/passwd
```
This enables `setuid` for the `passwd` command, allowing it to run with superuser privileges.

#### Setgid (Set Group ID)
The `setgid` permission allows a program to run with the group of the file instead of the executing user's group. Additionally, when `setgid` is used on a directory, all files created within that directory inherit the directory’s group.

To enable `setgid`:
- Octal mode: Prepend `2`
- Symbolic mode: Use `g+s`

#### Example 10: Setting Setgid
```bash
$ chmod 2755 /usr/bin/locate
```
This enables `setgid` on the `locate` command.

#### Example 11: Setting Setgid on a Directory
```bash
$ chmod 2770 /usr/local/sales
```
This ensures that all new files created in `/usr/local/sales` will inherit the `sales` group.

#### Sticky Bit
The `sticky` bit prevents users from deleting files owned by others, even if they have write access to the directory. This is typically used in shared directories like `/tmp` to prevent file deletion by unauthorized users.

To enable the sticky bit:
- Octal mode: Prepend `1`
- Symbolic mode: Use `+t`

#### Example 12: Setting the Sticky Bit
```bash
$ chmod 1777 /tmp
```
This allows everyone to write to `/tmp`, but only the owner of a file can delete it.

## Summary of Permissions Commands


| **Command**      | **Description**                                                  | **Example**                                                 |
|------------------|------------------------------------------------------------------|-------------------------------------------------------------|
| `ls -l`          | Lists files with detailed information, including permissions.    | `ls -l myfile.txt`                                           |
| `chmod`          | Changes file permissions.                                        | `chmod u+x myscript.sh`                                      |
| `groups`         | Displays the groups a user belongs to.                           | `groups`                                                    |
| `id -Gn`         | Shows the list of groups for a specific user.                    | `id -Gn john`                                               |
| `ls -l` (example)| Displays detailed file listing with permissions for `sales.data`.| `-rw-r--r-- 1 sri users 10400 Jun 14 09:31 sales.data`      |
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
| `<space>`| Display next k lines of text (current screen size)            |
| `z`| Display next k lines of text (current screen size)            |
| `<return>`| Display next k lines of text (1 line)                         |
| `d` or `ctrl-D`| Scroll k lines (current scroll size, initially 11)            |
| `q` or `Q` or `<interrupt>`  | Exit from more|
| `s`| Skip forward k lines of text (1 line)                         |
| `f`| Skip forward k screenfuls of text (1 screenful)               |
| `b` or `ctrl-B`| Skip backwards k screenfuls of text (1 screenful)             |
| `'`| Go to place where previous search started                     |
| `=`| Display current line number                                    |
| `/<regular expression>`      | Search for kth occurrence of regular expression (1 occurrence) |
| `n`| Search for kth occurrence of last regular expression (1 occurrence) |
| `!<cmd>` or `:!<cmd>`| Execute `<cmd>` in a subshell                                  |
| `v`                          | Start up '/usr/bin/vi' at current line|
| `ctrl-L`                     | Redraw screen|
| `:n`                         | Go to kth next file (1 file)|
| `:p`| Go to kth previous file (1 file)                               |
| `:f`| Display current file name and line number                      |
| `.`| Repeat previous command                                        |

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

Here’s a table summarizing the useful `less` commands:

| **Command**                  | **Description**                                                       |
|------------------------------|-----------------------------------------------------------------------|
| **Space** or **f**            | Move forward one screen.                                              |
| **b** or **Ctrl-B**           | Move backward one screen.                                             |
| **Enter** or **j**            | Move forward one line.                                                |
| **k**                         | Move backward one line.                                               |
| **g**                         | Go to the beginning of the file.                                      |
| **G**                         | Go to the end of the file.                                            |
| **<number>g**                 | Go to a specific line number (e.g., `50g` goes to line 50).           |
| **/pattern**                  | Search forward for the pattern.                                       |
| **?pattern**                  | Search backward for the pattern.                                      |
| **n**                         | Go to the next occurrence of the search pattern.                      |
| **N**                         | Go to the previous occurrence of the search pattern.                  |
| **/pattern[Enter]**           | Find the next match of the pattern.                                   |
| **?pattern[Enter]**           | Find the previous match of the pattern.                               |
| **{**                         | Jump to the previous search result.                                   |
| **}**                         | Jump to the next search result.                                       |
| **&pattern**                  | Show only the lines matching the given pattern.                       |
| **Ctrl-F**                    | Scroll forward by one screen.                                         |
| **Ctrl-B**                    | Scroll backward by one screen.                                        |
| **v**                         | Open the file in the `vi` editor at the current location.             |
| **=**                         | Display the current line number.                                      |
| **:f**                        | Show the current filename and line number.                            |
| **:p**                        | Display the previous file (when viewing multiple files).              |
| **:n**                        | Display the next file (when viewing multiple files).                  |
| **q** or **Ctrl-C**           | Exit `less`.                                                          |
| **Ctrl-D**                    | Scroll down half a screen.                                            |
| **Ctrl-U**                    | Scroll up half a screen.                                              |
| **h**                         | Show the help screen with all the commands.                           |
| **m**                         | Mark the current location.                                            |
| **`**                         | Jump back to the last marked location.                                |
| **s**                         | Sort the file (requires sorting support in `less`).                   |
  

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
| Install a `.deb` package| Install a `.deb` file.    | `sudo dpkg -i package.deb`|
| Fix broken dependencies| Fix unmet dependencies after installing a `.deb` package.    | `sudo apt install -f`|
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
Here’s a refined and well-structured version of the explanation for a better flow:

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
| **Action**                        | **Command** |
|------------------------------------|-------------|
| Move up one line                   | `k`         |
| Move down one line                 | `j`         |
| Move left one character            | `h`         |
| Move right one character           | `l`         |
| Move right one word                | `w`         |
| Move left one word                 | `b`         |
| Move to the beginning of the line  | `^`         |
| Move to the end of the line        | `$`         |
| Move to the beginning of the file  | `gg`        |
| Move to the end of the file        | `G`         |

**Examples**:
- Move 3 lines down: `3j`
- Go to the start of the file: `gg`
- Go to the end of the file: `G`

---

### 2. Insert Mode
Insert Mode allows you to input text directly into the file. You can enter Insert Mode from Command Mode using the following keys:
| **Action**                        | **Command** |
|------------------------------------|-------------|
| Insert at the current position     | `i`         |
| Insert at the beginning of the line | `I`        |
| Append after the current position  | `a`         |
| Append at the end of the line      | `A`         |

Once you’re done typing, press `Esc` to return to Command Mode.

**Examples**:
- Start typing at the current cursor: `i`
- Append text to the end of the line: `A`

---

### 3. Line Mode (Command Line Mode)
Line Mode is accessed by typing `:` in Command Mode. Here, you can execute commands for saving, quitting, searching, and more.

#### Common Commands in Line Mode:
| **Action**                        | **Command** |
|------------------------------------|-------------|
| Save the file                      | `:w`        |
| Quit the editor                    | `:q`        |
| Save and quit                      | `:wq` or `:x` |
| Quit without saving                | `:q!`       |
| Go to line `n`                     | `:n`        |
| Enable line numbers                | `:set nu`   |
| Disable line numbers               | `:set nonu` |
| Access help                        | `:help`     |

**Examples**:
- Save the file: `:w`
- Quit without saving changes: `:q!`
- Jump to line 20: `:20`
- Enable line numbering: `:set nu`

---

## Editing Commands in Command Mode

### 1. Deleting Text
| **Action**                        | **Command** |
|------------------------------------|-------------|
| Delete a character                 | `x`         |
| Delete a word                      | `dw`        |
| Delete a line                      | `dd`        |
| Delete from cursor to line end     | `D`         |

**Examples**:
- Delete a character: `x`
- Delete a word: `dw`
- Delete an entire line: `dd`

---

### 2. Changing Text
| **Action**                        | **Command** |
|------------------------------------|-------------|
| Replace the current character      | `r`         |
| Change the current word            | `cw`        |
| Change the current line            | `cc`        |
| Change to the line's end           | `c$`        |

**Examples**:
- Replace a character with `d`: `rd`
- Change a word: `cw`, then type the new word.

---

### 3. Copying and Pasting Text
Vim uses the `yank` command to copy and `p` to paste.
| **Action**                        | **Command** |
|------------------------------------|-------------|
| Yank the current line              | `yy`        |
| Yank a word                        | `yw`        |
| Paste the yanked text              | `p`         |

**Examples**:
- Yank a line: `yy`
- Paste it below the current line: `p`

---

### 4. Undo and Redo
| **Action**                        | **Command** |
|------------------------------------|-------------|
| Undo the last change               | `u`         |
| Redo the last undone change        | `Ctrl + r`  |

**Examples**:
- Undo: `u`
- Redo: `Ctrl + r`

---

### 5. Searching in Vim
Search for patterns in the text efficiently.
| **Action**                        | **Command** |
|------------------------------------|-------------|
| Search forward for a pattern       | `/pattern`  |
| Search backward for a pattern      | `?pattern`  |
| Move to the next occurrence        | `n`         |
| Move to the previous occurrence    | `N`         |

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
| **Action**                        | **Command** |
|------------------------------------|-------------|
| Toggle case of the current character | `~`         |

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

| **Command**                           | **Description**                                                                                     | **Example**                                                                                     |
|---------------------------------------|-----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| `rm file`                             | Remove a file.                                                                                      | `rm test.txt` - Removes `test.txt`.                                                            |
| `rm -r file_or_directory`             | Remove a directory or file recursively, including its contents.                                     | `rm -r my_folder` - Removes the `my_folder` directory and all its contents.                   |
| `rm -rf file_or_directory`            | Forcefully remove a directory or file recursively without confirmation.                             | `rm -rf temp_folder` - Forces removal of `temp_folder` and its contents without prompts.       |
| `chmod 444 write_protected_file`      | Make a file write-protected (read-only for all users).                                              | `chmod 444 my_file` - Makes `my_file` read-only.                                               |
| `rm *.txt`                            | Use a wildcard to remove all `.txt` files in the current directory.                                 | `rm *.txt` - Deletes all `.txt` files.                                                         |
| `rm * -r`                             | Remove all files and directories recursively in the current directory.                              | `rm * -r` - Deletes everything in the current directory recursively.                           |
| `rm file?.txt`                        | Remove files matching a single-character wildcard pattern.                                          | `rm file?.txt` - Deletes files like `file1.txt`, `file2.txt`, but not `file10.txt`.            |
| `rm .hidden_file_pattern`             | Remove hidden files matching a specific pattern.                                                    | `rm .myhiddenfile` - Removes the hidden file `.myhiddenfile`.                                  |
| `rm .*.txt`                           | Remove hidden files with a `.txt` extension.                                                        | `rm .*.txt` - Deletes hidden `.txt` files.                                                     |
| `cp source_file destination_file_directory` | Copy a file to a specific directory.                                                               | `cp report.pdf /documents/` - Copies `report.pdf` to the `/documents/` directory.              |
| `cp source_file1 [source_fileN ...] destination_directory` | Copy multiple files to a directory.                                                               | `cp file1.txt file2.txt /backup/` - Copies `file1.txt` and `file2.txt` to `/backup/`.          |
| `cp -i source_file destination_directory` | Copy a file interactively, prompting before overwriting.                                           | `cp -i file1.txt /backup/` - Asks for confirmation before overwriting files in `/backup/`.     |
| `cp -r source_directory destination_directory` | Recursively copy a directory and its contents.                                                    | `cp -r project_folder /backup/` - Copies `project_folder` and its contents to `/backup/`.      |
| `mv source destination`               | Move a file or directory to a new location.                                                        | `mv file.txt /home/user/documents/` - Moves `file.txt` to `/home/user/documents/`.             |
| `mv old_name new_name`                | Rename a file or directory.                                                                        | `mv old_project new_project` - Renames `old_project` to `new_project`.                         |
| `mv -i source destination`            | Move a file or directory interactively, prompting before overwriting.                              | `mv -i file.txt /home/user/documents/` - Prompts before overwriting an existing file.          |

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

| **Command**                                   | **Description**                                    | **Option**       | **Example**                                                                 |
|-----------------------------------------------|---------------------------------------------------|------------------|-----------------------------------------------------------------------------|
| `sort file`                                   | Sorts the contents of a file **line by line**     | `file`           | `sort table.txt` - Sorts all rows in `table.txt` by their first column.     |
| `sort -k FIELD_NUM`                           | Sorts by a specific field/column                 | `-k FIELD_NUM`   | `sort -k 2 table.txt` - Sorts `table.txt` by the second column.             |
| `sort -r`                                     | Sorts in reverse order                           | `-r`             | `sort -r table.txt` - Sorts `table.txt` by the first column in descending order. |
| `sort -u`                                     | Sorts uniquely (removing duplicates)             | `-u`             | `sort -u table.txt` - Removes duplicate rows while sorting `table.txt`.     |

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
sort: invalid number at field start: invalid count at start of ‘r’
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

| **Command**                                   | **Description**                                                              | **Example**                                                                 |
|-----------------------------------------------|------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| `find [path...] [options] [expression]`       | General syntax of the `find` command.                                         | `find . -name "*.txt"` - Finds all `.txt` files in the current directory.  |
| `find . -name name_pattern`                   | Find files by name (case-sensitive).                                          | `find . -name "*.txt"` - Finds files named with a `.txt` extension.        |
| `find . -iname name_pattern`                  | Find files by name (case-insensitive).                                       | `find . -iname "*.jpg"` - Finds files named with a `.jpg` extension.       |
| `find ~ -name name_pattern -ls`               | Find files by name and list their details.                                    | `find ~ -name "*.pdf" -ls` - Lists details for `.pdf` files in home directory. |
| `find . -mtime [+-]number_of_days`            | Find files modified within a specific number of days.                         | `find . -mtime -7` - Finds files modified in the last 7 days.              |
| `find . -size [+-]size`                       | Find files by size (e.g., +10M for files larger than 10MB).                   | `find . -size +10M` - Finds files larger than 10MB.                         |
| `find . -newer file_or_directory`             | Find files that are newer than a specific file or directory.                 | `find . -newer reference.txt` - Finds files modified after `reference.txt`. |
| `find . -name name_pattern -exec some_commands {} \;` | Execute a command on each found item.                                        | `find . -name "*.log" -exec rm {} \;` - Deletes all `.log` files.          |
| `find ~ -name bfile -mtime -1 -exec cat {} \;` | Combine `find` options: find files modified in the last day and display their content. | `find ~ -name "*.txt" -mtime -1 -exec cat {} \;` - Displays contents of `.txt` files modified in the last day. |
| `locate pattern`                              | Locate files by pattern using an indexed database.                           | `locate myfile.txt` - Locates `myfile.txt` using the database.             |
| `sort file`                                   | Sort the contents of a file line by line.                                     | `sort table.txt` - Sorts rows in `table.txt` by the first column.          |
| `sort -n file`                                | Sort the contents of a file numerically.                                     | `sort -n table.txt` - Sorts rows in `table.txt` numerically by the first column. |
| `sort -k column_number file`                  | Sort by a specific column.                                                   | `sort -k 2 table.txt` - Sorts `table.txt` by the second column.            |
| `sort -r table.txt`                           | Sort the contents of a file in reverse order.                                | `sort -r table.txt` - Sorts `table.txt` in reverse order.                  |
| `sort [-k number]+ filename`                  | Sort based on a specific column or columns.                                  | `sort -k 2 -k 3 table.txt` - Sorts by column 2, then column 3.             |
| `sort -n -u file_name`                        | Sort uniquely by numeric order (removes duplicates).                         | `sort -n -u table.txt` - Removes duplicate rows while sorting numerically. |
| `sort -n -k 2 -u table.txt`                   | Sort uniquely based on column 2 (numeric).                                   | `sort -n -k 2 -u table.txt` - Sorts `table.txt` uniquely by the second column. |
| `diff file_or_dir file_or_dir`                | Compare two files or directories line by line.                               | `diff file1.txt file2.txt` - Shows the differences between `file1.txt` and `file2.txt`. |
| `sdiff file_or_dir file_or_dir`               | Side-by-side comparison of files or directories.                             | `sdiff file1.txt file2.txt` - Displays a side-by-side comparison of the two files. |
| `vimdiff file1 file2`                         | Compare two files using `vimdiff` in Vim editor.                             | `vimdiff file1.txt file2.txt` - Opens a side-by-side diff view of `file1.txt` and `file2.txt`. |

---

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
  (Now, type the text you want to sort. **Press `Ctrl-d` to indicate EOF**, and the text will be sorted).

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
The above command has got three parts: 
1. `command` - when run, will generate errors or outputs. 
2. `> output.log` - tells that standard output to be redirected to file.
   * `> output.log` is equivalent to `1> output.log`
3. `2>&1`- tells that standard output to be redirected to `&1` **reference of 1**, which is `output.log`.


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
   This reads input from `test.txt` and sorts it, saving the sorted output to `sorted.txt`.   sort < test.txt > sorted.txt


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
   
   Again it's **not one continuous redirection**, command to output to error! Each of these are independent.

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
| **Sort the contents of a file**                              | `sort < file.txt`      | `<`               | Uses the contents of `file.txt` as input and outputs the sorted content.        |
| **Sort and save output to a file**                           | `sort < test.txt > sorted.txt` | `<` `>`         | Uses `test.txt` as input and saves the sorted output to `sorted.txt`.          |
| **Find and save matches from a file**                        | `cat file.txt | grep "search term" > result.txt` | `>` `|` | Searches `file.txt` for "search term" and saves matching lines to `result.txt`. |
| **Redirect standard output and error to separate files**     | `command > output.txt 2> error.txt` | `>` `2>`     | Saves standard output to `output.txt` and standard error to `error.txt`.       |
| **Combine standard output and error into one file**          | `command > combined-output.txt 2>&1` | `>` `2>&1` | Saves both standard output and standard error to `combined-output.txt`.        |
| **Pipe output of one command to another**                    | `cat file.txt | sort`  | `|`               | Redirects the output of `cat file.txt` to `sort` as its input.                  |


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

---

# Processes and Jobs 

## Processes

### What is a Process?  

A **process** is a program that is being executed by the operating system. It has a unique **process ID (PID)** and represents the actual execution of code in the system. Processes are managed by the Linux kernel, not the shell. While each job corresponds to one or more processes, not all processes are jobs.  

For example, system processes like `systemd` or `cron` are started by the operating system and are not initiated by the shell, so they aren’t considered jobs.  

The `ps` command gives information about currently running processes. Other commands to monitor and manage processes are `top`, `htop`, and `pstree` .

---

## The `ps` Command

The `ps` (**process status**) command provides a snapshot of the currently running processes on your system. By default, `ps` shows processes associated with your current terminal session.

```bash
# Syntax
$ ps

# Example
$ ps
  PID TTY          TIME CMD
 3264 pts/0    00:00:00 bash
23102 pts/0    00:00:00 ps
```
* **`pts/0`** means, ***pseudo terminal 0***, which denotes a terminal session. 
* Open a new terminal tab and type the command `ps` again. 
  ```bash
  $ ps
      PID TTY          TIME CMD
    27301 pts/1    00:00:00 bash
    27308 pts/1    00:00:00 ps  
  ```
  * We have `pts/1` here, because this is a new terminal session. 

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

### Commonly Used `ps` Commands

| **Command**          | **Description**                                                 |
|------------------|-------------------------------------------------------------|
| ps -e           | Display all processes.                                       |
| ps -ef          | Display all processes using a full format listing.           |
| ps -eH          | Display all processes in a tree format.                      |
| ps -e --forest  | Display all processes in a tree format with ASCII art.       |
| ps -u <username> | Display processes running for username.                     |
| ps -fp <PID>    | Display a full-format listing for process ID (PID).          |


#### Display every process running on the system:
To see all processes running on the system, regardless of the user or terminal, use:
```bash
# Syntax
$ ps -e

# Example
$ ps -e
  PID TTY          TIME CMD
    1 ?        00:00:03 systemd
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
$ ps -e

# Example
$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 05:02 ?        00:00:03 /sbin/init splash
root           2       0  0 05:02 ?        00:00:00 [kthreadd]
root           3       2  0 05:02 ?        00:00:00 [pool_workqueue_release]
root           4       2  0 05:02 ?        00:00:00 [kworker/R-rcu_g]
root           5       2  0 05:02 ?        00:00:00 [kworker/R-rcu_p]
root           6       2  0 05:02 ?        00:00:00 [kworker/R-slub_]
root           7       2  0 05:02 ?        00:00:00 [kworker/R-netns]
...

```

#### Display all running processes for your user:
To display all processes running under your username, use the following command:
```bash
# Syntax
$ ps -u username

# Example
$ ps -u sri
  PID TTY          TIME CMD
 2189 ?        00:00:07 systemd
 2194 ?        00:00:00 (sd-pam)
 2209 ?        00:00:05 pipewire
 2210 ?        00:00:00 pipewire
 2214 ?        00:00:00 wireplumber
 2216 ?        00:00:06 pipewire-pulse
 2218 ?        00:00:00 gnome-keyring-d
```

#### Display information for a specific process ID (PID):
```bash
# Syntax
$ ps -p <pid>

# Example
$ ps -p 10
    PID TTY          TIME CMD
     10 ?        00:00:00 kworker/0:0H-events_highpri

$ ps -pf 10
error: process ID list syntax error

Usage:
 ps [options]

 Try 'ps --help <simple|list|output|threads|misc|all>'
  or 'ps --help <s|l|o|t|m|a>'
 for additional help text.

For more details see ps(1).

$ ps -fp 10
UID          PID    PPID  C STIME TTY          TIME CMD
root          10       2  0 05:02 ?        00:00:00 [kworker/0:0H-events_highpri]
```

#### Display processes in a hierarchical (tree) format:
```bash
# Syntax
$ ps -eH

# Example
$ ps -Hu sri
    PID TTY          TIME CMD
   2291 tty2     00:00:00 gdm-wayland-ses
   2300 tty2     00:00:00   gnome-session-b
   2189 ?        00:00:07 systemd
   2194 ?        00:00:00   (sd-pam)
   2209 ?        00:00:05   pipewire
   2210 ?        00:00:00   pipewire
   2214 ?        00:00:00   wireplumber
   2216 ?        00:00:06   pipewire-pulse
   2218 ?        00:00:01   gnome-keyring-d
   7802 ?        00:00:00     ssh-agent
   2225 ?        00:00:10   dbus-daemon

```

#### Display all processes in a tree format with ASCII art:
```bash
# Syntax
ps -e --forest

# Example
$ ps -u sri --forest
    PID TTY          TIME CMD
   2291 tty2     00:00:00 gdm-wayland-ses
   2300 tty2     00:00:00  \_ gnome-session-b
   2189 ?        00:00:07 systemd
   2194 ?        00:00:00  \_ (sd-pam)
   2209 ?        00:00:05  \_ pipewire
   2210 ?        00:00:00  \_ pipewire
   2214 ?        00:00:00  \_ wireplumber
   2216 ?        00:00:06  \_ pipewire-pulse
   2218 ?        00:00:01  \_ gnome-keyring-d
   7802 ?        00:00:00  |   \_ ssh-agent
   2225 ?        00:00:10  \_ dbus-daemon
   2257 ?        00:00:00  \_ xdg-document-po
   2261 ?        00:00:00  \_ xdg-permission-
   2386 ?        00:00:00  \_ gcr-ssh-agent
   2391 ?        00:00:00  \_ gnome-session-c
   2413 ?        00:00:00  \_ gvfsd
   3209 ?        00:00:00  |   \_ gvfsd-trash
   3365 ?        00:00:00  |   \_ gvfsd-recent
   3759 ?        00:00:00  |   \_ gvfsd-http
   7720 ?        00:00:00  |   \_ gvfsd-network
   7732 ?        00:00:00  |   \_ gvfsd-smb-brows
   7741 ?        00:00:00  |   \_ gvfsd-dnssd
   2422 ?        00:00:00  \_ gvfsd-fuse
```

## `pstree` Command

The `pstree` command is another tool that displays running processes in a tree-like format. It is similar to the `ps -H` or `ps --forest` command options but with a more visually structured output. Unlike `ps`, `pstree` **provides a continuous, updated process tree.**

To use `pstree`:
```bash
# Syntax
$ pstree

# Example
$ pstree -u sri
gdm-wayland-ses─┬─gnome-session-b───3*[{gnome-session-b}]
                └─3*[{gdm-wayland-ses}]

systemd─┬─(sd-pam)
        ├─at-spi2-registr───3*[{at-spi2-registr}]
        ├─chrome_crashpad───2*[{chrome_crashpad}]
        ├─code─┬─code
        │      ├─code─┬─code───15*[{code}]
        │      │      └─code───11*[{code}]
        │      ├─code───8*[{code}]
        │      ├─2*[code───15*[{code}]]
        │      ├─code─┬─code───7*[{code}]
        │      │      └─15*[{code}]
        │      ├─code───17*[{code}]
        │      └─36*[{code}]
        ├─dbus-daemon
        ├─dconf-service───3*[{dconf-service}]
        ├─evolution-addre───6*[{evolution-addre}]
        ├─evolution-calen───9*[{evolution-calen}]
        ├─evolution-sourc───4*[{evolution-sourc}]
        ├─gcr-ssh-agent───2*[{gcr-ssh-agent}]
```

## Real-Time Process Monitoring with `top` and `htop`

While `ps` gives a snapshot of processes at a specific moment, `top` and `htop` display processes in real-time, refreshing periodically.

---

### The `top` Command

`top` is a command-line utility that provides an overview of the system's performance and real-time process monitoring.

#### Basic usage of `top`:
```bash
$ top
```
This displays a continuously updating list of processes sorted by CPU usage by default.

#### Interactive Options in `top`:
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

In Linux, a **job** is a shell-level abstraction for managing tasks initiated in the terminal, while a **process** is a broader system-level concept representing any program running on the system. Jobs are specific to the shell and are identified by job IDs, whereas processes are independent of the shell and are identified by PIDs.

| **Aspect**            | **Job**                                | **Process**                            |  
|------------------------|----------------------------------------|----------------------------------------|  
| **Scope**             | Managed by the shell.                  | Managed by the Linux kernel.           |  
| **Identifier**         | Identified by a **job ID** (e.g., `[1]`). | Identified by a **process ID (PID)**. |  
| **Creation**          | Created when a command is run in the shell. | Created by the operating system for any executed program. |  
| **Context**           | Tied to the shell session.             | Independent of the shell (can exist outside of a shell). |  
| **Examples**          | Background commands (`sleep 10 &`).    | System processes (`cron`, `systemd`).  |  

---

### Running Jobs in the Background

When you start a command in the background, **the terminal immediately returns the prompt**, allowing you to continue executing other commands. To start a command in the background, you **append an ampersand (`&`)** to the command:

```bash
# Syntax
$ command &

# Example
$ sleep 30 &
[1] 25837
```
The `sleep` command makes the shell idle for given period of time. In the above example, the `sleep 30` command will run in the background for 30 seconds while you are free to use the terminal for other tasks.

When a command runs in the background, two pieces of information are displayed: the **job number** and the **process ID (PID)**. The job number is enclosed in square brackets, and the PID is shown next to it. In the example, `1` is the job number, and `25837` is the process ID of the background job.

#### When Does the Output of a Background Job Appear?

The shell ensures that background job output doesn't interrupt your work at the command prompt. It only displays the output when a new prompt appears, keeping the session organized. The `jobs` command will show job statuses just before the prompt is displayed. 

To check job status, press the **Enter** key. If any jobs are completed, their statuses will be shown before the new prompt.

### Job Control Table

| **Description**                                   | **Command**          |
|---------------------------------------------------|----------------------|
| Start command in the background                   | `command &`          |
| Kill the foreground process                       | `Ctrl-C`             |
| Suspend(pause) the foreground process             | `Ctrl-Z`             |
| Background most recent suspended process          | `bg`                 |
| Background a suspended process                    | `bg [%num]`          |
| Foreground most recent backgrounded process       | `fg`                 |
| Foreground a backgrounded process                 | `fg [%num]`          |
| Kill a process by job number or PID               | `kill [%num]` or `kill <PID>` |
| List all jobs or a specific job by job number     | `jobs [%num]`        |
| List all the jobs with process id                 | `jobs -l`            |

### Job Status

The `jobs` command lists all the jobs running in the background or suspended. The job numbers are displayed in square brackets. Jobs that are running or stopped are listed with their status.

Example output:
```bash
# Syntax
$ jobs

# Example
$ jobs
[1]+  12345 Running                 sleep 30 &
[2]-  12346 Stopped                 nano

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
fg %<job_number>
fg %%
fg %+
# bring the most recent bg job to fg
fg

# Examples
$ sleep 30 &
[1] 26056
$ fg %1
sleep 30

$ sleep 30 &
[1] 26056
$ fg %%
sleep 30

$ sleep 30 &
[1] 26056
$ fg %+
sleep 30

# bring the most recent bg to fg
$ sleep 30 &
[1] 26056
$ fg
sleep 30

```

### Backgrounding a Suspended Job

If a job is suspended (e.g., using `Ctrl-Z`), you can **resume** it in the background by using the `bg` command followed by the job number.

```bash
# Syntax
$ bg %1

# Example
$ sleep 10
^Z
[1]+  Stopped                 sleep 10
$ bg %1
[1]+ sleep 10 &
$ 
[1]+  Done                    sleep 10
$ 
```

If you want to resume the most recently suspended job in the background, simply use `bg` without specifying the job number:

```bash
# Syntax
$ bg

# Example
$ sleep 10
^Z
[1]+  Stopped                 sleep 10
$ bg
[1]+ sleep 10 &
$ 
[1]+  Done                    sleep 10

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
kill %<job_number>

# Example
$ sleep 100000 &
[1] 26558
$ kill %1
$
```

To kill a job by its **PID**:
```bash
# Syntax
kill <process_id>

# Example
$ sleep 100000 &
[2] 26580
[1]   Terminated              sleep 100000
$ kill 26580
$ ps
    PID TTY          TIME CMD
   3264 pts/0    00:00:00 bash
  26581 pts/0    00:00:00 ps
[2]+  Terminated              sleep 100000
$ jobs
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

| **Command**                              | **Description**                                                                 | **Example**                                               |
|------------------------------------------|---------------------------------------------------------------------------------|-----------------------------------------------------------|
| `ps`                                     | Lists running processes on the system.                                          | `ps`                                                      |
| `ps -e`                                  | Displays all processes running on the system.                                   | `ps -e`                                                   |
| `ps -ef`                                 | Displays all processes with a full format listing.                              | `ps -ef`                                                  |
| `ps -eH`                                 | Displays processes in a hierarchical (tree) format.                             | `ps -eH`                                                  |
| `ps -e --forest`                         | Displays processes in a tree format using ASCII art.                            | `ps -e --forest`                                          |
| `ps -u <username>`                       | Displays processes running for a specific user.                                 | `ps -u john`                                              |
| `ps -p <PID>`                            | Displays information for a specific process ID (PID).                           | `ps -p 1234`                                              |
| `pstree`                                 | Displays processes in a hierarchical tree format.                               | `pstree`                                                  |
| `top`                                    | Displays a real-time process list with system performance information.          | `top`                                                     |
| `htop`                                   | Interactive and improved version of `top` with a user-friendly interface.       | `htop`                                                    |
| `sudo apt install htop`                  | Installs `htop` on a Debian-based system.                                       | `sudo apt install htop`                                   |
| `kill <PID>`                             | Terminates a running process using its process ID (PID).                        | `kill 5678`                                               |
| `command &`                              | Starts a command in the background.                                             | `sleep 60 &`                                              |
| `Ctrl-C`                                 | Kills the foreground process.                                                  | (Press `Ctrl-C` while the job is in the foreground)       |
| `Ctrl-Z`                                 | Suspends the foreground process.                                               | (Press `Ctrl-Z` while the job is running)                 |
| `bg [%num]`                              | Resumes a suspended job in the background.                                      | `bg %1`                                                   |
| `bg`                                     | Resumes the most recently suspended job in the background.                      | `bg`                                                      |
| `fg [%num]`                              | Brings a backgrounded job to the foreground.                                    | `fg %1`                                                   |
| `fg`                                     | Brings the most recent background job to the foreground.                        | `fg`                                                      |
| `kill [%num]` or `kill <PID>`            | Kills a job by job number or PID.                                               | `kill %1` or `kill 12345`                                 |
| `jobs` or `jobs [%num]`                  | Lists all jobs or a specific job by job number.                                 | `jobs` or `jobs %1`                                       |
| `kill -l`                                | Lists available signals.                                                        | `kill -l`                                                 |
| `kill -<signal> %num` or `kill -<signal> <PID>` | Sends a specific signal to a job.                                              | `kill -9 %1` or `kill -9 12345`                           |
| `kill -9`                                | Force kills a job using the SIGKILL signal.                                     | `kill -9 %1`                                              |

---

# Switching Users

In Linux, switching between users or performing administrative tasks requires specific commands: `su` (Switch User) and `sudo` (Super User Do).

## Switching Users with `su` (Switch User)

The `su` command is used to switch between users in a Linux system. By default, `su` switches to the superuser (root). You can also use `su` to switch to any specific user by providing their username as an argument.

### Common `su` Usage

#### **Switch to Root**:  
The `su` command without any arguments switches to the root user.
```bash
sri@envy:~/Documents/Linux
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

#### **Switch to a Specific User**:  
To switch to a specific user, use the command `su [username]`. Enter the **switching user**'s password and not current user's password. 

In the below example you will have to enter switching user, `ram`'s passowrd. 
```bash
sri@envy:~/Documents/Linux
$ su ram
Password: 
ram@envy:/home/sri/Documents/Linux$ 
```
Also notice that you are still the same directory as before. 

To quit from this user (`ram`) account: 
```bash
ram@envy:/home/sri/Documents/Linux$ exit
exit
sri@envy:~/Documents/Linux
$ 
```
  
Another way of logging to another user is through `sudo su [username]`, use the **current user**'s password. If the current user is in sudoers group, they will be able to login to another user's account.

In the below example you will have to enter current user, `sri`'s password. 
```bash
sri@envy:~/Documents/Linux
$ sudo su ram
[sudo] password for sri: 
ram@envy:/home/sri/Documents/Linux$ 
  ```

#### **Simulate Logging In as a User**:  
By adding a hyphen (`-`), you simulate logging in directly as that user. This changes your environment variables and your working directory to the user’s home directory. **While the previous method don't change the working directory.** 
```bash
sri@envy:~/Documents/Linux
$ sudo su - ram
[sudo] password for sri: 
ram@envy:~$ 
```

#### **Excuting command as another user**: 
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

The `sudo` command allows a **permitted user** to execute a command as another user, typically the root user, without switching users entirely. It’s often used for administrative tasks, such as installing software or managing system services, that require superuser privileges.

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
| `su [user]`| Switch to the superuser (root) or another specified user.| `su` or `su ram`|
| `su - [user]`| Switch to the specified user with their environment (login shell).     | `su -` or `su - ram`|
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