# 🚩 Bandit Level 01 — Special File Names

## 🎯 Objective

Find the password for **Bandit Level 02**.

This level introduces working with **special filenames** in Linux.

---

# 📖 Concept

Linux allows files to have almost any name, including special characters.

In this level, the file containing the password is named:

```text
-
```

Although it looks like a symbol, **`-` is the actual filename**.

Many Linux commands interpret `-` as **standard input (stdin)** instead of a filename, which makes this level a bit tricky.

---

# 🧠 What is Standard Input (stdin)?

**Standard Input (stdin)** is the default input stream from which a program reads data.

Normally, stdin is your **keyboard**.

For many Linux commands:

```text
-
```

means:

> Read input from **stdin** instead of a file.

That's why this command:

```bash
cat -
```

does **not** read the file named `-`.

Instead, `cat` waits for keyboard input.

---

# 💻 Commands Used

## 📂 cat -

### Purpose

Attempts to display the contents of a file.

### Command

```bash
cat -
```

### What Happened?

Instead of opening the file named `-`, `cat` interpreted `-` as **standard input (stdin)** and waited for keyboard input.

---

## 📂 Ctrl + D

### Purpose

Ends **standard input (EOF)**.

### When to Use

When a command is waiting for keyboard input and you want to signal that there is no more input.


---

## 📂 cat ./-

### Purpose

Displays the contents of the file named `-`.

### Command

```bash
cat ./-
```

### Why It Works

- `.` refers to the **current directory**.
- `./-` tells Linux that `-` is a **filename**, not standard input.

This successfully displays the password for the next level.

---

## 📂 exit

### Purpose

Closes the current shell session.

### Command

```bash
exit
```

### When to Use

- Disconnect from an SSH session.
- Close the current shell.

After running `exit`, the SSH connection is terminated and you return to your local terminal.

---

# 💡 What I Learned

- Linux filenames can contain special characters.
- `-` is commonly interpreted as **standard input (stdin)** by many commands.
- `.` represents the **current directory**.
- Prefixing a filename with `./` removes ambiguity and tells Linux to treat it as a file in the current directory.
- `Ctrl + D` sends an **EOF (End of File)** signal to end standard input.
- `exit` closes the current shell or SSH session.

---

# 📝 Key Observations

- The only file in the home directory was named `-`.
- `cat -` waited for keyboard input because `-` represented stdin.
- `Ctrl + D` exited the waiting `cat` process.
- `cat ./-` correctly displayed the contents of the file.
- The password for **Bandit Level 02** was obtained successfully.

---

# 🧠 Quick Revision

### What does `-` represent?

It usually represents **standard input (stdin)** for many Linux commands.

---

### What does `.` represent?

The current directory.

---

### Why does `cat -` not work here?

Because `cat` interprets `-` as stdin instead of a filename.

---

### Why does `cat ./-` work?

Because `./` specifies that `-` is a file in the current directory.

---

### What does `exit` do?

Closes the current shell or SSH session and returns to the local terminal.

---

# ✅ Level Checklist

- [x] Logged in as `bandit1`.
- [x] Listed files using `ls`.
- [x] Understood why `cat -` did not work.
- [x] Learned about **standard input (stdin)**.
- [x] Used `Ctrl + D` to exit stdin.
- [x] Used `cat ./-` to read the file.
- [x] Obtained the password for Bandit Level 02.

➡️ **Next Level:** Log in as `bandit2` and solve **Bandit Level 02 → Level 03**.
