# Manipulating Files and Directories

## Table of Content
- [Manipulating Files and Directories](#manipulating-files-and-directories)
  - [Table of Content](#table-of-content)
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
    - [Soft Links](#soft-links)

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
| -i     | --interactive   | Before overwriting an existing file, prompt the user for confirmation.                         |
| -r     | --recursive     | Recursively copy directories and their contents.                                             |
| -u     | --update        | Only copy files that either don't exist or are newer than the existing corresponding files.    |
| -v     | --verbose       | Display informative messages as the copy is performed.                                        |

### `cp` Examples

| Command                              | Description                                                                                     |
|--------------------------------------|-------------------------------------------------------------------------------------------------|
| cp file1 file2                       | Copy file1 to file2. If file2 exists, it is overwritten with the contents of file1. If file2 does not exist, it is created. |
| cp -i file1 file2                    | Same as the previous command, except that if file2 exists, the user is prompted before it is overwritten. |
| cp file1 file2 dir1                  | Copy file1 and file2 into directory dir1. The directory dir1 must already exist.                 |
| cp dir1/* dir2                       | Using a wildcard, copy all the files in dir1 into dir2. The directory dir2 must already exist.   |
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

Here is the table for the options of the `rm` command:

| Option | Long Option   | Meaning                                                                                                   |
|--------|---------------|-----------------------------------------------------------------------------------------------------------|
| `-i`   | `--interactive` | Before deleting an existing file, prompt the user for confirmation. If this option is not specified, `rm` will silently delete files. |
| `-r`   | `--recursive`   | Recursively delete directories. This means that if a directory being deleted has subdirectories, delete them too. To delete a directory, this option must be specified. |
| `-f`   | `--force`       | Ignore nonexistent files and do not prompt. This overrides the `--interactive` option.                    |
| `-v`   | `--verbose`     | Display informative messages as the deletion is performed.                                                |

### `rm` Examples

Here is the table for the command results of the `rm` command:

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

Here are the bullet point notes for **Hard Links**:

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

### Soft Links

- **Definition**: Symbolic links are special files that contain a text pointer to the referenced file or directory, overcoming the limitations of hard links.
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

---

