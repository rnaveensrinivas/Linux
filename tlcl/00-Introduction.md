## Table of Contents
- [Introduction](#introduction)
  - [Why use Command Line?](#why-use-command-line)
  - [What this Book is about?](#what-this-book-is-about)
  - [Who Should Read This Book](#who-should-read-this-book)
  - [What's in This Book](#whats-in-this-book)
  - [How to Read this Book](#how-to-read-this-book)
  - [Why I Don't Call It 'GNU/Linux'](#why-i-dont-call-it-gnulinux)

---

# Introduction

**This book is not a history lesson**:  
- No retelling of **Linus Torvalds' creation of Linux kernel in 1991**.  
- No retelling of **Richard Stallman’s GNU Project to create free Unix-like OS that started years prior to 1991**.  

**Main focus of the book**:  
- How to take back control of your computer.  

**Background (1970s Revolution)**:  
- Microprocessors allowed ordinary people to own computers.  
- Before that, only big businesses and governments had it.  
- Limited what individuals could do with computers.  

**Current situation**:  
- Computers are everywhere—wristwatches, data centers, etc.  
- Global network connects all these devices.  
- This should have led to more personal empowerment.  

**Problem**:  
- Large corporations now control most computers.  
- They decide what users can and cannot do with computers.  

**Solution**:  
- People worldwide are writing their own software.  
- They are building Linux to regain control.  

**True meaning of freedom**:  
- Freedom is the power to deciding what your computer does.  
- This requires knowing what your computer is doing.  
- A free computer has no secrets—everything is transparent.

---

## Why use Command Line?

**Hacker stereotype in movies**  
- Super hackers never use a mouse.  
- Filmmakers recognize that real efficiency comes from typing.  

**Modern computer users and the GUI**  
- Most users today only know the **Graphical User Interface (GUI)**.  
- Vendors and media portray the **Command Line Interface (CLI)** as outdated and difficult.  

**Advantages of the CLI**  
- **Expressive & powerful**: Communicating via CLI is like using the written word for humans.  
- **Classic saying**:  
  - GUIs make easy tasks easy.  
  - CLIs make **difficult tasks possible**.  

**Linux and Unix connection**  
- Linux inherits its CLI tools from **Unix**.  
- Unix gained prominence in the early **1980s**, before widespread GUI adoption.  
- Since it existed before GUIs, extensive CLI tools were developed out of necessity.  

**Why early adopters chose Linux over Windows NT**  
- The **powerful command line interface** made complex tasks achievable.

---

## What this Book is about?

**Broad overview of the Linux command line**  
- Not just about a single program like **bash**.  
- Focuses on **how to use the CLI effectively** in a larger sense, **how to live with CLI**.  
- Covers **how it works, what it can do, and the best ways to use it**.  

**Not a Linux system administration book**  
- Some system admin topics are touched upon, but not the main focus.  
- Provides a **solid foundation** for further study.  
- Essential for anyone interested in **system administration**.  

**Linux-centric approach**  
- Unlike other books that include **generic Unix or macOS**, this book is **focused on Linux**.  
- Other books often **"water down"** content for broader appeal.  
- **95% of the content** covered here is useful for Unix-like systems, but **optimized for modern Linux users**.
---

## Who Should Read This Book

**Target audience**  
- New **Linux users** migrating from other platforms.  
- Likely **power users** of **Microsoft Windows**.  
- People tasked with **administering a Linux server**.  
- Users exploring **single-board computers (SBCs)** like **Raspberry Pi**.  
- Desktop users switching due to **security concerns**.  

**No shortcuts to Linux mastery**  
- Learning the command line is **challenging** and requires **real effort**.  
- Not **difficult**, but **vast**—thousands of commands available.  
- Not a **casual** learning process.  

**Why it's worth it**  
- Mastering the command line unlocks **real power** beyond GUI limitations.  
- Skills are **long-lasting**—useful **even after 10 years**.  
- The **CLI has stood the test of time**.  

**No programming experience required**  
- Assumes **zero programming background**.  
- Introduces readers to **basic programming concepts** along the way.

---

## What's in This Book

This book is structured to guide you through the Linux command line in a **logical sequence**, helping you adapt to the **Unix mindset**, which differs from Windows. It’s divided into four parts: Part 1 introduces the shell and basic command line concepts, Part 2 covers configuring the environment, Part 3 explores common tasks and essential tools for data manipulation, and Part 4 introduces shell scripting to automate tasks and develop transferable programming skills. Along the way, you'll gain insights into Linux's Unix roots and the rationale behind its design.

---

## How to Read this Book

To read this book, **start from the beginning and progress through to the end**, as it’s designed to be a **continuous learning journey rather than a reference**. You’ll need a working Linux installation, which can be set up by either installing Linux on a desktop computer (preferably Ubuntu, Fedora, or OpenSUSE) or using a Live CD/USB for testing compatibility. A desktop with at least 2 GB of RAM and 6 GB of free space is recommended. You’ll also need superuser privileges for some tasks. Once your setup is ready, follow along with the exercises and start typing to get hands-on experience.

---

## Why I Don't Call It 'GNU/Linux'

**Terminology Debate**: 
- The term “GNU/Linux” is used by some to reflect both the Linux kernel and the GNU Project's contributions.
- Technically, “Linux” refers to just the operating system kernel, not the full operating system.

**Role of Richard Stallman**:
- Richard Stallman founded the Free Software Movement and the Free Software Foundation.
- He created the GNU Project, wrote the first version of the GNU C Compiler (gcc), and authored the GNU General Public License (GPL).
- Stallman prefers using “GNU/Linux” to highlight the contributions of the GNU Project.

**Issues with "GNU/Linux" Naming**:
- The Linux kernel is essential but not the entire operating system; many other contributions from various developers form the complete OS.
- The term “GNU/Linux” may seem unfair to others who made significant contributions to the system outside of GNU.

**Technically Accurate Naming**:
- “Linux/GNU” would be more technically accurate as the kernel (Linux) boots first, with everything else running on top.

**Popular Usage**:
- In practice, "Linux" commonly refers to both the kernel and the entire ecosystem of open-source software in a Linux distribution.
- The use of single-word names like DOS, Windows, macOS, etc., is more common in the operating system marketplace.

---