# 🚩 Bandit Level 08 — Finding a Unique Line with `sort` and `uniq`

## 🎯 Objective

Find the password for **Bandit Level 09**.

The password is stored in the file `data.txt` and is the **only line of text that occurs exactly once**.

---

# 📖 Concept

In this level, the password is hidden among many repeated lines.

The file contains:

- Many lines that appear multiple times.
- One line that appears only once.

The challenge is to identify that single unique line.

Linux provides the `sort` and `uniq` commands to solve this efficiently.

---

# 💻 Command Used

```bash
sort data.txt | uniq -u
```

## Command Breakdown

| Part | Meaning |
| :--- | :--- |
| `sort` | Sorts the lines of a file |
| `data.txt` | The file containing the data |
| `\|` | Sends the output of one command to another |
| `uniq -u` | Displays only lines that appear exactly once |

---

# 📖 What is `sort`?

`sort` is a Linux command used to arrange lines of text in a specific order.

### Example

Before sorting:

```text
banana
apple
orange
apple
```

Command:

```bash
sort file.txt
```

Output:

```text
apple
apple
banana
orange
```

Sorting places duplicate lines next to each other, which allows `uniq` to detect them.

---

# 📖 What is `uniq`?

`uniq` is a Linux command used to detect or remove repeated lines.

However, `uniq` only checks **consecutive duplicate lines**.

### Example

Input:

```text
apple
banana
apple
```

Running:

```bash
uniq file.txt
```

will not remove both `apple` entries because they are not next to each other.

Output:

```text
apple
banana
apple
```

That is why we use:

```bash
sort file.txt | uniq
```

First:

- `sort` groups identical lines together.
- `uniq` can then correctly identify duplicates.

---

# 📖 What does `uniq -u` do?

The `-u` option means **unique only**.

It displays only lines that appear exactly once.

### Example

Input:

```text
apple
apple
banana
orange
orange
```

Command:

```bash
sort file.txt | uniq -u
```

Output:

```text
banana
```

Because `banana` is the only line that occurs once.

---

# 💻 Solution Steps

## Step 1: Check the file

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

## Step 2: Find the unique line

Run:

```bash
sort data.txt | uniq -u
```

The output will be the password for the next level.

---

# 🧠 Understanding the Pipe Operator (`|`)

The pipe operator connects multiple Linux commands.

## Syntax

```bash
command1 | command2
```

The output of `command1` becomes the input of `command2`.

### Example

```bash
cat file.txt | grep hello
```

First:

```bash
cat file.txt
```

reads the file.

Then:

```bash
grep hello
```

searches for `"hello"` in the output.

Pipes allow small commands to be combined into powerful workflows.

---

# 🧠 Mistake I Made

Initially, I tried viewing the file directly:

```bash
cat data.txt
```

Since the file contained a huge amount of text, the terminal printed many lines.

Instead of manually searching through the file, Linux commands can process the data automatically.

The correct approach was:

```bash
sort data.txt | uniq -u
```

---

# 🧠 Difference Between `sort` and `uniq`

| `sort` | `uniq` |
| :--- | :--- |
| Arranges lines in order | Detects duplicate lines |
| Groups identical lines together | Removes or displays repeated lines |
| Usually used before `uniq` | Works best after sorting |

---

# 🧠 What I Learned

- `sort` arranges text lines alphabetically.
- `uniq` identifies duplicate lines.
- `uniq -u` finds lines that occur only once.
- The pipe operator (`|`) connects multiple commands.
- Linux commands can be combined to perform powerful text processing.

---

# 📝 Key Observations

- `uniq` alone may not work correctly if duplicates are scattered.
- Always use `sort` before `uniq` when searching for duplicates.
- Pipes allow multiple small commands to work together efficiently.

---

# 🧠 Quick Revision

### What command finds the unique line in this level?

```bash
sort data.txt | uniq -u
```

### Why is `sort` required before `uniq`?

Because `uniq` only detects duplicates when they appear next to each other.

### What does `uniq -u` do?

It prints only lines that occur exactly once.

### What does `|` do in Linux?

It sends the output of one command as input to another command.

---

# ✅ Level Checklist

- [x] Learned the `sort` command.
- [x] Learned how `uniq` detects duplicate lines.
- [x] Used `uniq -u` to find a unique line.
- [x] Learned how pipes connect Linux commands.
- [x] Obtained the password for Bandit Level 09.

---

➡️ **Next Level:** Log in as `bandit9` and solve **Bandit Level 09 → Level 10**.

---

# 🚀 DevOps Relevance

This level introduces some of the most commonly used Linux text-processing tools in DevOps.

Commands like:

- `sort`
- `uniq`
- `grep`
- `awk`
- `cut`
- `sed`

are frequently used for:

- Analyzing logs
- Filtering server output
- Processing configuration files
- Extracting useful information from large datasets
- Automating system administration tasks

Mastering these tools is an essential Linux skill for DevOps engineers.
