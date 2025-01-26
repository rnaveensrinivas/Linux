# What is the Shell?

### Table of Contents

- [What is the Shell?](#what-is-the-shell)
    - [Table of Contents](#table-of-contents)
    - [The Shell](#the-shell)
    - [Terminal Emulators](#terminal-emulators)
    - [Shell Prompt](#shell-prompt)
    - [A Few Words About Mice and Focus](#a-few-words-about-mice-and-focus)
    - [Simple Commands](#simple-commands)
    - [The Console Behind the Curtain](#the-console-behind-the-curtain)
  - [Summary:](#summary)

---

### The Shell
- The command line refers to the shell, a **program** that processes keyboard commands and passes them to the operating system.
- The default shell on most Linux distributions is **bash** (Bourne Again SHell), which is an enhanced version of the original Unix shell, **sh**, created by Steve Bourne.

---

### Terminal Emulators
- Terminal emulators are required to interact with the shell when using a graphical user interface (GUI).
- Common terminal emulators:
  - **KDE** (KDE stands for **K** **D**esktop **E**nvironment, and it's a **g**raphical **u**ser **i**nterface (GUI) for Linux operating systems) uses **konsole**.
  - **GNOME** (GNOME (**G**NU **N**etwork **O**bject **M**odel **E**nvironment) is a graphical user interface (GUI) and set of computer desktop applications for Linux operating system (OS) users) uses **gnome-terminal** (often listed simply as "terminal" in app menu).
- Many other terminal emulators exist, and all of them provide access to the shell. Personal preference for terminal emulators may develop based on features and functionality.

---

### Shell Prompt

**Launching the Terminal**: 
- Open the terminal emulator to begin interacting with the shell.
- You will gets something like this `[username@machinename ~]$`. This is called a shell prompt.

**Shell Prompt Breakdown**:
- It includes the username, machine name, and current directory.
- The prompt usually ends with a dollar sign (`$`).

**Superuser Privileges**:
- If the prompt ends with a pound sign (`#`), the terminal session has superuser privileges.
- This indicates that the user is either logged in as the root user or has superuser (administrative) privileges.

**Command History & Cursor Movement**
- Press the **up-arrow** key to recall the previous command.
- Most Linux distributions store the last 1000 commands by default.
- Press the **down-arrow** key to move forward through the command history.
- Use the **left** and **right-arrow** keys to move the cursor anywhere on the command line for easier editing.

---

### A Few Words About Mice and Focus

**Using the Mouse in Terminal**:
- The terminal can also be used with a mouse for quick copy and paste.
- Highlight text (left-click and drag or double-click a word) to copy it into an X Window buffer, (X Window System is the underlying engine that makes the GUI go and it has a buffer (clipboard)).
- Press the **middle mouse button** to paste the text at the cursor.

**Copy-Paste in Terminal**:
- **Ctrl+C** and **Ctrl+V** do not work for copy-paste in the terminal.
- These key combinations have different functions in the shell.
- And they were assigned many years before the release of Microsoft Windows.

**Focus Policy**:
- Most desktop environments (KDE or GNOME) in an effort to mimic Windows use "click to focus," meaning you must click a window to activate it.
- Traditional X behavior is "focus follows mouse," where a window becomes active by just passing the mouse over it.
- Setting "focus follows mouse" can improve copy-paste usability and can be enabled in the window manager’s configuration program.

---

### Simple Commands

```bash
$ date
Sun Jan 26 11:53:56 AM IST 2025

$ uptime
 11:54:31 up  3:24,  1 user,  load average: 0.37, 0.51, 0.59

$ df -h # stands for disk free, -h for human readable
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           732M  2.3M  730M   1% /run
/dev/nvme0n1p2  468G   28G  416G   7% /
tmpfs           3.6G   23M  3.6G   1% /dev/shm
tmpfs           5.0M   16K  5.0M   1% /run/lock
efivarfs        160K   72K   84K  47% /sys/firmware/efi/efivars
/dev/nvme0n1p1  1.1G  6.2M  1.1G   1% /boot/efi
tmpfs           732M  132K  732M   1% /run/user/1000


$ free
               total        used        free      shared  buff/cache   available
Mem:         7493980     3370188     1750160      121776     2768712     4123792
Swap:        4194300           0     4194300

$ exit
$ ^d # control + d also quit.
```

---

### The Console Behind the Curtain

**Virtual Terminals/Consoles**:
- Even without a terminal emulator, several terminal sessions (virtual consoles) run in the background.
- Access virtual terminals by pressing **Ctrl-Alt-F1** through **Ctrl-Alt-F6**.

**Switching Between Consoles**:
- To switch between virtual consoles, use **Alt-F1** through **Alt-F6**.
- To return to the graphical desktop, press **Ctrl-Alt-F2** or **Alt-F2**.

---

## Summary: 

The shell is a program that processes keyboard commands and passes them to the operating system, with **bash** being the default shell in most Linux distributions. Terminal emulators, such as **konsole** (KDE) and **gnome-terminal** (GNOME), are used to interact with the shell in a graphical environment. The shell prompt displays the username, machine name, and current directory, with a dollar sign (`$`) indicating a regular user and a pound sign (`#`) indicating superuser privileges. Command history and cursor movement are facilitated with the up, down, left, and right arrow keys, making editing commands easy. Mouse support in the terminal allows for quick copy-paste using the middle mouse button, and focus behavior can be configured to improve usability. Virtual terminals provide additional terminal sessions that can be accessed using **Ctrl-Alt-F1** through **Ctrl-Alt-F6**, with the ability to switch between them and return to the graphical desktop. Simple commands like `date`, `uptime`, `df`, `free`, and `exit` provide useful system information and control.

**Summary of commands and keybindings**:

| Command/Keybinding           | Description                                                       |
|------------------------------|-------------------------------------------------------------------|
| `$ date`                      | Displays the current date and time.                               |
| `$ uptime`                    | Shows how long the system has been running, along with load average. |
| `$ df`                        | Displays disk space usage of mounted filesystems (df stands for disk free).           |
| `$ free`                      | Shows memory and swap usage.                                     |
| `$ exit`                      | Exits the current terminal session.                              |
| `$ ^d`                        | Control + D also exits the terminal session.                     |
| `Ctrl-Alt-F1 to F6`           | Access virtual terminals 1 through 6.                             |
| `Alt-F1 to F6`                | Switch between virtual consoles 1 through 6.                      |
| `Ctrl-Alt-F2` or `Alt-F2`     | Return to the graphical desktop (home).                          |

---