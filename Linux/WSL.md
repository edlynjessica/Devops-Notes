# WSL Prompt Breakdown

When you open Ubuntu in WSL, you'll usually see a prompt similar to:

```text
edlyn_jessica@Ed:~$
```

Each part of the prompt has a specific meaning:

```text
edlyn_jessica@Ed:~$
│               │  │ │
│               │  │ └── $ → Normal user prompt
│               │  └──── ~ → Home directory (/home/edlyn_jessica)
│               └─────── Ed → Hostname (computer name)
└──────────────── edlyn_jessica → Linux username
```

---

# 1. Linux Username

**Value:**

```text
edlyn_jessica
```

This is your Linux user account.

- Created during Ubuntu installation.
- Used to log in to your Linux environment.
- Owns your personal files and directories.

### Check your current user

```bash
whoami
```

**Output**

```text
edlyn_jessica
```

---

# 2. Hostname

**Value:**

```text
Ed
```

The **hostname** is your computer's name on the network.

Think of it as the computer's identity.

### Check your hostname

```bash
hostname
```

**Example Output**

```text
Ed
```

---

# 3. Home Directory (`~`)

The **tilde (`~`)** is a shortcut that represents your **home directory**.

For your account:

```text
/home/edlyn_jessica
```

This is where you should store:

- Projects
- Bash scripts
- Git repositories
- DevOps practice files

### Check your current directory

```bash
pwd
```

**Output**

```text
/home/edlyn_jessica
```

### Go to your home directory

```bash
cd ~
```

or simply:

```bash
cd
```

---

# 4. Prompt Symbol

## `$` — Normal User

A dollar sign (`$`) indicates you're logged in as a **regular user**.

Example:

```text
edlyn_jessica@Ed:~$
```

A normal user has limited permissions and uses `sudo` when administrative privileges are needed.

---

## `#` — Root User

A hash (`#`) indicates you're logged in as the **root (administrator)** user.

Example:

```text
root@Ed:~#
```

The root user has unrestricted access to the system.

> **Note:** Be careful when working as `root`, since commands can affect the entire operating system.

---

# Prompt Examples

### In your Linux home directory

```text
edlyn_jessica@Ed:~$
```

---

### Inside your Windows Documents folder

```text
edlyn_jessica@Ed:/mnt/c/Users/Edlyn Jessica/Documents$
```

---

### Logged in as the root user

```text
root@Ed:~#
```

---

# Useful Commands

```bash
whoami      # Display the current user
hostname    # Display the computer's hostname
pwd         # Print the current working directory
cd ~        # Go to the home directory
cd          # Also goes to the home directory
ls          # List files and folders
```

---

# Quick Summary

| Prompt Part | Meaning |
|-------------|---------|
| `edlyn_jessica` | Linux username |
| `Ed` | Hostname (computer name) |
| `~` | Home directory (`/home/edlyn_jessica`) |
| `$` | Normal user |
| `#` | Root (administrator) |

---

## Example Prompt

```text
edlyn_jessica@Ed:~$
```

Read it as:

> **User:** `edlyn_jessica`  
> **Computer:** `Ed`  
> **Current Location:** Home directory (`~`)  
> **Permission Level:** Normal user (`$`)
