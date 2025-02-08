### Table of Content
- [Manipulating Files and Directories](#manipulating-files-and-directories)
  - [Wildcards (Globbing)](#wildcards-globbing)
    - [Non-Exhaustive list of Wildcards](#non-exhaustive-list-of-wildcards)
    - [Commonly Used Character Classes](#commonly-used-character-classes)
    - [Wildcard Examples](#wildcard-examples)
    - [Character Ranges](#character-ranges)
    - [Dot Files](#dot-files)
    - [Wildcards Work in the GUI Too](#wildcards-work-in-the-gui-too)
  - [`mkdir` - Create Directories](#mkdir---create-directories)
  - [`cp` - Copy Files and Directories](#cp---copy-files-and-directories)
    - [`cp` Options](#cp-options)
    - [`cp` Examples](#cp-examples)
  - [`mv` - Move and Rename Files](#mv---move-and-rename-files)
    - [`mv` Options](#mv-options)
    - [`mv` Examples](#mv-examples)
  - [`rm` - Remove Files and Directories](#rm---remove-files-and-directories)
    - [`rm` Options](#rm-options)
    - [`rm` Examples](#rm-examples)
    - [Be careful with `rm`](#be-careful-with-rm)
  - [`ln` - Create Links](#ln---create-links)
    - [Hard Links](#hard-links)
    - [Soft Links (Symlink)](#soft-links-symlink)
  - [Summary](#summary)
    - [Summary of Commands](#summary-of-commands)

# Manipulating Files and Directories

## Wildcards (Globbing)

- Shell provides special characters called **wildcards** to help select groups of filenames or directories.
- Wildcards are also known as **globbing**.
- Wildcards allow filenames to be selected based on **patterns of characters**.

---

### Non-Exhaustive list of Wildcards

| Wildcard        | Meaning                                                        |
|-----------------|----------------------------------------------------------------|
| `*`             | Matches any characters                                         |
| `?`             | Matches any single character                                   |
| `[characters]`  | Matches any character that is a member of the set `characters` |
| `[!characters]` or `[^\characters]` | Matches any character that is not a member of the set `characters` |
| `[[:class:]]`   | Matches any character that is a member of the specified class |

---

### Commonly Used Character Classes

| Character Class | Meaning                          |
|-----------------|----------------------------------|
| `[:alnum:]`     | Matches any alphanumeric character |
| `[:alpha:]`     | Matches any alphabetic character  |
| `[:digit:]`     | Matches any numeral               |
| `[:lower:]`     | Matches any lowercase letter     |
| `[:upper:]`     | Matches any uppercase letter     |

---

### Wildcard Examples

| Pattern                                | Matches                                                   |
|----------------------------------------|-----------------------------------------------------------|
| `*`                                    | All files                                                 |
| `g*`                                   | Any file beginning with “g”                               |
| `b*.txt`                               | Any file beginning with “b” followed by any characters and ending with “.txt” |
| `Data???`                              | Any file beginning with “Data” followed by exactly three characters |
| `[abc]*`                               | Any file beginning with either an “a”, a “b”, or a “c”     |
| `BACKUP.[0-9][0-9][0-9]`               | Any file beginning with “BACKUP.” followed by exactly three numerals |
| `[[:upper:]]*`                         | Any file beginning with an uppercase letter               |
| `[![:digit:]]*`                        | Any file not beginning with a numeral                      |
| `*[[:lower:]123]`                      | Any file ending with a lowercase letter or the numerals “1”, “2”, or “3” |

---

### Character Ranges  
- [A-Z] and [a-z] are traditional Unix notations for character ranges.
- These notations may not always work as expected in modern Linux versions unless properly configured.
- It's recommended to avoid using character ranges and instead use **character classes**.

---

### Dot Files
- Files and directories starting with a dot (.) are **hidden files**.
- Hidden files don't appear in the output of `ls` unless the `-a` or `-A` options are used.
- **Wildcards**: Hidden files won't show unless a wildcard pattern like `.*` is used.
- The `.*` pattern will also match the current directory (`.`) and the parent directory (`..`).
- To exclude `.` and `..`, use patterns like `.[!.]*` or `.??*`.
   - **Explanation**:
     - `.`: Matches the literal dot at the beginning of the filename (indicating it's a hidden file).
     - `[!.]`: Matches any character except for a dot (`!` negates the pattern). This ensures the pattern doesn't match files like `.` or `..`.
     - `??`: Matches exactly two characters (any character except a space).
       - This pattern matches hidden files that start with a dot and have at least two characters in the name.
     - `*`: Matches zero or more additional characters after the first two.
     - `*`: Matches any number of characters after the dot (ensures the file name isn't just a dot).

---

### Wildcards Work in the GUI Too

- **Wildcards** are not just for the command line; they are also supported by graphical file managers, making file selection easier and faster.

- **Nautilus** (GNOME file manager):
  - You can press `Ctrl-s` to open the search box.
  - Enter a file selection pattern with wildcards, and Nautilus will select the matching files in the current directory.

- **Takeaway**: Many useful features from the command line, like wildcards, are integrated into graphical file managers, enhancing the Linux desktop experience.

---

## `mkdir` - Create Directories

**Syntax**:  
```bash
mkdir directory...
```
The three dots (`...`) indicate that multiple directories can be specified in a single command.

**Example 1**:  
```bash
mkdir dir1
```  
This creates a single directory named `dir1`.

**Example 2**:  
```bash
mkdir dir1 dir2 dir3
```  
This creates three directories: `dir1`, `dir2`, and `dir3`.

---

## `cp` - Copy Files and Directories

The `cp` command is used to copy files or directories.

**Syntax 1**:  
```bash
cp item1 item2
```  
This copies the single file or directory `item1` to the file or directory `item2`.

**Syntax 2**:  
```bash
cp item... directory
```  
This copies multiple items (either files or directories) into a specified `directory`.

### `cp` Options

| Option | Long Option     | Meaning                                                                                      |
|--------|-----------------|----------------------------------------------------------------------------------------------|
| -a     | --archive       | Copy the files and directories and all of their attributes, including ownerships and permissions. |
| -i     | --interactive   | Before overwriting an existing file, prompt the user for confirmation.  [yY] are yes, and any other character conveys no.    |
| -r     | --recursive     | Recursively copy directories and their contents.                                             |
| -u     | --update        | Only copy files that either don't exist or are newer than the existing corresponding files.    |
| -v     | --verbose       | Display informative messages as the copy is performed.                                        |

### `cp` Examples

| Command                              | Description                                                                                     |
|--------------------------------------|-------------------------------------------------------------------------------------------------|
| cp file1 file2                       | Copy file1 to file2. If file2 exists, it is overwritten with the contents of file1. If file2 does not exist, it is created. |
| cp -i file1 file2                    | Same as the previous command, except that if file2 exists, the user is prompted before it is overwritten. |
| cp file1 file2 dir1                  | Copy file1 and file2 into directory dir1. The directory dir1 must already exist.                 |
| cp dir1/* dir2                       | Using a wildcard, copy all the files in dir1 into dir2. The directory **dir2 must already exist**.   |
| cp -r dir1 dir2                      | Copy the contents of directory dir1 to directory dir2. If directory dir2 does not exist, it is created and, after the copy, will contain the same contents as directory dir1. If directory dir2 does exist, then directory dir1 (and its contents) will be copied into dir2. |

---

## `mv` - Move and Rename Files

- **`mv item1 item2`**: Moves or renames the file or directory `item1` to `item2`. The original `item1` no longer exists after the operation.
- **`mv item... directory`**: Moves one or more items (files or directories) from one location to another directory.

### `mv` Options

| Option | Long Option     | Meaning                                                                                         |
|--------|-----------------|-------------------------------------------------------------------------------------------------|
| -i     | --interactive   | Before overwriting an existing file, prompt the user for confirmation. Without this option, files are silently overwritten. |
| -u     | --update        | Only move files that either don't exist or are newer than the existing corresponding files in the destination directory. |
| -v     | --verbose       | Display informative messages as the move is performed.                                          |

### `mv` Examples

Here is the table representation of the `mv` command results:

| Command                             | Result                                                                                                         |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------|
| `mv file1 file2`                    | Move `file1` to `file2`. If `file2` exists, it is overwritten with the contents of `file1`. If `file2` does not exist, it is created. In either case, `file1` ceases to exist. |
| `mv -i file1 file2`                 | Same as the previous command, except that if `file2` exists, the user is prompted before it is overwritten.    |
| `mv file1 file2 dir1`               | Move `file1` and `file2` into directory `dir1`. The directory `dir1` must already exist.                      |
| `mv dir1 dir2`                      | If directory `dir2` does not exist, create directory `dir2` and move the contents of directory `dir1` into `dir2`, deleting directory `dir1`. If directory `dir2` exists, move directory `dir1` (and its contents) into `dir2`. |

---

## `rm` - Remove Files and Directories

The rm command is used to remove (delete) files and directories, as shown here:
```bash
rm item...
```
where item is one or more files or directories.

### `rm` Options

| Option | Long Option   | Meaning                                                                                                   |
|--------|---------------|-----------------------------------------------------------------------------------------------------------|
| `-i`   | `--interactive` | Before deleting an existing file, prompt the user for confirmation. If this option is not specified, `rm` will silently delete files. |
| `-r`   | `--recursive`   | Recursively delete directories. This means that if a directory being deleted has subdirectories, delete them too. To delete a directory, this option must be specified. |
| `-f`   | `--force`       | Ignore nonexistent files and do not prompt. This overrides the `--interactive` option.                    |
| `-v`   | `--verbose`     | Display informative messages as the deletion is performed.                                                |

### `rm` Examples

| Command                          | Result                                                                                                      |
|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
| `rm file1`                        | Delete file1 silently.                                                                                       |
| `rm -i file1`                     | Same as the previous command, except that the user is prompted for confirmation before the deletion is performed. |
| `rm -r file1 dir1`                | Delete file1 and dir1 along with its contents.                                                               |
| `rm -rf file1 dir1`               | Same as the previous command, except that if either file1 or dir1 do not exist, `rm` will continue silently. |

### Be careful with `rm`

- **No Undelete in Unix-like Systems**: Linux doesn't have an undelete command, so once something is deleted with `rm`, it is gone permanently.
- **Be Careful with Wildcards**: Wildcards can cause unintended deletions. For example:
  - Correct command: `rm *.html` (deletes only HTML files).
  - Mistaken command: `rm * .html` (deletes all files in the directory and then throws an error about `.html`).
- **Test Wildcards First**: Before using `rm` with wildcards, always use `ls` to list the files that will be affected.
  - After confirming with `ls`, press the up arrow to recall the command and replace `ls` with `rm` for deletion.

---

## `ln` - Create Links

### Hard Links

- **Definition**: A hard link creates an additional directory entry for a file, making it indistinguishable from the original file.
- **Limitations**:
  1. Cannot reference a file outside its own file system (same disk partition).
  2. Cannot reference a directory.
- **Characteristics**:
  - Hard links don't show any special indication when listed in a directory (unlike symbolic links).
  - When a hard link is deleted, the file contents remain until all links to the file are deleted.
- **Modern Practice**: Although hard links are important, symbolic links are preferred in modern practice.

- Hard link creation: 
  ```bash
  ln <file-name> <link-name>
  ```
- When using `ls`, the number after permissions denote the hard link. Every file will at least have on hard link, because the file's name is created by a link.
  ```bash
  [me@linuxbox playground]$ ls -l
  total 16
  -rw-r--r-- 2 me me 1650 2025-01-10 16:33 fun
  -rw-r--r-- 2 me me 1650 2025-01-10 16:33 fun-hard
  ```
- What is the difference between the above two links?
  - Files are made of two parts - file content and file name. 
  - We can have multiple file names (hard links) pointing to the same content (blob).
  - System assigns a chain of disk blocks to what is called **inode**, which is then associated with the name part. 
  - Each hard link refers to a specific inode containing the file's contents.
  - Use `ls -i` to view the details of inode, in the below code, first column gives inode number, and we can infer that they both point to same file. 
    ```bash
    [me@linuxbox playground]$ ls -li
    total 16
    12353538 -rw-r--r-- 4 me me 1650 2025-01-10 16:33 fun
    12353538 -rw-r--r-- 4 me me 1650 2025-01-10 16:33 fun-hard
    ```


### Soft Links (Symlink)

- **Definition**: Symbolic links are special files that contain a **text pointer** to the referenced file or directory, overcoming the limitations of hard links.
- **Comparison to Windows Shortcuts**: Similar to Windows shortcuts, but they predate the Windows feature by many years.
- **Key Characteristics**:
  - The symbolic link and the file it points to are largely indistinguishable. Writing to the symbolic link writes to the referenced file.
  - Deleting a symbolic link removes only the link, not the original file.
  - If the file is deleted before the symbolic link, the link becomes "**broken**" and points to nothing.
- **Broken Links**: Many implementations, like `ls`, display broken links in a distinguishing color (e.g., red).

- Soft link creation: 
  ```bash
  ln -s <file-name> <link-name>
  ```
  - Note the file-name and link-name should use relative paths instead of absolute path, since if the directories were moved, there would be no breaking changes.
- Examples: 
  - Not good example: 
    ```bash
    [me@linuxbox playground]$ ln -s /home/me/playground/fun dir1/fun-sym
    ```
  - Good example: 
    ```bash
    [me@linuxbox playground]$ ln -s fun fun-sym
    [me@linuxbox playground]$ ln -s ../fun dir1/fun-sym
    ```
- Symlink can be created in GUI holding `Ctrl + Shift` keys and dragging the files.

---

## Summary

Wildcards, also known as **globbing**, allow users to match filenames based on patterns, making file selection more efficient. Common wildcards include `*` (matches any characters), `?` (matches a single character), and character sets like `[abc]` or `[!0-9]`. Character classes such as `[:alnum:]` and `[:digit:]` provide more precise matching. Hidden files (those starting with `.`) require special patterns like `.[!.]*` or `.??*` to exclude `.` and `..`. Wildcards are not limited to the command line—they also work in graphical file managers like **Nautilus**, where `Ctrl+S` enables quick pattern-based file selection.

The `mkdir` command creates one or multiple directories at once, while `cp` is used to copy files and directories. The `cp` command supports options like `-r` for recursive copying, `-i` for interactive prompts before overwriting, and `-v` for verbose output. Similarly, `mv` is used to move or rename files and directories, with options like `-i` for confirmation before overwriting and `-u` to move only newer files.  

The `rm` command permanently deletes files and directories, requiring the `-r` option for recursive deletion of directories. The `-i` option prompts before deletion, while `-f` forces deletion without prompts. Since Linux does not have an undelete command, extreme caution is needed, especially when using wildcards (`*`). A good practice is to first list files with `ls` before executing a deletion command.

The `ln` command creates links, which can be either **hard links** or **symbolic (soft) links** or **symlinks**. Hard links act as additional directory entries pointing to the same inode, meaning the file content remains until all links are deleted. However, they cannot span different file systems or reference directories. Symbolic links, on the other hand, function like Windows shortcuts, containing a text pointer to the target file or directory. They can reference directories and cross file system boundaries but break if the target is deleted.  

To create a hard link, use `ln <file> <link>`, and for a symbolic link, use `ln -s <file> <link>`. Using relative paths when creating symbolic links prevents breakage if directories are moved. While hard links provide redundancy, symbolic links are more flexible and commonly used in modern systems. In GUI environments, symlinks can be created by dragging files while holding `Ctrl + Shift`.

### Summary of Commands

| Command                                      | Description                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| `*`                                          | Matches any characters                                                                                           |
| `?`                                          | Matches any single character                                                                                     |
| `[characters]`                               | Matches any character that is a member of the set `characters`                                                   |
| `[!characters]` or `[^\characters]`         | Matches any character that is not a member of the set `characters`                                               |
| `[[:class:]]`                               | Matches any character that is a member of the specified class                                                    |
| `[:alnum:]`     | Matches any alphanumeric character |
| `[:alpha:]`     | Matches any alphabetic character  |
| `[:digit:]`     | Matches any numeral               |
| `[:lower:]`     | Matches any lowercase letter     |
| `[:upper:]`     | Matches any uppercase letter     |
| `g*`                                   | Any file beginning with “g”                               |
| `b*.txt`                               | Any file beginning with “b” followed by any characters and ending with “.txt” |
| `Data???`                              | Any file beginning with “Data” followed by exactly three characters |
| `[abc]*`                               | Any file beginning with either an “a”, a “b”, or a “c”     |
| `BACKUP.[0-9][0-9][0-9]`               | Any file beginning with “BACKUP.” followed by exactly three numerals |
| `[[:upper:]]*`                         | Any file beginning with an uppercase letter               |
| `[![:digit:]]*`                        | Any file not beginning with a numeral                      |
| `*[[:lower:]123]`                      | Any file ending with a lowercase letter or the numerals “1”, “2”, or “3” |
| `.[!.]*` or `.??*`                          | Matches hidden files excluding `.` and `..`.                                                                    |
| `mkdir dir1`                                | Create a directory named `dir1`                                                                                  |
| `mkdir dir1 dir2`                           | Create multiple directories `dir1` and `dir2`                                                                    |
| `cp file1 file2`                            | Copy `file1` to `file2`. If `file2` exists, it is overwritten; otherwise, it is created.                        |
| `cp item1 item2 dir`                        | Copy `item1` and `item2` into `dir`. The directory must already exist.                                          |
| `cp -r dir1 dir2`                           | Copy directory `dir1` to `dir2`. If `dir2` exists, `dir1` is copied inside `dir2`; otherwise, `dir2` is created.|
| `cp dir1/* dir2`                       | Using a wildcard, copy all the files in dir1 into dir2. The directory **dir2 must already exist**.   |
| `cp -a file1 file2`                         | Copy `file1` to `file2` preserving attributes (ownership, permissions, etc.).                                   |
| `cp -i file1 file2`                         | Copy `file1` to `file2`, prompting before overwriting an existing `file2`.                                      |
| `cp -u file1 file2`                         | Copy only if `file1` is newer than `file2` or if `file2` does not exist.                                        |
| `cp -v file1 file2`                         | Copy `file1` to `file2`, displaying progress messages.                                                          |
| `mv file1 file2`                            | Move `file1` to `file2`. If `file2` exists, it is overwritten.                                                  |
| `mv item1 item2 ... itemN dir`              | Move multiple items into directory `dir`. The directory must already exist.                                     |
| `mv -i file1 file2`                         | Move `file1` to `file2`, prompting before overwriting `file2`.                                                  |
| `mv -u file1 file2`                         | Move `file1` to `file2` only if `file1` is newer than `file2` or if `file2` does not exist.                     |
| `mv -v file1 file2`                         | Move `file1` to `file2`, displaying progress messages.                                                          |
| `rm file1`                                  | Delete `file1` silently.                                                                                        |
| `rm -i file1`                               | Delete `file1`, prompting for confirmation before deletion.                                                     |
| `rm -r dir1`                                | Delete directory `dir1` and all its contents.                                                                   |
| `rm -rf dir1`                               | Force delete `dir1` and its contents without prompting.                                                         |
| `rm -v file1`                               | Delete `file1`, displaying progress messages.                                                                   |
| `ln file1 link1`                            | Create a hard link `link1` to `file1` (same inode).                                                             |
| `ln -s file1 link1`                         | Create a symbolic link `link1` to `file1` (different inode).                                                    |
| `ls -i`                                     | Display inode numbers of files.                                                                                 |
| `Nautilus - Ctrl + s`                       | Shortcut for searching in Nautilus file manager.                                                                |

---

