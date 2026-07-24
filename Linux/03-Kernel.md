# 🧠 Linux Kernel

## Overview

The **Kernel** is the core component of an operating system. It acts as a bridge between **applications (software)** and the **computer hardware**, ensuring that programs can safely and efficiently use hardware resources.

> 💡 **Key Point**
>
> The **Linux Kernel** is the reason the operating system is called **Linux**.

---

## What is a Kernel?

A **Kernel** is the central part of an operating system that manages communication between software and hardware.

Applications cannot directly access hardware. Instead, they request services from the kernel, which interacts with the hardware on their behalf.

### Communication Flow

```text
 User {types ls to list directories}
   │
   ▼
Terminal {it catches the keystrokes and It forwards the command to the shell}
   │
   ▼
 Shell (Bash) {Bash reads it and Bash starts the ls program.}
- It cannot access the disk directly. So it makes a system call to the kernel.
   │
   ▼
System Call
   │
   ▼
 Kernel
- checks permissions
- accesses the file system
- reads the directory entries from storage
   │
   ▼
Hardware {The SSD/HDD returns the requested data.}
   │
   ▼
 Kernel {The kernel sends the directory information back to the ls program.}
   │
   ▼
 Shell {The ls program formats the output.}
   │
   ▼
Terminal {The terminal displays the directories (output)}
   │
   ▼
  User
```

---

## Why is Linux Called "Linux"?

In 1991, **Linus Torvalds** developed the **Linux Kernel**.

Originally, the term **Linux** referred only to the **kernel**, not the complete operating system.

A complete operating system is formed by combining:

```text
Linux Kernel
      +
GNU Tools
      =
GNU/Linux
```

This is why many people refer to the operating system as **GNU/Linux**.

---

## Responsibilities of the Kernel

The kernel is responsible for managing the computer's hardware resources.

### 1. Process Management

A **process** is a running program.

The kernel:

- Creates processes
- Schedules CPU time
- Switches between running processes

---

### 2. Memory Management

The kernel allocates and manages RAM for different applications.

It ensures that one application cannot overwrite another application's memory.

---

### 3. Device Management

The kernel communicates with hardware devices through **device drivers**.

Examples include:

- Keyboard
- Mouse
- Printer
- SSD/HDD
- Network Adapter

---

### 4. File System Management

The kernel manages:

- File creation
- Reading files
- Writing files
- File permissions
- Storage organization

---

### 5. Security & Permissions

The kernel enforces security by checking:

- User permissions
- File permissions
- Device access
- Process privileges

---

## User Space vs Kernel Space

Modern operating systems separate applications from the kernel to improve **security**, **stability**, and **resource management**.

```text
+--------------------------------------+
|             User Space               |
|--------------------------------------|
|  • Chrome                            |
|  • VS Code                           |
|  • Terminal                          |
|  • Spotify                           |
|  • Your Applications                 |
+--------------------------------------+
                 │
                 │  System Calls
                 ▼
+--------------------------------------+
|            Kernel Space              |
|--------------------------------------|
|  • Process Management                |
|  • Memory Management                 |
|  • File System Management            |
|  • Device Drivers                    |
|  • Security & Permissions            |
+--------------------------------------+
                 │
                 ▼
+--------------------------------------+
|              Hardware                |
|--------------------------------------|
|  • CPU                               |
|  • RAM                               |
|  • SSD / HDD                         |
|  • Keyboard                          |
|  • Mouse                             |
|  • Network Card                      |
+--------------------------------------+
```

### User Space

User Space is where **applications** run.

Examples include:

- Chrome
- VS Code
- Terminal
- Spotify

Applications running in User Space **cannot directly access hardware**.

---

### Kernel Space

Kernel Space is where the **Linux Kernel** runs.

It has complete access to the computer's hardware and is responsible for managing system resources.

---

## System Calls

Applications communicate with the kernel using **System Calls**.

A **System Call** is a request made by an application to the kernel for services such as:

- Reading or writing files
- Allocating memory
- Creating processes
- Communicating with hardware

> 💡 **Key Point**
>
> Applications **never communicate directly with hardware**. Every request must go through the **Kernel** using **System Calls**.

## Communication

Applications communicate with the kernel using **System Calls**.

A **System Call** is a request made by an application to the kernel for services such as:

- Reading a file
- Writing a file
- Allocating memory
- Accessing hardware

---

## Interview Questions

### What is a Kernel?

A kernel is the core component of an operating system that acts as a bridge between applications and hardware.

---

### Why is Linux called Linux?

Because **Linux** originally referred to the **Linux Kernel**, developed by Linus Torvalds.

---

### Why do applications use System Calls?

Applications cannot directly access hardware. They use system calls to request services from the kernel.

---

### What is the difference between User Space and Kernel Space?

User Space is where applications run with limited hardware access, while Kernel Space is where the kernel runs with complete control over the system hardware.

---

### Why Can't Applications Access Hardware Directly?

Allowing every application to directly access hardware would lead to:

- Resource conflicts
- Security risks
- System crashes
- Data corruption

The kernel acts as a manager, ensuring that hardware resources are shared safely and efficiently.

---

## ✅ Key Takeaways

- The **Kernel** is the core component of an operating system.
- It acts as a bridge between **software** and **hardware**.
- Linux originally referred only to the **Linux Kernel**.
- Applications communicate with the kernel using **System Calls**.
- The kernel manages processes, memory, files, devices, and security.
- Applications run in **User Space**, while the kernel runs in **Kernel Space**.

---

## ⭐ Revision Summary

| Concept | Remember |
| :--- | :--- |
| Kernel | Core of the Operating System |
| Linux | Refers to the Linux Kernel |
| GNU + Linux | Complete Operating System (GNU/Linux) |
| User Space | Applications |
| Kernel Space | Kernel + Hardware Access |
| System Call | Communication between Applications and Kernel |
| Main Responsibilities | Process, Memory, Device, File System, Security |
