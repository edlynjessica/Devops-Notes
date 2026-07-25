# ⌨️ Basic Linux Commands

## Overview

Linux is primarily operated through the **Command Line Interface (CLI)**.

Commands are entered in the **Terminal**, interpreted by the **Shell**, and executed by the **Linux Kernel**.

Most Linux commands follow the same general syntax:

```text
command [options] [arguments]
```

Example:

```bash
ls -l Downloads
```

- **Command:** `ls`
- **Option:** `-l`
- **Argument:** `Downloads`

---

# 📂 pwd

### What is it?

`pwd` stands for **Print Working Directory**.

It displays the **absolute path** of your current directory.

### Syntax

```bash
pwd
```

### Example

```bash
$ pwd
/home/edlyn/Documents
```

### When to Use

- To know your current location in the file system.
- Before navigating to another directory.

---

# 📁 ls

### What is it?

`ls` stands for **List**.

It displays the files and folders inside the current directory.

### Syntax

```bash
ls
```

### Common Options

| Option | Description |
| :--- | :--- |
| `-l` | Long listing format |
| `-a` | Show hidden files |
| `-la` | Long listing including hidden files |

### Example

```bash
$ ls
Documents  Downloads  Pictures
```

### When to Use

- To view the contents of a directory.

---

# 📁 cd

### What is it?

`cd` stands for **Change Directory**.

It is used to move from one directory to another.

### Syntax

```bash
cd directory_name
```

### Examples

Move into a directory:

```bash
cd Documents
```

Move to the home directory:

```bash
cd
```

Move back one directory:

```bash
cd ..
```

### When to Use

- To navigate through the Linux file system.

---

# 🧹 clear

### What is it?

`clear` clears the terminal screen.

It does **not** delete any files or commands—it only removes the displayed output from the terminal.

### Syntax

```bash
clear
```

### Example

```bash
clear
```

### When to Use

- To keep the terminal clean and organized.

---

# 👤 whoami

### What is it?

`whoami` displays the username of the currently logged-in user.

### Syntax

```bash
whoami
```

### Example

```bash
$ whoami
edlyn
```

### When to Use

- To verify which user account is currently active.

---

# 🖥️ cat

### Purpose

Displays the contents of a file.

### Syntax

cat <filename>

### Example

cat readme

### Output

Displays the contents of the file on the terminal.

### Common Uses

- Read text files
- View configuration files
- Concatenate multiple files

# 📌 Summary

| Command | Purpose |
| :--- | :--- |
| `pwd` | Display the current directory |
| `ls` | List files and folders |
| `cd` | Change the current directory |
| `clear` | Clear the terminal screen |
| `whoami` | Display the current username |
