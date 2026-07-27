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

# ✅ Options and Hyphens

Most Linux commands support **options** (also called **flags**) that modify how the command behaves.

Options are typically prefixed with a **hyphen (`-`)**.

For example:

```bash
ls -l Downloads
```

Here:

- `ls` → Command
- `-l` → Option (long listing format)
- `Downloads` → Argument

The hyphen tells the command:

> "Treat the following character(s) as an option, not as a filename or argument."

## 🔹 Single Hyphen (`-`)

A **single hyphen** is used for **single-letter options**.

Examples:

```bash
ls -l
ls -a
ls -h
```

Multiple single-letter options can be combined:

```bash
ls -lah
```

This is equivalent to:

```bash
ls -l -a -h
```

## 🔹 Double Hyphen (`--`)

A **double hyphen** is typically used for **long, descriptive option names**.

Examples:

```bash
ls --all
ls --human-readable
```

These are equivalent to:

```bash
ls -a
ls -h
```

## 🔹 The Special `--`

A standalone `--` tells the command:

> "Stop interpreting anything after this as an option."

This is useful when a filename begins with a hyphen.

Example:

```bash
ls -- -file
```

Without `--`, `ls` would assume `-file` is an option instead of a filename.

> **Note:** The `-` and `--` syntax is a long-standing Unix convention followed by most Linux commands, making command-line usage consistent across different tools.

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

Displays the contents of text files and can combine multiple files.

### Syntax

```bash
cat <filename>
```

### Example

```bash
cat readme.txt
```

### Output

Displays the contents of `readme.txt` in the terminal.

### Common Uses

Read a text file:

```bash
cat notes.txt
```

Read multiple files:

```bash
cat file1.txt file2.txt
```

Display line numbers:

```bash
cat -n notes.txt
```

### When to Use

- Read small text files
- View configuration files
- Concatenate multiple files
- Quickly inspect file contents

> **Tip:** For large files, use `less filename` for easier scrolling.

---

# 📌 Summary

| Command | Purpose |
|--------|---------|
| `pwd` | Display the current directory |
| `ls` | List files and folders |
| `cd` | Change the current directory |
| `clear` | Clear the terminal screen |
| `whoami` | Display the current username |
| `cat` | Display or combine text file contents |
