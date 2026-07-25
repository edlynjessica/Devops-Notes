# 🚩 Bandit Level 02 — Filenames with Spaces and Special Characters

## 🎯 Objective

Find the password for **Bandit Level 03**.

This level teaches how the shell handles **spaces** in filenames and how commands interpret **arguments beginning with `-` or `--`**.

---

# 📖 Concept

The password is stored in a file named:

```text
--spaces in this filename--
```

This filename introduces two common Linux challenges:

- Filenames containing **spaces**
- Filenames beginning with **`--`**

Understanding how the Shell and Linux commands interpret arguments is essential.

---

# 🧠 Problem 1 — Spaces in Filenames

The Shell (Bash) treats spaces as separators between arguments.

For example,

```bash
cat hello world.txt
```

Bash interprets this as:

```text
Command : cat

Argument 1 : hello
Argument 2 : world.txt
```

Instead of one filename.

---

## ✅ Solution

Wrap the filename inside quotes.

```bash
cat "hello world.txt"
```

Now Bash treats everything inside the quotes as **one single argument**.

---

# 🧠 Problem 2 — Filenames Beginning with `--`

Many Linux commands use `-` or `--` to specify command-line options.

Examples:

```bash
cat --help
ls --all
```

So when the filename starts with:

```text
--
```

the command may mistakenly interpret it as an option instead of a filename.

For example,

```bash
cat "--spaces in this filename--"
```

produces an error because `cat` thinks the filename is another command-line option.

---

## ✅ Solution

Linux provides a special marker:

```text
--
```

A standalone `--` tells the command:

> **Stop parsing command-line options. Everything after this is a normal argument.**

---

# 💻 Final Command

```bash
cat -- "--spaces in this filename--"
```

---

# 🧠 What Happens Internally?

### Step 1 — Bash (Shell)

Bash processes the command.

The quotes tell Bash:

> Treat the entire filename as a single argument.

Bash sends the following arguments to `cat`:

```text
Argument 0 → cat
Argument 1 → --
Argument 2 → --spaces in this filename--
```

Notice that the quotes disappear after Bash processes them.

---

### Step 2 — `cat`

`cat` receives the arguments.

It sees:

```text
--
```

and understands:

> Stop reading command-line options.

Everything after that is treated as a filename.

So `cat` opens:

```text
--spaces in this filename--
```

and displays its contents.

---

# 💻 Commands Used

## 📂 cat

### Purpose

Displays the contents of a file.

### Final Command

```bash
cat -- "--spaces in this filename--"
```

---

# 💡 What I Learned

- Bash splits command-line arguments using spaces.
- Double quotes (`"..."`) tell Bash to treat everything inside as one argument.
- Commands like `cat` interpret arguments beginning with `-` or `--` as options.
- A standalone `--` tells a command to stop parsing options.
- The Shell and the command process arguments independently.

---

# 📝 Key Observations

- Quotes are interpreted by **Bash (Shell)**.
- `--` is interpreted by the **command** (`cat`).
- Quotes solve the **space problem**.
- `--` solves the **option parsing problem**.

---

# 🧠 Quick Revision

### Why are quotes (`"..."`) used?

To tell the Shell that spaces belong to the filename and should not split the argument.

---

### Why is `--` used?

To tell the command to stop interpreting arguments as command-line options.

---

### Who understands quotes?

The **Shell (Bash)**.

---

### Who understands `--`?

The **command being executed** (such as `cat`, `ls`, `grep`, etc.).

---

### Why didn't this work?

```bash
cat "--spaces in this filename--"
```

Because `cat` interpreted the filename as a command-line option.

---

### Why does this work?

```bash
cat -- "--spaces in this filename--"
```

Because:

- `--` stops option parsing.
- Quotes preserve the spaces.
- `cat` correctly treats the argument as a filename.

---

# ✅ Level 2 Checklist

- [x] Logged in as `bandit2`.
- [x] Listed the files using `ls`.
- [x] Learned how Bash handles spaces.
- [x] Learned how Linux commands parse options.
- [x] Understood the purpose of quotes (`"..."`).
- [x] Understood the purpose of `--`.
- [x] Obtained the password for Bandit Level 03.

➡️ **Next Level:** Log in as `bandit3` and solve **Bandit Level 03 → Level 04**.
