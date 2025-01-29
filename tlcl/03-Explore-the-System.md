# Explore the System

## Table of Contents
- [Explore the System](#explore-the-system)
  - [Table of Contents](#table-of-contents)
  - [Linux Commands' Options and Arguments](#linux-commands-options-and-arguments)
  - [Fun with `ls`](#fun-with-ls)
    - [A table showing some important `ls` command options.](#a-table-showing-some-important-ls-command-options)
    - [A Longer Look at Long Format](#a-longer-look-at-long-format)
  - [Determining a File's Type with `file`](#determining-a-files-type-with-file)
  - [Viewing Text Files with `less`](#viewing-text-files-with-less)
    - [What is "Text"?](#what-is-text)
    - [Using the `less` Command](#using-the-less-command)
    - [Here are some frequently used `less` commands:](#here-are-some-frequently-used-less-commands)
    - [Less Is More](#less-is-more)
  - [Touring Linux File System](#touring-linux-file-system)
    - [A list some well known directories:](#a-list-some-well-known-directories)
  - [Symbolic Links](#symbolic-links)
  - [Summary](#summary)

## Linux Commands' Options and Arguments

- **Command Structure**: Most commands follow the format `command -options arguments`.  
- **Options**: Modify the behavior of the command.  
- **Arguments**: The items upon which the command acts.  
- **Short Options**: Single-character options preceded by a dash (e.g., `-l`).  
- **Long Options**: Full-word options preceded by two dashes (e.g., `--reverse`).  
- **Multiple Short Options**: Can be combined (e.g., `ls -lt`).  
- **Example Usage**: `ls -lt` lists files in long format sorted by modification time.  
- **Long Option Example**: `ls -lt --reverse` reverses the order of the sort.  
- **Case Sensitivity**: Options are case-sensitive in Linux.

## Fun with `ls` 

- **`ls` Command Overview**: Probably the most frequently used Linux command.  
- **Basic Usage**: Running `ls` without arguments lists files and subdirectories in the current working directory.  
- **Listing a Specific Directory**: Use `ls /directory_path` (e.g., `ls /usr`) to list the contents of a specified directory.  
- **Listing Multiple Directories**: Provide multiple directory paths (e.g., `ls ~ /usr`) to list contents of both.  
- **Long Format Output**: Use `ls -l` to display additional details such as permissions, ownership, size, and modification time.

### A table showing some important `ls` command options.
| Option | Long Option     | Description |
|--------|---------------|-------------|
| `-a`   | `--all`       | List all files, including hidden ones (files beginning with `.`). |
| `-A`   | `--almost-all` | Like `-a`, but excludes `.` (current directory) and `..` (parent directory). |
| `-d`   | `--directory`  | Lists details of the directory itself instead of its contents (use with `-l`). |
| `-F`   | `--classify`   | Appends an indicator character (e.g., `/` for directories). |
| `-h`   | `--human-readable` | Displays file sizes in human-readable format (e.g., KB, MB). |
| `-l`   |               | Displays results in long format. |
| `-r`   | `--reverse`    | Displays results in reverse order. |
| `-S`   |               | Sorts results by file size. |
| `-t`   |               | Sorts results by modification time. |

---

### A Longer Look at Long Format  

- Consider the following output of an `ls -l` command:  
  ```bash
  -rw-r--r-- 1 root root 32059 2017-04-03 11:05 oo-cd-cover.odf
  ```  

- This format provides a lot of useful information:  

  - **Access Rights (`-rw-r--r--`)**:  
    - First character: File type (`-` for a regular file, `d` for a directory).  
    - Next three (`rw-`): Owner's permissions (read, write, no execute).  
    - Next three (`r--`): Group permissions (read-only).  
    - Last three (`r--`): Permissions for others (read-only).  

  - **Number of Hard Links (`1`)**: Number of hard links to the file.  

  - **Owner (`root`)**: The username of the file’s owner.  

  - **Group (`root`)**: The group that owns the file.  

  - **Size (`32059` bytes)**: File size in bytes.  

  - **Modification Time (`2017-04-03 11:05`)**: Last modification date and time.  

  - **Filename (`oo-cd-cover.odf`)**: The name of the file.  

---

## Determining a File's Type with `file`

- The `file` command helps identify the type of data a file contains.  
- Unlike other systems, filenames in Linux do not necessarily indicate their contents.  
  - Example: A file named `picture.jpg` is expected to be a JPEG image, but it is not required to be.  
- **Usage:**  
  ```sh
  file filename
  ```  
- **Example:**  
  ```sh
  [me@linuxbox ~]$ file picture.jpg
  picture.jpg: JPEG image data, JFIF standard 1.01
  ```  
- The command outputs a brief description of the file’s contents.  
- Linux follows the principle that **"everything is a file,"** including text files, images, directories, and even devices.  
- While some file types are common (e.g., MP3, JPEG), Linux also contains many lesser-known or unusual file types.  

---

## Viewing Text Files with `less`  

- **`less` Command:** A program used to view text files in Linux.  

- **Why View Text Files?**  
  - Many system files contain **human-readable text**.  
  - **Configuration files** (which store system settings) are in text format.  
  - **Scripts** (actual programs used by the system) are also stored as text files.  
- **Benefits of Understanding Text Files:**  
  - Helps in understanding how the system works.  
  - Essential for modifying system settings and writing scripts (covered in later chapters).  
- **For Now:** We will focus on viewing files, not editing them.

---

### What is "Text"?

- Computers represent all data as numbers through various encoding systems.  
- Some data representations are complex (e.g., compressed video files), while others are simple.  
- **ASCII Text:**  
  - One of the earliest and simplest encoding schemes.  
  - **ASCII** stands for *American Standard Code for Information Interchange* (pronounced "As-Key").  
  - Originally used on Teletype machines to map keyboard characters to numbers.  
- **Characteristics of ASCII Text:**  
  - Uses a simple one-to-one mapping of characters to numbers.  
  - **Compact**: Each character corresponds to a single byte.  
  - **Plain Text vs. Word Processor Files:**  
    - Plain ASCII text contains only characters and simple control codes (tabs, carriage returns, line feeds).  
    - Word processor files (e.g., Microsoft Word, LibreOffice Writer) include formatting and structural data.  
- **Text in Linux:**  
  - Many Linux system files are stored in text format.  
  - Linux provides numerous tools for working with text files.  
- **Text in Windows:**  
  - Even Windows recognizes plain text’s importance (e.g., Notepad can edit plain ASCII text files).  

---

### Using the `less` Command  

- **Syntax:**  
  ```sh
  less filename
  ```  
- **Functionality:**  
  - Allows **scrolling forward and backward** through a text file.  
  - Useful for viewing long files without opening an editor.  
- **Example:** Viewing the system's user account definitions:  
  ```sh
  less /etc/passwd
  ```  

---

### Here are some frequently used `less` commands:

| Command       | Action                                      |
|--------------|---------------------------------------------|
| Page Up or `b` | Scroll back one page                     |
| Page Down or `space` | Scroll forward one page            |
| Up arrow     | Scroll up one line                         |
| Down arrow   | Scroll down one line                       |
| `G`          | Move to the end of the text file           |
| `1G` or `g`  | Move to the beginning of the text file     |
| `/characters` | Search forward to the next occurrence of characters |
| `n`          | Search for the next occurrence of the previous search |
| `h`          | Display help screen                        |
| `q`          | Quit `less`                                |

---

### Less Is More  

- **History:**  
  - The `less` program was designed as an improved replacement for the older Unix program **`more`**.  
  - The name **"less"** is a play on the phrase **"less is more,"** a motto associated with modernist architects and designers.  
- **Pager Program:**  
  - `less` is part of the class of programs called **"pagers"**.  
  - **Pagers** allow easy viewing of long text documents in a **page-by-page** manner.  
- **Features:**  
  - Unlike `more`, which could only scroll **forward**, `less` allows paging in **both directions** (forward and backward).  
  - `less` also offers **many other features** for better navigation and interaction with text files.  

---

## Touring Linux File System

- The **Linux file system layout** follows the **Linux Filesystem Hierarchy Standard**, though not all distributions fully adhere to it.  
- **Steps to Explore:**  
  1. **Change directory (`cd`)** into a given directory.  
  2. **List contents** with `ls -l`.  
  3. Use the **`file` command** to determine a file's contents.  
  4. If the file seems to be text, **view it with `less`**.  
  5. If a non-text file scrambles the terminal, use the **`reset` command** to recover.  
- **Notes:**  
  - Regular users are mostly restricted from damaging the system, so feel free to explore.  
  - **In Linux, there are no secrets**—the system is open to discovery.

---

### A list some well known directories: 
| Directory       | Comments                                                                 |
|-----------------|--------------------------------------------------------------------------|
| `/`             | The root directory, where everything begins.                             |
| `/bin`          | Contains binaries (programs) needed for booting and running the system.  |
| `/boot`         | Contains the Linux kernel, RAM disk image, and boot loader.              |
| `/dev`          | Contains device nodes. Devices are treated as files here.                |
| `/etc`          | Contains system-wide configuration files and startup scripts.            |
| `/home`         | Home directories for regular users. Users can write only in their own home directories. |
| `/lib`          | Contains shared libraries used by system programs (deprecated in favor of `/usr/lib`). |
| `/lost+found`   | Used for recovery of files after file system corruption.                 |
| `/media`        | Mount points for removable media like USB drives and CD-ROMs.           |
| `/mnt`          | Older directory for manually mounted devices.                           |
| `/opt`          | Directory for optional software, often used for commercial software.    |
| `/proc`         | A virtual file system with kernel and hardware information.              |
| `/root`         | Home directory for the root user.                                       |
| `/run`          | Replaces `/tmp`, stores temporary data in memory.                        |
| `/sbin`         | Contains system binaries, generally for superuser use.                   |
| `/sys`          | Contains detailed information about detected devices.                    |
| `/tmp`          | Stores temporary files created by programs.                             |
| `/usr`          | The largest directory, containing programs and support files for regular users. |
| `/usr/bin`      | Contains executable programs installed by the Linux distribution.       |
| `/usr/lib`      | Contains shared libraries for programs in `/usr/bin`.                   |
| `/usr/local`    | For programs not included in the distribution, usually compiled from source. |
| `/usr/sbin`     | Contains system administration programs.                                |
| `/usr/share`    | Contains shared data for programs, including configuration files, icons, etc. |
| `/usr/share/doc`| Contains documentation for installed packages.                          |
| `/var`          | Stores data that changes frequently (logs, databases, user mail, etc.). |
| `/var/log`      | Contains log files for system activity, which should be monitored.      |
| `~/.config`     | Stores user-specific configuration data for desktop applications.       |
| `~/.local`      | Stores user-specific data for desktop applications.                     |

---

## Symbolic Links

- **Symbolic Links** (also known as soft links or symlinks):
  - A file that points to another file, allowing multiple names for a file.
  - Example: `libc.so.6 -> libc-2.6.so`, meaning programs accessing `libc.so.6` actually access `libc-2.6.so`.
  - Useful for managing files with version changes (e.g., software dependencies).
  - Programs can rely on a common name (e.g., `foo`) while the actual file name can include version numbers (e.g., `foo-2.6`).
  - Easy to upgrade or revert versions by changing the symbolic link target, without modifying programs using it.
  - Allows multiple versions of a file to exist on the system while maintaining a consistent reference.
- Note, there is also something called **hardlinks**. 

---

## Summary

This chapter covered several important Linux commands and concepts, starting with the commonly used `ls` command for listing directory contents, with options like `-l` for long format and `-a` for showing hidden files. It explains how to examine file details, including permissions, ownership, and modification times. The `file` command helps determine the type of a file, while `less` is a pager for viewing text files in a scrollable format. The document also delves into the Linux file system structure, detailing key directories like `/bin`, `/usr`, and `/etc`. Lastly, symbolic links (soft links) are introduced as a way to reference files with multiple names, simplifying version management, and allowing for easy upgrades or reverts.

One imporant thing to note is, how open Linux is, unlike proprietory systems.

Take a look at: 
- `ls` command [options](#a-table-showing-some-important-ls-command-options).   
- `less` [commands](#here-are-some-frequently-used-less-commands)
- Common Linux [directories](#a-list-some-well-known-directories)

Here are the commands that we introduced here: 
| Command        | Description                                                  |
|----------------|--------------------------------------------------------------|
| `file filename` | Identifies the type of data contained in the specified file. |
| `less filename` | Views the contents of the specified text file in a paged format. |
