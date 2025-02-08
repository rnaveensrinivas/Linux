### Table of Contents
- [Working with Commands](#working-with-commands)
  - [Identifying Commands](#identifying-commands)
    - [`type` – Display a Command's Type](#type--display-a-commands-type)
    - [`which` – Display an Executable's Location](#which--display-an-executables-location)
  - [Getting a Command's Documentation](#getting-a-commands-documentation)
    - [`help` - Get Help for Shell Builtins](#help---get-help-for-shell-builtins)
    - [`--help` - Display Usage Information](#--help---display-usage-information)
    - [Using the `man` Command (Manual Pages)](#using-the-man-command-manual-pages)
      - [Manual Page Sections](#manual-page-sections)
      - [Specifying a Section](#specifying-a-section)
      - [Navigation in `man` Pages](#navigation-in-man-pages)
    - [Using `apropos` to Find Commands](#using-apropos-to-find-commands)
      - [Alternative: `man -k`\*](#alternative-man--k)
    - [**Using `whatis` to Get a Quick Command Description**](#using-whatis-to-get-a-quick-command-description)
    - [The most brutal man page, `bash`](#the-most-brutal-man-page-bash)

# Working with Commands

A **command** in Linux can be one of four types:  

1. **Executable Program**  
   - Found in directories like `/usr/bin`.  
   - Can be compiled binaries (C, C++, etc.) or scripts (Shell, Python, Perl, Ruby, etc.).  
   - These create a separate process to run.

2. **Shell Builtin**  
   - Commands built directly into the shell (e.g., `cd`).  
   - Executed faster than external programs since they don’t require a separate process.  

3. **Shell Function**  
   - Miniature shell scripts defined within the shell environment.  
   - Allow for reusable code inside the shell session.  

4. **Alias**  
   - User-defined shortcuts for commands.  
   - Useful for simplifying or customizing frequently used commands.

## Identifying Commands

### `type` – Display a Command's Type
- A **shell builtin** that shows what kind of command the shell will execute.  
- Syntax: `type command1 command2`  
- Examples:  
    ```bash
    $ type type
    type is a shell builtin # builtin

    $ type ls
    ls is aliased to 'ls --color=auto' # alias

    $ type cp
    cp is /usr/bin/cp # executable

    $ type which
    which is /usr/bin/which # executable

    $ type ls cp
    ls is aliased to `ls --color=auto'
    cp is hashed (/usr/bin/cp)

    ```
- Output can show if the command is a **builtin, alias, or executable**.  

### `which` – Display an Executable's Location
- Finds the **exact location** of an executable program.  
- Syntax: `which command`  
- Example:  
    ```bash
    $ which ls
    /usr/bin/ls
    ```
- Works **only for executables**, **not for builtins or aliases**.  
- Example of a failure case:  
    ```bash
    $ which cd
    /usr/bin/which: no cd in (/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games)
    ```
- This means `cd` is not an executable but a **shell builtin**.

---

## Getting a Command's Documentation

### `help` - Get Help for Shell Builtins

- Bash has a built-in help facility available for each of the shell builtins. 
- Syntax, `help builtin-command-name`
- Example: 
    ```bash
    [me@linuxbox ~]$ help cd
    cd: cd [-L|[-P [-e]] [-@]] [dir]
        Change the shell working directory.

        Change the current directory to DIR. ...
        Options: ...
    ```
- A note on notation: 
  - **Square brackets `[ ]`** → Indicate **optional** elements.  
  - **Vertical bar `|`** → Indicates **mutually exclusive** options (choose one).  
  - **Example: `cd [-L|[-P[-e]]] [dir]`**  
    - `cd` command may have optional flags:  
      - `-L` **or** `-P` (one of these, not both).  
      - If `-P` is used, `-e` can **also** be included.  
      - The command may end with an **optional** `dir` argument.  


- `help -m` command
    ```bash
    $ help -m
    GNU bash, version 5.2.21(1)-release (x86_64-pc-linux-gnu)
    These shell commands are defined internally.  Type `help' to see this list.
    Type `help name' to find out more about the function `name'.
    Use `info bash' to find out more about the shell in general.
    Use `man -k' or `info' to find out more about commands not in this list.

    A star (*) next to a name means that the command is disabled.

    job_spec [&]                                   history [-c] [-d offset] [n] or history -an>
    (( expression ))                               if COMMANDS; then COMMANDS; [ elif COMMANDS>
    . filename [arguments]                         jobs [-lnprs] [jobspec ...] or jobs -x comm>
    :                                              kill [-s sigspec | -n signum | -sigspec] pi>
    [ arg... ]                                     let arg [arg ...]
    [[ expression ]]                               local [option] name[=value] ...
    alias [-p] [name[=value] ... ]                 logout [n]
    bg [job_spec ...]                              mapfile [-d delim] [-n count] [-O origin] [>
    bind [-lpsvPSVX] [-m keymap] [-f filename] [>  popd [-n] [+N | -N]
    break [n]                                      printf [-v var] format [arguments]
    builtin [shell-builtin [arg ...]]              pushd [-n] [+N | -N | dir]
    caller [expr]                                  pwd [-LP]
    case WORD in [PATTERN [| PATTERN]...) COMMAN>  read [-ers] [-a array] [-d delim] [-i text]>
    cd [-L|[-P [-e]] [-@]] [dir]                   readarray [-d delim] [-n count] [-O origin]>
    command [-pVv] command [arg ...]               readonly [-aAf] [name[=value] ...] or reado>
    compgen [-abcdefgjksuv] [-o option] [-A acti>  return [n]
    complete [-abcdefgjksuv] [-pr] [-DEI] [-o op>  select NAME [in WORDS ... ;] do COMMANDS; d>
    compopt [-o|+o option] [-DEI] [name ...]       set [-abefhkmnptuvxBCEHPT] [-o option-name]>
    continue [n]                                   shift [n]
    coproc [NAME] command [redirections]           shopt [-pqsu] [-o] [optname ...]
    declare [-aAfFgiIlnrtux] [name[=value] ...] >  source filename [arguments]
    dirs [-clpv] [+N] [-N]                         suspend [-f]
    disown [-h] [-ar] [jobspec ... | pid ...]      test [expr]
    echo [-neE] [arg ...]                          time [-p] pipeline
    enable [-a] [-dnps] [-f filename] [name ...>   times
    eval [arg ...]                                 trap [-lp] [[arg] signal_spec ...]
    exec [-cl] [-a name] [command [argument ...]>  true
    exit [n]                                       type [-afptP] name [name ...]
    export [-fn] [name[=value] ...] or export ->   typeset [-aAfFgiIlnrtux] name[=value] ... o>
    false                                          ulimit [-SHabcdefiklmnpqrstuvxPRT] [limit]
    fc [-e ename] [-lnr] [first] [last] or fc -s>  umask [-p] [-S] [mode]
    fg [job_spec]                                  unalias [-a] name [name ...]
    for NAME [in WORDS ... ] ; do COMMANDS; don>   unset [-f] [-v] [-n] [name ...]
    for (( exp1; exp2; exp3 )); do COMMANDS; don>  until COMMANDS; do COMMANDS-2; done
    function name { COMMANDS ; } or name () { CO>  variables - Names and meanings of some shel>
    getopts optstring name [arg ...]               wait [-fn] [-p var] [id ...]
    hash [-lr] [-p pathname] [-dt] [name ...]      while COMMANDS; do COMMANDS-2; done
    help [-dms] [pattern ...]                      { COMMANDS ; }
    ```
---

### `--help` - Display Usage Information
 
- Many **executable programs** support `--help`, which provides a brief description of their **syntax and options**.  
- Example:  
  ```bash
  $ mkdir --help
  Usage: mkdir [OPTION] DIRECTORY...
  Create the DIRECTORY(ies), if they do not already exist.

    -m, --mode=MODE     Set file mode (like `chmod`).
    -p, --parents       Create parent directories as needed.
    -v, --verbose       Print a message for each created directory.
    --help              Display this help and exit.
    --version           Output version information and exit.
  ```
- If a program **doesn't support** `--help`, trying it might still display an **error message** with usage information.  
- **Tip**: Always try `--help` first when exploring a new command!

---

### Using the `man` Command (Manual Pages)

- The `man` command displays a program’s **manual page**, which serves as a **reference** (not a tutorial).  
- Syntax:  
  ```bash
  man command
  ```
- Example:  
  ```bash
  $ man ls
  ```
- **Man pages typically include:**  
  - **Title** (command name)  
  - **Synopsis** (syntax and usage)  
  - **Description** (command purpose)  
  - **Options** (list of available flags)  
  - *Usually, no examples are included*  

---

#### Manual Page Sections
- The **Linux manual** is organized into sections, and each of these sections contain a bunch of commands:  

    | Section | Description |
    |---------|-------------|
    | **1** | User commands |
    | **2** | Kernel system calls |
    | **3** | C library functions |
    | **4** | Special files (devices, drivers) |
    | **5** | File formats and configuration files |
    | **6** | Games and amusements (screen savers, etc.) |
    | **7** | Miscellaneous (macro packages, conventions) |
    | **8** | System administration commands |

---

#### Specifying a Section

- If a name appears in multiple sections, specify the **section number** to get the correct page.  
- Example:  
  ```bash
  # Syntax
  $ man section search_term

  $ man 5 passwd
  ```
  - Displays the man page for `/etc/passwd` **file format** (Section 5), instead of the `passwd` **command** (Section 1).  
- Note, not all commands have all the sections:
    ```bash
    $ man 1 
    Display all 1663 possibilities? (y or n)

    $ man 5 
    Display all 592 possibilities? (y or n)

    $ man 3 ls
    No manual entry for ls in section 3
    ```

---

#### Navigation in `man` Pages
- The `man` command uses **`less`** for navigation, so you can:  
  - Scroll: **Up/Down** or `j/k`  
  - Search: `/keyword`  
  - Quit: `q`  

---

### Using `apropos` to Find Commands

- The `apropos` command searches for man pages **related to a keyword**.  
- Syntax:  
  ```bash
  apropos search_term
  ```
- Example:  
  ```bash
  $ apropos partition
  ```
  Output:  
  ```
  cfdisk (8)         - display or manipulate disk partition table
  fdisk (8)          - manipulate disk partition table
  partprobe (8)      - inform the OS of partition table changes
  sfdisk (8)         - partition table manipulator for Linux
  ```
- The **first column** is the command name, and the **second column** is the man page section.  

---

#### Alternative: `man -k`*
- The `man -k` command performs the same search as `apropos`.  
- Example:  
  ```bash
  $ man -k partition
  ```

**When to Use `apropos`?**  
- When you **don’t know** the exact command name.  
- To explore **related commands** for a topic.  

---

### **Using `whatis` to Get a Quick Command Description**  

- The `whatis` command provides a **one-line summary** of a command from the man pages.  
- Syntax:  
  ```bash
  whatis command
  ```
- Example:  
  ```bash
  $ whatis ls
  ```
  Output:  
  ```
  ls (1) - list directory contents
  ```
- The **first field** is the command name, **second field** is the man page section, and **third field** is the description.  

---

### The most brutal man page, `bash`
- The **`man bash`** page is **over 80 pages long**, very **dense**, and difficult for beginners.  
- While **not beginner-friendly**, it is an **accurate and complete** reference.  
- Mastering it is a milestone for **advanced shell users!** 🚀  

---