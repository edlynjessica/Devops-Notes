# 🚩 Bandit Level 07 — Searching Inside Files with `grep`

## 🎯 Objective

Find the password for **Bandit Level 08**.

The password is stored in the file `data.txt` **next to the word** `millionth`.

---

# 📖 Concept

Unlike the previous levels, we already know **which file** contains the password.

The challenge is to locate a **specific line** inside a large file.

Instead of reading the entire file manually using `cat`, Linux provides the **`grep`** command to search for text inside files.

---

# 💻 Command Used

```bash
grep millionth data.txt
```

---

## Command Breakdown

| Part | Meaning |
| :--- | :--- |
| `grep` | Searches for text matching a pattern |
| `millionth` | The word (pattern) to search for |
| `data.txt` | The file to search in |

---

# 📖 What is `grep`?

`grep` is a Linux command used to **search for lines containing a specific word or pattern** inside one or more files.

> 💡 Think of `grep` as the Linux equivalent of **Ctrl + F** for text files.

---

## Syntax

```bash
grep <pattern> <file>
```

Example:

```bash
grep hello notes.txt
```

Displays all lines containing the word `hello`.

---

# 📂 Example

Suppose `data.txt` contains:

```text
apple banana
linux commands
millionth abc123xyz
hello world
```

Running:

```bash
grep millionth data.txt
```

Output:

```text
millionth abc123xyz
```

The password is the text next to `millionth`.

---

# ⚠️ Mistake I Made

Initially, I tried:

```bash
cat data.txt
```

Since `data.txt` is very large, the terminal kept printing thousands of lines.

To stop the running command:

```text
Ctrl + C
```

This interrupts the currently running program and returns control to the terminal.

---

# 🧠 Difference Between `find` and `grep`

| `find` | `grep` |
| :--- | :--- |
| Searches for files and directories | Searches for text inside files |
| Uses properties like name, size, owner, etc. | Uses words or patterns |
| Helps locate files | Helps locate content within files |

---

# 🧠 What I Learned

- `grep` searches for text inside files.
- It prints only the lines that match the given pattern.
- `grep` is much faster than reading a large file manually.
- `Ctrl + C` stops a running command.

---

# 📝 Key Observations

- Use `find` when you don't know where a file is.
- Use `grep` when you know the file but need to find specific content inside it.
- Large files should be searched using `grep` instead of opening them with `cat`.

---

# 🧠 Quick Revision

### What does `grep` do?

Searches for lines containing a specific word or pattern inside a file.

---

### What is the syntax of `grep`?

```bash
grep <pattern> <file>
```

---

### Why was `grep` used instead of `cat`?

Because `data.txt` is very large, and `grep` directly displays only the matching line.

---

### How do you stop a running command?

Press:

```text
Ctrl + C
```

---

### What is the difference between `find` and `grep`?

`find` searches for files, while `grep` searches for text inside files.

---

# ✅ Level Checklist

- [x] Learned the `grep` command.
- [x] Searched for a specific word inside a file.
- [x] Used `grep` instead of `cat` for a large file.
- [x] Learned to stop a running command using `Ctrl + C`.
- [x] Obtained the password for Bandit Level 08.

➡️ **Next Level:** Log in as `bandit8` and solve **Bandit Level 08 → Level 09**.
