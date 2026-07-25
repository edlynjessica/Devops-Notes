# 🐧 Linux Cheat Sheet

A quick reference for the Linux fundamentals required for DevOps, Backend Development, System Administration, and Cybersecurity.

> 💡 **Tip:** Read the detailed notes in each chapter to understand the concepts, then use this page for quick revision before interviews, tests, or coding sessions.

---

# 📚 Learning Roadmap

```
Introduction
      │
      ▼
Linux vs Windows
      │
      ▼
Linux Kernel
      │
      ▼
     GNU
      │
      ▼
Shell & Terminal
      │
      ▼
Basic Commands
      │
      ▼
File System
      │
      ▼
Permissions
      │
      ▼
     SSH
      │
      ▼
Searching & Text Processing
      │
      ▼
Pipes & Redirection
```

---

# 🏗️ Linux Command Execution Flow

One of the most important concepts in Linux is understanding what happens after you type a command.

## Overall Architecture

```text
User
   │
   ▼
Terminal
   │
   ▼
Shell (Bash)
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

## Quick Definitions

| Term | Definition |
| :--- | :--- |
| **CLI** | Command Line Interface — a text-based way to interact with the operating system. |
| **Terminal** | An application that accepts user input and displays command output. |
| **Shell** | A command-line interpreter that understands and executes commands. |
| **Bash** | The most commonly used Linux shell (Bourne Again SHell). |
| **System Call** | A request made by a program to the Linux Kernel for system-level services. |
| **Linux Kernel** | The core of the operating system that manages hardware and system resources. |
| **User Space** | The area where applications and user programs run. |
| **Kernel Space** | The protected area where the Linux Kernel executes. |

---

## Responsibilities of Each Component

| Component | Responsibility |
| :--- | :--- |
| 👤 User | Types the command |
| 🖥️ Terminal | Accepts keyboard input and displays output |
| 🐚 Shell (Bash) | Interprets commands and executes programs |
| 📞 System Calls | Request services from the Kernel |
| 🧠 Linux Kernel | Manages hardware and system resources |
| 💻 Hardware | Executes the requested operation |

---

## Example: `mkdir Projects`

| Step | Component | What Happens? |
| :--- | :--- | :--- |
| 1 | 🖥️ Terminal | Accepts keyboard input |
| 2 | 🐚 Shell (Bash) | Interprets the command "mkdir" |
| 3 | 📞 System Calls | Request the Kernel to create a directory named "Projects"|
| 4 | 🧠 Kernel | Creates the directory "Projects" in the file system |
| 5 | 🖥️ Terminal | Displays the result |

---

## Example: `ls`

```text
User
   │
   ▼
Terminal
   │
   ▼
Shell (Bash)
   │
   ▼
Runs the `ls` program
   │
   ▼
System Calls
   │
   ▼
Linux Kernel
   │
   ▼
Reads the file system
   │
   ▼
Returns the data
   │
   ▼
`ls` formats the output
   │
   ▼
Terminal displays the output
```

---

# 🧠 Core Concepts

| Concept | Remember |
| :--- | :--- |
| Linux | Linux is a **Kernel**, not a complete operating system. |
| GNU | GNU provides the tools, libraries, shell, and utilities required by users. |
| GNU/Linux | GNU + Linux Kernel = Complete Operating System |
| Terminal | Where you type commands. |
| Shell | Understands and executes commands. |
| Bash | The default shell on many Linux distributions. |
| System Calls | Bridge between programs and the Kernel. |
| Kernel | The only component that directly interacts with hardware. |

---

# ⚡ Command Syntax

Most Linux commands follow this syntax:

```text
command [options] [arguments]
```

Example:

```bash
ls -la Downloads
```

| Part | Meaning |
| :--- | :--- |
| `ls` | Command |
| `-la` | Options |
| `Downloads` | Argument |

---

# 📂 Commands Learned

| Command | Purpose |
| :--- | :--- |
| `pwd` | Print the current working directory |
| `ls` | List files and directories |
| `cd` | Change the current directory |
| `clear` | Clear the terminal screen |
| `whoami` | Display the current logged-in user |

---

# 📖 Chapters

| File | Topic |
| :--- | :--- |
| `01-Introduction.md` | Introduction to Linux |
| `02-Linux-vs-Windows.md` | Linux vs Windows |
| `03-Kernel.md` | Linux Kernel |
| `04-GNU.md` | GNU |
| `05-Shell-and-Terminal.md` | Shell, Terminal & Bash |
| `06-File-System.md` | Linux File System |
| `07-Basic-Commands.md` | Essential Linux Commands |
| `08-File-Permissions.md` | File Permissions |
| `09-SSH.md` | Secure Shell (SSH) |
| `10-Searching-and-Text-Processing.md` | Searching & Text Processing |
| `11-Pipes-and-Redirection.md` | Pipes & Redirection |

---

# ⭐ Remember

- Linux = **Kernel**
- GNU + Linux = **GNU/Linux**
- Terminal ≠ Shell
- Bash is a type of Shell.
- Applications run in **User Space**.
- The Kernel runs in **Kernel Space**.
- The Shell communicates with the Kernel using **System Calls**.
- Only the **Kernel** directly interacts with the hardware.
- Most Linux commands follow the syntax: `command [options] [arguments]`.

---

> 🐧 **Master the concepts, not just the commands.** Once you understand how Linux works internally, learning new commands becomes much easier.
