# 🚩 Bandit Level 00 — Connecting via SSH

## 🎯 Objective

Log in to the Bandit server using **SSH (Secure Shell)**.

This level introduces the basics of connecting to a remote Linux machine securely.

---

# 📖 Concept

This level teaches how to connect to a remote Linux machine using **SSH**.

Instead of running Linux commands on your own computer, you connect to another computer over the Internet and execute commands there.

---

# 🔐 What is SSH?

**SSH (Secure Shell)** is a network protocol that allows you to securely connect to and control another computer over a network.

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

### Command Breakdown

| Part | Meaning |
| :--- | :--- |
| `ssh` | Starts an SSH connection |
| `bandit0` | Username on the remote server |
| `@` | Login as this user |
| `bandit.labs.overthewire.org` | Remote server address |
| `-p` | Specifies the port number |
| `2220` | SSH port used by Bandit |

---

# 🔐 First-Time Connection

The first time you connect, SSH displays:

```text
The authenticity of host ...
Are you sure you want to continue connecting (yes/no)?
```

Type:

```text
yes
```

SSH stores the server's fingerprint so it can verify the server's identity during future connections.

---

# 🧠 What Actually Happens?

```text
               YOUR COMPUTER

        👤 User
            │
            ▼
     🖥️ Terminal
            │
            │  🔒 SSH Connection
            ▼

           REMOTE SERVER

      🐚 Shell (Bash)
            │
            ▼
      📞 System Calls
            │
            ▼
      🧠 Linux Kernel
            │
            ▼
        💻 Hardware
```

Your **Terminal** remains on your computer.

The **Shell**, **Kernel**, and **Hardware** belong to the remote Bandit server.

All commands are executed on the remote machine.

---

# 💻 Commands Used

## 📂 whoami

### Purpose

Displays the username of the currently logged-in user.

### Command

```bash
whoami
```

### Output

```text
bandit0
```

---

## 📂 pwd

### Purpose

Displays the absolute path of the current working directory.

### Command

```bash
pwd
```

### Output

```text
/home/bandit0
```

---

## 📂 ls

### Purpose

Lists the files and directories in the current directory.

### Command

```bash
ls
```

### Output

```text
readme
```

---

## 📂 cat

### Purpose

Displays the contents of a file.

### Command

```bash
cat readme
```

### Output

Displays the password for the next Bandit level.

---

# 💡 What I Learned

- SSH creates a secure connection to a remote computer.
- After logging in, commands execute on the **remote Linux server**, not on my local machine.
- The Terminal accepts input and displays output.
- The Shell interprets commands.
- The Kernel communicates with the hardware.
- `cat` displays the contents of a file.

---

# 📝 Key Observations

- `whoami` returned `bandit0`, confirming the logged-in user.
- `pwd` showed `/home/bandit0`, which is the home directory on the **remote server**.
- `ls` listed the files in the current directory.
- The file `readme` contained the password for the next level.
- The password should be stored **locally**, not committed to GitHub.

---

# ✅ Level Checklist

- [x] Connected to the Bandit server using SSH.
- [x] Understood the purpose of SSH.
- [x] Verified the current user using `whoami`.
- [x] Verified the current directory using `pwd`.
- [x] Listed files using `ls`.
- [x] Read the `readme` file using `cat`.
- [x] Obtained the password for Bandit Level 01.

➡️ **Next Level:** Log in as `bandit1` and solve **Bandit Level 01 → Level 02**.
