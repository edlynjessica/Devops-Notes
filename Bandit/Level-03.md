# 🚩 Bandit Level 03 — Hidden Files

## 🎯 Objective

Find the password for **Bandit Level 04**.

The password is stored in a **hidden file** inside the `inhere` directory.

---

# 📖 Concept

Linux allows files and directories to be **hidden** by starting their names with a **dot (`.`)**.

Examples:

```text
.bashrc
.profile
.gitignore
.env
```

These files are usually configuration files and are hidden from normal directory listings.

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

## 📂 ls -a

### Purpose

Lists **all** files and directories, including hidden ones.

### Command

```bash
ls -a
```

### Output

```text
.
..
...Hiding-From-You
```

### Breakdown

| Part | Meaning |
| :--- | :--- |
| `ls` | Lists files and directories |
| `-a` | Shows **all** files, including hidden files |

---

## 📂 cat

### Purpose

Displays the contents of a file.

### Command

```bash
cat ...Hiding-From-You
```

> Quotes are optional here because the filename contains **no spaces** and does **not** begin with `-`.

---

# 🧠 What I Learned

- Files beginning with `.` are considered **hidden files** in Linux.
- A normal `ls` command does **not** display hidden files.
- `ls -a` displays **all** files, including hidden ones.
- Hidden files are usually configuration files.
- Hidden files are **not protected or encrypted**—they are simply hidden from normal listings.

---

# 💡 Why Are Hidden Files Used?

Hidden files help keep directories clean by hiding configuration files that users do not need to see every time they list a directory.

Common examples include:

- `.bashrc` – Bash configuration
- `.profile` – User profile settings
- `.gitignore` – Git ignore rules
- `.env` – Environment variables

---

# 📝 Key Observations

- `.` at the beginning of a filename makes it a **hidden file**.
- `-a` stands for **all**.
- Hidden files are visible using `ls -a`.
- Hidden does **not** mean secure.

---

# 🧠 Quick Revision

### What is a hidden file?

A file whose name begins with a dot (`.`).

---

### Why doesn't `ls` show hidden files?

Because `ls` hides files beginning with `.` by default.

---

### What does `ls -a` do?

Displays **all** files and directories, including hidden ones.

---

### Are hidden files secure?

No. They are only hidden from normal directory listings.

---

# ✅ Level Checklist

- [x] Entered the `inhere` directory.
- [x] Used `ls -a` to display hidden files.
- [x] Read the hidden file using `cat`.
- [x] Obtained the password for Bandit Level 04.

➡️ **Next Level:** Log in as `bandit4` and solve **Bandit Level 04 → Level 05**.
