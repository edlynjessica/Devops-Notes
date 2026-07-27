# 🚩 Bandit Level 05 — Searching for Files

## 🎯 Objective

Find the password for **Bandit Level 06**.

The password is stored in a file somewhere under the `inhere` directory with the following properties:

- Human-readable
- Exactly **1033 bytes** in size
- **Not executable**

---

# 📖 Concept

When you don't know **where** a file is located, manually checking every directory is inefficient.

Linux provides the **`find`** command to search for files and directories based on different conditions such as:

- Name
- Type
- Size
- Permissions
- Owner
- And many more...

---

# 💻 Commands Used

## 📂 find

### Purpose

Searches for files and directories recursively.

### Syntax

```bash
find <starting-directory> [conditions]
```

---

### Search from the Current Directory

```bash
find .
```

- `find` → Search command
- `.` → Start searching from the current directory

This lists every file and directory inside the current directory and its subdirectories.

---

## 📂 Filter by File Type

```bash
find . -type f
```

### Breakdown

| Part | Meaning |
| :--- | :--- |
| `find` | Search command |
| `.` | Start searching here |
| `-type f` | Search only for **files** |

If you wanted only directories:

```bash
find . -type d
```

---

## 📂 Filter by File Size

```bash
find . -size 1033c
```

### Breakdown

| Part | Meaning |
| :--- | :--- |
| `-size` | Filter by file size |
| `1033c` | Exactly **1033 bytes** (`c` = bytes/characters) |

---

## 📂 Combining Multiple Conditions

One of the strengths of `find` is that multiple filters can be combined.

Command used:

```bash
find . -type f -size 1033c
```

### Output

```text
./maybehere07/.file2
```

This tells Linux to search:

- Starting from the current directory
- Only files
- Exactly 1033 bytes in size

Since only one file matched, the remaining condition (**not executable**) did not need to be checked.

---

## 📂 Hidden Files

The search result was:

```text
./maybehere07/.file2
```

Notice the filename starts with a dot (`.`).

That means it is a **hidden file**.

After entering the directory:

```bash
cd maybehere07
```

a normal `ls` did **not** display it.

Using:

```bash
ls -a
```

revealed:

```text
.file2
```

---

## 📂 cat

### Purpose

Displays the contents of a file.

### Command

```bash
cat .file2
```

This displayed the password for the next level.

---

# ⚠️ Mistake I Made

I first ran:

```bash
cat -- -file2
```

This opened a **different file**.

I forgot that:

```text
.file2
```

and

```text
-file2
```

are completely different filenames.

The correct file was the hidden file:

```text
.file2
```

---

# 🧠 What I Learned

- `find` searches recursively through directories.
- `-type f` filters only files.
- `-size 1033c` searches for files exactly **1033 bytes** in size.
- Hidden files begin with a dot (`.`).
- `ls -a` displays hidden files.
- Similar-looking filenames can refer to completely different files.

---

# 📝 Key Observations

- `find` searches recursively by default.
- Multiple search conditions can be combined in a single command.
- The `.` at the beginning of a filename is part of the filename.
- Hidden files are not shown by a normal `ls`.

---

# 🧠 Quick Revision

### What does `find` do?

Searches for files and directories recursively.

---

### What does `-type f` mean?

Search only for files.

---

### What does `1033c` mean?

A file that is exactly **1033 bytes** in size.

---

### Why didn't `ls` show `.file2`?

Because hidden files are not displayed by a normal `ls`.

---

### Are `.file2` and `-file2` the same file?

No. They are two completely different filenames.

---

### Why wasn't the "not executable" condition needed?

Because only one file matched the other search conditions.

---

# ✅ Level Checklist

- [x] Entered the `inhere` directory.
- [x] Learned the `find` command.
- [x] Filtered by file type using `-type f`.
- [x] Filtered by file size using `-size 1033c`.
- [x] Located the hidden file.
- [x] Used `ls -a` to reveal the hidden file.
- [x] Read the password using `cat`.
- [x] Obtained the password for Bandit Level 06.

➡️ **Next Level:** Log in as `bandit6` and solve **Bandit Level 06 → Level 07**.
