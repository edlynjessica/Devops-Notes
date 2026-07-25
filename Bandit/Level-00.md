# 🚩 Bandit Level 0 — Connecting via SSH

## 🎯 Objective

Log in to the Bandit server using **SSH (Secure Shell)**.

This level introduces the basics of connecting to a remote Linux machine securely.

---

# 📖 What is SSH?

**SSH (Secure Shell)** is a network protocol that allows you to **securely connect to and control another computer over a network.**

It provides an encrypted communication channel between your computer and the remote machine.

> Think of SSH as opening a secure terminal on another computer.

---

# 🖥️ Connection Details

| Field | Value |
| :--- | :--- |
| Host | `bandit.labs.overthewire.org` |
| Port | `2220` |
| Username | `bandit0` |
| Password | `bandit0` |

---

# 💻 SSH Command

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

### Breakdown

| Part | Meaning |
| :--- | :--- |
| `ssh` | Secure Shell command |
| `bandit0` | Username |
| `@` | Login as this user on the remote machine |
| `bandit.labs.overthewire.org` | Remote server |
| `-p` | Specifies the port number |
| `2220` | SSH port used by Bandit |

---

# 🔐 First Connection

On the first connection, SSH may display:

```text
The authenticity of host ...
Are you sure you want to continue connecting (yes/no)?
```

Type:

```text
yes
```

This stores the server's fingerprint so future connections can verify you're talking to the same server.

---

# ⚠️ Password Input

When entering a password in a Linux terminal:

- No characters are displayed.
- No `*` or `•` appear.
- This is normal and improves security.

---

# 🧠 What Actually Happens?

```text
Your Keyboard
      │
      ▼
Your Terminal
      │
      │ 🔒 Encrypted SSH Connection
      ▼
Bandit Server
      │
      ▼
Shell (Bash)
      │
      ▼
Linux Kernel
      │
      ▼
Hardware
```

Your computer provides the **keyboard and terminal**, while the **remote server** executes the commands.

---

# 🔍 Verification Commands

```bash
whoami
```

Expected output:

```text
bandit0
```

---

```bash
pwd
```

Expected output:

```text
/home/bandit0
```

---

```bash
ls
```

Expected output:

```text
readme
```

---

# 📝 Observations

- `whoami` displays the current logged-in user.
- `pwd` shows the current working directory on the **remote server**.
- `ls` lists the files in the current directory.
- The file `readme` contains the password for the next level.

---

# 💡 Key Concepts Learned

- SSH provides a **secure, encrypted** connection to a remote computer.
- After connecting, commands execute on the **remote Linux server**, not on your local machine.
- The Terminal accepts input and displays output.
- The Shell interprets commands.
- The Kernel performs the requested operations.

---

# 🧠 Architecture

```text
User
   │
   ▼
Terminal
   │
   │ 🔒 SSH
   ▼
Remote Shell (Bash)
   │
   ▼
System Calls
   │
   ▼
Linux Kernel
   │
   ▼
Hardware
```

---

# ✅ Level Status

- [x] Connected to the Bandit server using SSH.
- [x] Verified the current user.
- [x] Verified the working directory.
- [x] Listed the files in the home directory.

➡️ **Next:** Read the `readme` file to obtain the password for **Bandit Level 1**.
