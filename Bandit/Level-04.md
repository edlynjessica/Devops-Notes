# 🚩 Bandit Level 04 — Human-Readable Files

## 🎯 Objective

Find the password for **Bandit Level 05**.

The password is stored in the **only human-readable file** inside the `inhere` directory.

---

# 📖 Concept

Not every file contains plain text.

A file may contain:

- 📄 Plain Text
- 🖼️ Image Data
- 🎵 Audio
- 🎥 Video
- 📦 Compressed Data
- ⚙️ Executable/Binary Data

A **human-readable file** is simply a file whose contents can be read as plain text.

Example:

```text
Hello World!
Linux is awesome.
password123
```

Binary files, on the other hand, contain machine-readable data and usually appear as unreadable characters when opened with `cat`.

---

# 💻 Commands Used

## 📂 cd

### Purpose

Changes the current working directory.

### Command

```bash
cd inhere
```

---

## 📂 ls

### Purpose

Lists the files in the current directory.

### Command

```bash
ls
```

### Output

```text
-file00
-file01
...
-file09
```

---

## 📂 file

### Purpose

Identifies the type of a file instead of displaying its contents.

### Syntax

```bash
file filename
```

### Example

```bash
file notes.txt
```

Output

```text
notes.txt: ASCII text
```

---

## ⚠️ Why `--` Again?

The filenames begin with `-`.

Linux commands usually interpret arguments beginning with `-` as command-line options.

To tell the command that the following arguments are **filenames**, we use:

```text
--
```

which means:

> Stop parsing options. Everything after this is a normal argument.

---

## ⭐ Wildcards (`*`)

Instead of checking every file individually:

```bash
file -- -file00
file -- -file01
...
```

Linux provides a wildcard:

```text
*
```

`*` matches **all files** in the current directory.

So one command checks every file:

```bash
file -- *
```

### Output

```text
-file00: data
-file01: data
-file02: data
-file03: data
-file04: data
-file05: data
-file06: OpenPGP Public Key
-file07: ASCII text
-file08: data
-file09: Motorola S-Record; binary data in text format
```

The only **human-readable** file is:

```text
-file07
```

---

## 📂 cat

### Purpose

Displays the contents of a file.

### Command

```bash
cat -- -file07
```

This displays the password for the next level.

---

# 🧠 What I Learned

- The `file` command identifies the type of a file.
- Human-readable files are usually plain text (ASCII text).
- Binary files cannot be read meaningfully using `cat`.
- `*` is a wildcard that matches all files.
- `--` tells a command to stop interpreting filenames as options.

---

# 📝 Key Observations

- `file` does **not** display file contents.
- `cat` displays the contents of a file.
- `*` expands to every matching filename before the command runs.
- Bash expands wildcards before executing the command.

---

# 🧠 Quick Revision

### What does the `file` command do?

Identifies the type of a file.

---

### What is a human-readable file?

A file containing plain text that can be read directly by humans.

---

### Why didn't we use `cat` on every file?

Because we first needed to identify which file contained readable text.

---

### What does `*` represent?

A wildcard that matches all files in the current directory.

---

### Why did we use `--`?

Because the filenames started with `-`, which commands normally interpret as options.

---

# ✅ Level Checklist

- [x] Entered the `inhere` directory.
- [x] Listed the files.
- [x] Used `file` to identify file types.
- [x] Learned how wildcards (`*`) work.
- [x] Found the only ASCII text file.
- [x] Read the password using `cat`.
- [x] Obtained the password for Bandit Level 05.

➡️ **Next Level:** Log in as `bandit5` and solve **Bandit Level 05 → Level 06**.
