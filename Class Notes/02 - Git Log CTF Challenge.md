# 🔑 Understanding Git Commit Hashes (CTF Example)

## 📖 Scenario

During a Git forensics CTF challenge, the repository appeared to have the sensitive information removed.

Viewing the commit history:

```bash
git log --oneline
```

Output:

```text
8dc5180 remove sensitive info
87b85d7 create flag
```

At first glance, the latest version no longer contained the flag.

However, Git stores the complete history of every commit.

---

# 📸 What is a Commit?

A **commit** is a snapshot of your project at a specific point in time.

Every time changes are committed, Git saves the current state of the repository.

For this challenge, the history looked like this:

```text
Commit 1
│
├── Created message.txt
├── Added the flag
│
▼
Commit 2
│
├── Removed the sensitive information
│
▼
Current Version
```

Each snapshot has its own unique identifier called a **commit hash**.

---

# 🔑 What is a Commit Hash?

A **commit hash** is a unique identifier that Git automatically assigns to every commit.

Example:

```text
87b85d7dfb839b077678611280fa023d76e017b8
```

Git often displays a shortened version:

```text
87b85d7
```

The shortened hash is usually enough to uniquely identify the commit within the repository.

---

# 🧠 Why Is It Useful?

Suppose Git only displayed commit messages:

```text
create flag
remove sensitive info
```

If multiple commits had the same message, Git wouldn't know which one you meant.

Instead, every commit has a unique hash.

For example:

```text
87b85d7 create flag
8dc5180 remove sensitive info
```

Now Git can identify the exact snapshot you want.

---

# 📜 Viewing the Commit History

Command:

```bash
git log --oneline
```

Output:

```text
8dc5180 remove sensitive info
87b85d7 create flag
```

## Breakdown

| Part | Meaning |
|------|---------|
| `8dc5180` | Commit hash (latest commit) |
| `remove sensitive info` | Commit message |
| `87b85d7` | Commit hash (previous commit) |
| `create flag` | Commit message |

From the commit messages, we can infer:

- The first commit created the flag.
- The second commit removed it.

This suggests the flag may still exist in the earlier commit.

---

# 🔍 Inspecting a Commit

Command:

```bash
git show 87b85d7
```

Git uses the commit hash to locate that exact snapshot and display its contents.

Output:

```diff
commit 87b85d7dfb839b077678611280fa023d76e017b8
Author: picoCTF <ops@picoctf.com>

    create flag

diff --git a/message.txt b/message.txt

+picoCTF{s@n1t1z3_ea83ff2a}
```

The line beginning with `+` indicates content that was **added** in that commit.

That added line contained the flag.

---

# 🤔 Why Was the Flag Still There?

Although the latest commit removed the sensitive information, Git preserves previous commits.

Repository history:

```text
87b85d7
│
├── message.txt
│      picoCTF{s@n1t1z3_ea83ff2a}
│
▼
8dc5180
│
├── Removed the flag
│
▼
Current Version
```

The latest version no longer has the flag, but the earlier snapshot still contains it.

By referencing the earlier commit hash, Git reconstructed that snapshot.

---

# 🎯 Why This Matters

A commit hash allows Git to retrieve a specific version of the repository.

Using the commit hash, you can:

- View old versions of files.
- Recover deleted content.
- Compare different snapshots.
- Investigate repository history.

In this challenge, the commit hash was the key to recovering information that had been removed later.

---

# ⭐ Quick Revision

| Command | Purpose |
|---------|---------|
| `git log --oneline` | View a compact commit history |
| `git show <commit-hash>` | Display the contents and changes of a specific commit |

---

# 💡 Key Takeaways

- A **commit** is a snapshot of a project.
- Every commit has a unique **commit hash**.
- Git displays a shortened version of the hash for convenience.
- The commit hash lets Git locate an exact snapshot in the repository's history.
- Deleting a file in a later commit does **not** remove it from earlier commits.
- In Git forensics and CTFs, inspecting older commits can reveal deleted or hidden information.
