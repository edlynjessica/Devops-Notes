# 🚩 Bandit Level 06 — Searching the Entire Server

## 🎯 Objective

Find the password for **Bandit Level 07**.

The password is stored **somewhere on the server** and has all of the following properties:

- Owned by user **bandit7**
- Owned by group **bandit6**
- Exactly **33 bytes** in size

---

# 📖 Concept

Unlike the previous level, the file is **not** located inside your home directory.

It could be **anywhere on the server**, so we must search the **entire Linux file system**.

The root directory (`/`) is the starting point of the entire file system.

```text
/
├── home
├── etc
├── var
├── usr
├── tmp
└── ...
```

Searching from `/` means searching everywhere.

---

# 💻 Command Used

```bash
find / -type f -user bandit7 -group bandit6 -size 33c
```

---

## Command Breakdown

| Part | Meaning |
| :--- | :--- |
| `find` | Search command |
| `/` | Start searching from the root (entire file system) |
| `-type f` | Search only for files |
| `-user bandit7` | File must be owned by user `bandit7` |
| `-group bandit6` | File must belong to group `bandit6` |
| `-size 33c` | File must be exactly **33 bytes** |

---

# 📖 New `find` Options

## `-user`

Filters files owned by a specific user.

```bash
find / -user bandit7
```

---

## `-group`

Filters files belonging to a specific group.

```bash
find / -group bandit6
```

---

## Combining Conditions

One of the biggest strengths of `find` is that multiple conditions can be combined.

```bash
find / -type f -user bandit7 -group bandit6 -size 33c
```

This tells Linux:

- Search the entire file system
- Only regular files
- Owned by `bandit7`
- Group `bandit6`
- Exactly 33 bytes

Only files matching **all** the conditions are displayed.

---

# ⚠️ Permission Denied

While searching, many messages appeared like:

```text
find: '/root': Permission denied
```

This is **normal**.

`find` attempts to search every directory.

If the current user (`bandit6`) does not have permission to enter a directory, Linux blocks access and displays **Permission denied**.

The search **continues** in other directories.

These messages do **not** mean the command failed.

---

# 📂 Search Result

The command returned:

```text
/var/lib/dpkg/info/bandit7.password
```

---

# 📂 Read the Password

Use `cat` to display the file contents.

```bash
cat /var/lib/dpkg/info/bandit7.password
```

This displayed the password for Bandit Level 07.

---

# 🧠 What I Learned

- `find` can search the entire Linux file system.
- `/` represents the root of the Linux file system.
- `-user` filters by file owner.
- `-group` filters by group ownership.
- Multiple search conditions can be combined into a single command.
- Permission denied messages are expected when searching system directories.

---

# 📝 Key Observations

- `find .` searches only the current directory and its subdirectories.
- `find /` searches the entire server.
- The search continues even if some directories cannot be accessed.
- Linux file ownership can be used as a search condition.

---

# 🧠 Quick Revision

### Why did we use `find /` instead of `find .`?

Because the file could be **anywhere on the server**, not just inside the current directory.

---

### What does `-user bandit7` do?

Searches for files owned by the user **bandit7**.

---

### What does `-group bandit6` do?

Searches for files belonging to the group **bandit6**.

---

### What does `-size 33c` mean?

Search for files that are exactly **33 bytes**.

---

### Why did "Permission denied" messages appear?

The current user (`bandit6`) does not have permission to access certain directories. `find` skips those directories and continues searching elsewhere.

---

# ✅ Level Checklist

- [x] Learned to search from the root directory (`/`).
- [x] Learned the `-user` option.
- [x] Learned the `-group` option.
- [x] Combined multiple search filters.
- [x] Understood why "Permission denied" messages appear.
- [x] Located the password file.
- [x] Read the password using `cat`.
- [x] Obtained the password for Bandit Level 07.

➡️ **Next Level:** Log in as `bandit7` and solve **Bandit Level 07 → Level 08**.
