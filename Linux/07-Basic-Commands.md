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

# 📌 Command Summary

| Command | Purpose |
| :--- | :--- |
| `pwd` | Display the current working directory |
| `ls` | List files and folders |
| `cd` | Change the current directory |
| `clear` | Clear the terminal screen |
| `whoami` | Display the current username |
| `cat` | Display or combine text file contents |
| `less` | View large text files one page at a time |
| `head` | Display the first few lines of a file |
| `tail` | Display the last few lines of a file |
| `file` | Identify the type of a file |
| `find` | Search for files and directories recursively |
| `grep` | Search for lines containing a pattern |
| `strings` | Display printable text from binary files |
| `sort` | Sort lines of text |
| `uniq` | Remove or identify duplicate lines |
| `wc` | Count lines, words, and characters |

---

# ✅ Options and Hyphens

Most Linux commands support **options** (also called **flags**) that modify how the command behaves.

Options are typically prefixed with a **hyphen (`-`)**.

Example:

```bash
ls -l Downloads
```

Here:

- `ls` → Command
- `-l` → Option (long listing format)
- `Downloads` → Argument

The hyphen tells the command:

> "Treat the following characters as options, not as filenames."

---

## 🔹 Single Hyphen (`-`)

A **single hyphen** is used for short options.

Examples:

```bash
ls -l
ls -a
ls -h
```

Multiple options can be combined:

```bash
ls -lah
```

Equivalent to:

```bash
ls -l -a -h
```

---

## 🔹 Double Hyphen (`--`)

A double hyphen is used for long option names.

Examples:

```bash
ls --all
ls --human-readable
```

Equivalent to:

```bash
ls -a
ls -h
```

---

## 🔹 Special `--`

A standalone `--` tells the command:

> "Stop interpreting anything after this as an option."

Useful when filenames begin with `-`.

Example:

```bash
cat -- -file
```

Without `--`, Linux may interpret `-file` as an option.

---

# 📂 pwd

### What is it?

`pwd` stands for **Print Working Directory**.

It displays the **absolute path** of the current directory.

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

- Find your current location.
- Verify your directory before navigating.

---

# 📁 ls

### What is it?

`ls` stands for **List**.

It displays files and folders inside a directory.

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
ls
```

Output:

```text
Documents  Downloads  Pictures
```

### When to Use

- View directory contents.
- Check available files.

---

# 📁 cd

### What is it?

`cd` stands for **Change Directory**.

It is used to move between directories.

### Syntax

```bash
cd directory_name
```

### Examples

Move into a directory:

```bash
cd Documents
```

Move to home directory:

```bash
cd
```

Move one directory back:

```bash
cd ..
```

### When to Use

- Navigate through the Linux file system.

---

# 🧹 clear

### What is it?

`clear` clears the terminal display.

It does **not** delete files or commands.

### Syntax

```bash
clear
```

### When to Use

- Keep the terminal clean.

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

- Verify the active user account.

---

# 🖥️ cat

### What is it?

`cat` displays the contents of files and can combine multiple files.

### Syntax

```bash
cat <filename>
```

### Examples

Read a file:

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

- Read small text files.
- Quickly inspect file contents.
- Combine files.

> 💡 For large files, use `less`.

---

# 📄 file

### What is it?

`file` identifies the **actual type of a file** by examining its contents instead of relying on the filename extension.

### Syntax

```bash
file <filename>
```

### Common Options

| Option | Description |
| :--- | :--- |
| `-i` | Display MIME type |
| `-b` | Display only the file type |

### Examples

Identify a file:

```bash
file notes.txt
```

Identify all files:

```bash
file *
```

Handle filenames beginning with `-`:

```bash
file -- *
```

### Example Output

```text
notes.txt: ASCII text
image.png: PNG image data
program: ELF executable
archive.gz: gzip compressed data
```

### When to Use

- Identify unknown files.
- Check if a file is text, binary, executable, or an image.

> 💡 **Bandit Level 04:** `file -- *` was used to find the only human-readable file.

---

# 🔎 find

### What is it?

`find` searches for files and directories recursively based on conditions like name, type, size, owner, and permissions.

Unlike `ls`, which lists a directory, `find` searches through directories and subdirectories.

---

## Syntax

```bash
find <starting-directory> [options]
```

Example:

```bash
find .
```

Searches everything inside the current directory.

---

## Common Options

### `-type`

Filters by file type.

| Option | Meaning |
| :--- | :--- |
| `f` | Regular files |
| `d` | Directories |
| `l` | Symbolic links |

Examples:

```bash
find . -type f
find . -type d
```

---

### `-name`

Search by filename.

```bash
find . -name "notes.txt"
find . -name "*.txt"
```

---

### `-iname`

Case-insensitive filename search.

```bash
find . -iname "*.jpg"
```

---

### `-size`

Search by file size.

| Suffix | Meaning |
| :--- | :--- |
| `c` | Bytes |
| `k` | KB |
| `M` | MB |
| `G` | GB |

Examples:

```bash
find . -size 1033c
find . -size +1M
find . -size -500k
```

---

### `-empty`

Find empty files and directories.

```bash
find . -empty
```

---

## Combine Conditions

Example:

```bash
find . -type f -size 1033c
```

Finds files that are exactly 1033 bytes.

---

## `find` vs `ls`

| `ls` | `find` |
| :--- | :--- |
| Lists directory contents | Searches recursively |
| Used for browsing | Used for searching |
| Limited filtering | Powerful filtering |

---

## Quick Revision

| Command | Purpose |
| :--- | :--- |
| `find .` | Search everything |
| `find . -type f` | Find files |
| `find . -type d` | Find directories |
| `find . -name "*.txt"` | Find text files |
| `find . -size 1033c` | Find files of a specific size |
| `find . -empty` | Find empty files/directories |

---

# 🔍 grep

### What is it?

`grep` (**Global Regular Expression Print**) is a Linux command used to **search for text patterns inside files**.

It searches line by line and displays matching lines.

### Syntax

```bash
grep <pattern> <filename>
```

### Example

Search for a word:

```bash
grep millionth data.txt
```

Output:

```text
millionth password123
```

### Common Options

| Option | Description |
| :--- | :--- |
| `-i` | Ignore uppercase/lowercase differences |
| `-n` | Show line numbers |
| `-r` | Search recursively inside directories |
| `-v` | Show lines that do not match |

Examples:

```bash
grep -i linux file.txt
```

```bash
grep -n password data.txt
```

```bash
grep -r "hello" .
```

### When to Use

- Search inside files.
- Find specific text in logs.
- Filter command output.

> 💡 **Bandit Level 07:** `grep millionth data.txt` was used to find the password next to the word `millionth`.

---

# 🔤 strings

### What is it?

`strings` displays **human-readable text** present inside binary files.

It is useful when a file contains hidden readable information among binary data.

### Syntax

```bash
strings <filename>
```

### Example

```bash
strings data.bin
```

Output:

```text
Linux
Password123
Hello World
```

### When to Use

- Inspect binary files.
- Find hidden text.
- Analyze executables.

> 💡 **Bandit Level 09:** `strings` was used to extract readable text from a file containing binary data.

---

# 📊 sort

### What is it?

`sort` arranges lines of text in a specific order.

By default, it sorts alphabetically.

### Syntax

```bash
sort <filename>
```

### Example

File:

```text
banana
apple
orange
```

Command:

```bash
sort fruits.txt
```

Output:

```text
apple
banana
orange
```

### Common Options

| Option | Description |
| :--- | :--- |
| `-r` | Reverse order |
| `-n` | Numeric sorting |
| `-u` | Sort and remove duplicates |

Examples:

```bash
sort -r names.txt
```

```bash
sort -n numbers.txt
```

### When to Use

- Arrange text data.
- Prepare data before using `uniq`.

---

# 🔁 uniq

### What is it?

`uniq` removes or displays **duplicate consecutive lines**.

Usually used together with `sort`.

### Syntax

```bash
uniq <filename>
```

### Example

Input:

```text
apple
apple
banana
banana
```

Command:

```bash
uniq fruits.txt
```

Output:

```text
apple
banana
```

### Common Options

| Option | Description |
| :--- | :--- |
| `-c` | Count occurrences |
| `-d` | Display only duplicates |
| `-u` | Display only unique lines |

Example:

```bash
uniq -c fruits.txt
```

Output:

```text
2 apple
2 banana
```

### When to Use

- Remove repeated lines.
- Count occurrences of values.

---

# 🔢 wc

### What is it?

`wc` (**word count**) displays the number of lines, words, and characters in a file.

### Syntax

```bash
wc <filename>
```

### Example

```bash
wc data.txt
```

Output:

```text
10 50 300 data.txt
```

Meaning:

```text
lines  words  characters
```

### Common Options

| Option | Description |
| :--- | :--- |
| `-l` | Count lines |
| `-w` | Count words |
| `-c` | Count bytes |

Examples:

```bash
wc -l data.txt
```

```bash
wc -w data.txt
```

### When to Use

- Count data.
- Analyze text files.
- Combine with pipes.

Example:

```bash
grep "error" log.txt | wc -l
```

Counts the number of error lines.

---

# 🔗 Pipes (`|`)

### What is it?

A pipe sends the **output of one command as input to another command**.

### Syntax

```bash
command1 | command2
```

### Example

```bash
cat data.txt | grep password
```

Flow:

```text
cat data.txt
      |
      ▼
grep password
      |
      ▼
Matching lines
```

### When to Use

- Combine multiple commands.
- Process output step by step.

Example:

```bash
ls | wc -l
```

Counts the number of files in a directory.
