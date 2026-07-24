# 🛠️ GNU

## Overview

**GNU** is a free and open-source collection of software tools, libraries, and utilities that work together with the **Linux Kernel** to form a complete operating system, commonly known as **GNU/Linux**.

The GNU Project was started by **Richard Stallman** in **1983** with the goal of creating a completely free Unix-like operating system.

---

## What is GNU?

**GNU** stands for **"GNU's Not Unix"**, a recursive acronym.

It is a project that provides many of the essential components required for a functional operating system, including:

- Shells
- Compilers
- Libraries
- Core Utilities
- Debugging Tools
- Text Editors

> 💡 **Key Point**
>
> GNU is **not the kernel**. It provides the software that runs **on top of the Linux Kernel**.

---

## Why Was GNU Created?

During the early 1980s, most operating systems were **proprietary**, meaning their source code was not publicly available.

Richard Stallman started the **GNU Project** to develop a completely **free and open-source Unix-like operating system**.

Although GNU successfully developed most of the required software, it lacked one essential component:

- **A Kernel**

---

## The Missing Piece

In **1991**, **Linus Torvalds** released the **Linux Kernel**.

Combining the GNU tools with the Linux Kernel resulted in a complete operating system.

```text
GNU Tools
      +
Linux Kernel
      =
GNU/Linux
```

This is why the operating system is technically referred to as **GNU/Linux**.

---

## GNU Tools

GNU provides many tools that are used daily by Linux users and developers.

Some commonly used GNU tools include:

| Tool | Purpose |
| :--- | :--- |
| **Bash** | Command Shell |
| **GCC** | C/C++ Compiler |
| **GDB** | Debugger |
| **Make** | Build Automation Tool |
| **GNU Core Utilities** | Basic commands such as `ls`, `cp`, `mv`, `cat`, `pwd`, `mkdir`, `rm` |
| **glibc** | GNU C Standard Library |
| **Emacs** | Text Editor |

---

## How GNU Works with Linux

The GNU tools provide the interface and utilities used by users and applications.

Whenever a command is executed, the GNU tools communicate with the Linux Kernel through **System Calls**, and the kernel interacts with the hardware.

```text
User
   │
   ▼
GNU Tools (Bash, ls, cp...)
   │
   ▼
System Calls
   │
   ▼
Linux Kernel
   │
   ▼
Hardware
```

---

## Why is GNU Important?

Without GNU:

- There would be no Bash shell.
- Basic commands like `ls`, `cp`, and `mv` would not exist.
- Developers would not have tools such as `gcc` or `gdb`.
- The Linux Kernel alone would not be a complete operating system.

---

## ❓ Interview Questions

### What is GNU?

GNU is a free and open-source collection of software tools, libraries, and utilities that work with the Linux Kernel to form a complete operating system.

---

### What does GNU stand for?

GNU stands for **"GNU's Not Unix"**, a recursive acronym.

---

### Why is the operating system called GNU/Linux?

Because the complete operating system is formed by combining **GNU tools** with the **Linux Kernel**.

---

### Why couldn't GNU become a complete operating system on its own?

GNU lacked a kernel. Although it provided essential tools and utilities, it required a kernel to manage hardware resources.

---

### Why couldn't the Linux Kernel become a complete operating system on its own?

The Linux Kernel only manages hardware resources. It requires user-space tools, libraries, shells, and utilities (provided by GNU) to become a usable operating system.

---

## ✅ Key Takeaways

- GNU is a collection of free and open-source software tools.
- Richard Stallman started the GNU Project in **1983**.
- GNU provides shells, compilers, libraries, and core utilities.
- The Linux Kernel manages hardware resources.
- GNU + Linux Kernel = **GNU/Linux**, a complete operating system.

---

## ⭐ Revision Summary

| Concept | Remember |
| :--- | :--- |
| GNU | Collection of software tools and utilities |
| Founder | Richard Stallman |
| Started | 1983 |
| Linux | Kernel |
| GNU + Linux | Complete Operating System (GNU/Linux) |
| Missing Component in GNU | Kernel |
| Missing Component in Linux | User-space tools and utilities |
