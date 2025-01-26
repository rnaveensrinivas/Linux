# Navigation

### Table of Content
- [Navigation](#navigation)
    - [Table of Content](#table-of-content)
    - [Understanding the file System Tree](#understanding-the-file-system-tree)
    - [The Current Working Directory](#the-current-working-directory)
    - [Changing the Current Working Directory](#changing-the-current-working-directory)
    - [Important Facts about Filenames](#important-facts-about-filenames)
    - [Summary](#summary)

---

### Understanding the file System Tree

- **Unix-like File System**: Organized in a hierarchical directory (folder in other OSes) structure.
- **Tree-like Pattern**: Directories contain files and other directories.
- **Root Directory**: The first (top most) directory in the file system, represented by `/`.
- **Subdirectories**: The root directory contains files and subdirectories, which may contain further files and subdirectories.
- **Single File System Tree**: Unlike Windows, Linux does not have separate file system trees for different storage devices.
- **Mounting Storage Devices**: Additional storage devices are attached (mounted, the correct term) to specific points on the file system tree.
- **System Administrator**: A person who manages and configures the file system structure and mounting of storage devices.

---

### The Current Working Directory

- **Current Working Directory**: We are always inside a single directory, called the current working directory.
- **Parent Directory**: The directory above the current one is called the parent directory.
- **Subdirectories**: The directories below the current directory are its subdirectories.
- **Displaying Current Directory**: To view the current directory, use the `$ pwd` (print working directory) command.
- **Home Directory**: When first logging in or starting a terminal, the default current working directory is the user's home directory (represented by `~`).
- **User Permissions**: Each user has their own home directory, and regular users can only write files in their respective home directories.
- **Listing Content of Directory**: To list the content of current directory (in fact any directory) use `ls` (list) command. 

---

### Changing the Current Working Directory

- To change the working directory, use the `cd` command followed by the pathname of the target directory.

- **Pathnames**:
  - **Absolute Pathnames**: Start from the root directory (`/`) and specify the full path to the target directory or file.
    - Example: `cd /usr/bin` changes the directory to `/usr/bin`.
  - **Relative Pathnames**: Start from the current working directory, not the root.
    - Use `.` (dot) to refer to the current directory.
    - Use `..` (dot dot) to refer to the parent directory.
  - There may be many ways to get to a directory using both Absolute and Relative pathnames, use the one which takes less typing.
- Here are some `cd` shortcuts.
    | Shortcut               | Result                                                                 |
    |------------------------|------------------------------------------------------------------------|
    | `cd`                   | Changes the working directory to your home directory.                 |
    | `cd -`                 | Changes the working directory to the previous working directory.      |
    | `cd ~user_name`        | Changes the working directory to the home directory of `user_name`. |

---

### Important Facts about Filenames

**Hidden Files**:
- Filenames that begin with a period (`.`) are hidden.
- Hidden files are not shown by default in `ls` but can be listed using `ls -a`.
- Examples: Configuration files in your home directory or application settings are often hidden.

**Case Sensitivity**:
- Filenames and commands in Linux are case-sensitive.
- For example, `File1` and `file1` are considered different files.

**No File Extensions**:
- Linux does not require file extensions like other operating systems.
- File contents or purpose are determined by other means, not by the file extension.
- Many applications may still use extensions but this is not a system requirement.

**Filename Best Practices**:
- Linux supports long filenames, including those with spaces and punctuation.
- It is recommended to limit punctuation to period (`.`), dash (`-`), and underscore (`_`).
- Avoid using spaces in filenames. Instead, use underscores (`_`) to separate words for better compatibility.

---

### Summary

This chapter explained how the shell treats the directory structure of the system. We learned about absolute and relative pathnames and the basic commands that we use to move about that structure. In the next chapter we will use this knowledge to go on a  tour of a modern Linux system.

**Summary of Commands**

| Command                        | Description                                                 |
|---------------------------------|-------------------------------------------------------------|
| `pwd`                           | Prints the current working directory.                       |
| `ls`                            | Lists the files and directories in the current directory.  |
| `ls -a`                         | Lists all files, including hidden files, in the directory. |
| `cd`                            | Changes the working directory to the home directory.        |
| `cd /`                          | Changes the working directory to the root directory.        |
| `cd ~`                          | Changes the working directory to the home directory.        |
| `cd ~username`                  | Changes the working directory to the home directory of `username`. |
| `cd -`                          | Changes the working directory to the previous directory.    |
| `cd .`                          | Stays in the current directory (refers to the current directory). |
| `cd ..`                         | Changes the working directory to the parent directory.      |
| `cd /home/username/absolute/path` | Changes the working directory to an absolute path.        |
| `cd ./relative/path`            | Changes the working directory using a relative path.        |
| `cd relative/path`              | Same as `cd ./relative/path`; `.` can be omitted.           |

---