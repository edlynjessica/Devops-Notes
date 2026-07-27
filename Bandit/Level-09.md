# 🚩 Bandit Level 09 — Extracting Hidden Text with `strings`

## 🎯 Objective

Find the password for **Bandit Level 10**.

The password is stored in the file `data.txt` in one of the few **human-readable strings**, and it is preceded by several `=` characters.

---

# 📖 Concept

In previous levels, the files contained normal text that could be searched using commands like:

- `cat`
- `grep`
- `sort`
- `uniq`

However, this level introduces a file that contains a mixture of:

- Binary data
- Random characters
- Human-readable text hidden inside

Trying to read the file directly using:

```bash
cat data.txt
```

does not give useful information.

To extract readable text from a file containing binary data, Linux provides the `strings` command.

---

# 💻 Command Used

```bash
strings data.txt | grep "="
```

## Command Breakdown

| Part | Meaning |
| :--- | :--- |
| `strings` | Extracts readable text from binary files |
| `data.txt` | The file being analyzed |
| `\|` | Sends the output of one command to another |
| `grep "="` | Searches for lines containing `=` characters |

---

# 📖 What is `strings`?

`strings` is a Linux command used to extract sequences of readable characters from files.

It is useful when working with:

- Binary files
- Executable files
- Malware analysis
- Debugging
- Digital forensics

## Syntax

```bash
strings <file>
```

## Example

```bash
strings program.bin
```

Output:

```text
Hello World
config.txt
password123
```

Even though the file may contain unreadable binary content, `strings` extracts the readable portions.

---

# 💻 Solution Steps

## Step 1: Check the available files

Command:

```bash
ls
```

Output:

```text
data.txt
```

The password is stored inside this file.

---

## Step 2: Try reading the file normally

Command:

```bash
cat data.txt
```

The output contains unreadable characters because the file contains binary data.

---

## Step 3: Extract readable strings

Run:

```bash
strings data.txt
```

This displays all human-readable text hidden inside the file.

---

## Step 4: Find the password

The level tells us that the password is:

- A readable string.
- Preceded by several `=` characters.

So we filter the output:

```bash
strings data.txt | grep "="
```

Example output:

```text
==========password_here
```

The text after the `=` characters is the password.

---

# 🧠 Understanding the Pipe Operator (`|`)

The pipe operator connects multiple commands together.

## Syntax

```bash
command1 | command2
```

The output of `command1` becomes the input of `command2`.

## Example

```bash
strings data.txt | grep "="
```

### Flow

```text
data.txt
   ↓
strings
   ↓
Readable text
   ↓
grep
   ↓
Lines containing "="
```

---

# 🧠 Mistake I Made

Initially, I tried:

```bash
cat data.txt
```

Since the file contained binary data, the terminal displayed messy unreadable output.

Instead of manually searching through the file, the correct approach was:

```bash
strings data.txt | grep "="
```

This extracted only the useful information.

---

# 🧠 Difference Between `cat` and `strings`

| `cat` | `strings` |
| :--- | :--- |
| Displays the complete file content | Extracts only readable text |
| Best for normal text files | Useful for binary files |
| May show unreadable output for binary files | Filters meaningful characters |

---

# 🧠 What I Learned

- Not every file contains readable text.
- Binary files can hide useful information.
- `strings` extracts human-readable text from binary data.
- `grep` helps filter large outputs.
- Linux commands can be combined using pipes.

---

# 📝 Key Observations

- Use `cat` when working with normal text files.
- Use `strings` when dealing with unknown or binary files.
- Combining commands makes searching much faster.

Example:

```bash
strings file | grep keyword
```

---

# 🧠 Quick Revision

### What does `strings` do?

Extracts readable text from binary files.

---

### Why did `cat data.txt` fail?

Because the file contained binary data mixed with unreadable characters.

---

### What command solved this level?

```bash
strings data.txt | grep "="
```

---

### What does `grep "="` search for?

It finds lines containing the `=` character.

---

### What does the pipe (`|`) do?

It sends the output of one command as input to another command.

---

# ✅ Level Checklist

- [x] Learned how binary files can contain hidden text.
- [x] Learned the `strings` command.
- [x] Used `grep` to filter useful output.
- [x] Learned another use of the pipe operator.
- [x] Obtained the password for Bandit Level 10.

---

➡️ **Next Level:** Log in as `bandit10` and solve **Bandit Level 10 → Level 11**.
