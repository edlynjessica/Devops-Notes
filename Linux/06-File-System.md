# 📂 Linux File System

## What is a File System?

A **File System** is the method an operating system uses to **store, organize, name, and retrieve files and directories** on a storage device.

Without a file system:

- Files would have no names.
- The operating system wouldn't know where data is stored.
- Creating, locating, or managing files would be impossible.

> 💡 Think of a file system as a library. Files are books, directories are shelves, and the file system is the catalog that organizes everything.

---

# 🌳 Linux Directory Hierarchy

Unlike Windows, which uses multiple drives such as `C:\` and `D:\`, Linux uses a **single hierarchical directory structure**.

Everything starts from the **Root Directory**:

```text
/
```

All files and directories branch from this single location.

```text
                /
      ┌─────────┼─────────┐
    home       etc       var
      │          │         │
    edlyn      configs    logs
```

---

# 📁 Common Linux Directories

## `/` — Root Directory

The **Root Directory** is the top-most directory in Linux.

Every file and directory exists somewhere under `/`.

Example:

```text
/
├── home
├── root
├── etc
├── usr
├── var
└── tmp
```

---

## `/home`

Contains the **home directories of normal users**.

Examples:

```text
/home/edlyn
/home/bandit5
```

This is where users typically store their personal files such as documents, downloads, pictures, and projects.

> 💡 In Bandit, you logged into directories like `/home/bandit5`.

---

## `/root`

The home directory of the **root (administrator)** user.

Do **not** confuse this with the Root Directory (`/`).

```text
/
├── home
├── root
```

- `/` → Top of the file system.
- `/root` → Home directory of the administrator.

---

## `/etc`

Contains **system configuration files**.

Examples include:

- Network configuration
- User account information
- Hostname
- SSH configuration

Think of it as the **Settings folder** for Linux.

---

## `/bin`

`bin` stands for **Binary**.

Contains essential executable programs required for basic system operation.

Examples:

```text
ls
cat
cp
mv
rm
pwd
```

These commands are executed when you type them in the terminal.

---

## `/usr`

Historically stands for **Unix System Resources**.

Contains:

- Applications
- Libraries
- Documentation
- Additional executable programs

Most installed software is located here.

---

## `/var`

`var` stands for **Variable**.

Stores files that frequently change while the system is running.

Examples:

- Log files
- Cache
- Mail
- Databases

> 💡 In Bandit Level 6, the password was found in:

```text
/var/lib/dpkg/info/
```

---

## `/tmp`

Stores **temporary files** created by programs.

Examples:

- Installation files
- Temporary downloads
- Application cache

The operating system may automatically remove files from this directory.

---

# 📍 Absolute vs Relative Paths

## Absolute Path

An **absolute path** starts from the Root Directory (`/`).

Example:

```text
/home/edlyn/Documents
```

It always points to the same location, regardless of the current working directory.

---

## Relative Path

A **relative path** is interpreted based on the **current working directory**.

Suppose the current directory is:

```text
/home/edlyn
```

Then:

```text
Documents
```

is a relative path.

It depends on where you are currently located.

---

# 📌 Special Directories

## `.` (Current Directory)

Represents the **current working directory**.

Example:

```bash
find .
```

Searches within the current directory and all its subdirectories.

---

## `..` (Parent Directory)

Represents the **parent directory**.

Example:

```bash
cd ..
```

Moves one directory up.

---

# 👻 Hidden Files

In Linux, files and directories whose names begin with a dot (`.`) are **hidden** by default.

Examples:

```text
.bashrc
.profile
.secret
```

To display hidden files:

```bash
ls -a
```

> 💡 In Bandit Level 3, `ls -a` was used to reveal the hidden password file.

---

# 🔄 Linux vs Windows File System

| Linux | Windows |
| :--- | :--- |
| Single directory hierarchy | Multiple drives (`C:\`, `D:\`) |
| Everything starts from `/` | Each drive has its own root |
| Uses `/` as the path separator | Uses `\` as the path separator |

---

# 📌 Quick Revision

| Directory | Purpose |
| :--- | :--- |
| `/` | Root of the Linux file system |
| `/home` | Home directories of normal users |
| `/root` | Home directory of the root user |
| `/etc` | System configuration files |
| `/bin` | Essential executable programs |
| `/usr` | Applications, libraries, and documentation |
| `/var` | Frequently changing data (logs, cache, databases) |
| `/tmp` | Temporary files |

---

# 📝 Key Takeaways

- Linux uses a **single hierarchical file system** starting from the Root Directory (`/`).
- Every file and directory exists somewhere under `/`.
- Normal users have home directories inside `/home`, while the administrator's home directory is `/root`.
- Configuration files are stored in `/etc`.
- Essential commands are stored in `/bin`.
- Frequently changing data is stored in `/var`.
- Temporary files are stored in `/tmp`.
- Absolute paths begin with `/`, whereas relative paths depend on the current working directory.
- Hidden files begin with a dot (`.`) and can be viewed using `ls -a`.
