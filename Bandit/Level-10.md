# 🚩 Bandit Level 10 - Base64 Encoding

## 🎯 Objective

Find the password for **Bandit Level 11**.

The password is stored in the file:

```text
data.txt
```

The file contains **Base64 encoded data**.

---

# 📖 Concept

## What is Base64?

Base64 is an **encoding method** that converts binary data into a readable text format.

It uses:

- 🔤 Uppercase letters (`A-Z`)
- 🔡 Lowercase letters (`a-z`)
- 🔢 Numbers (`0-9`)
- ➕ Plus symbol (`+`)
- ➗ Slash symbol (`/`)
- `=` for padding

Example:

Original text:

```text
Hello
```

Base64 encoded:

```text
SGVsbG8=
```

Base64 makes data easier to store and transfer as text.

---

# 🔐 Encoding vs Encryption

Base64 is **not encryption**.

| Encoding | Encryption |
|---|---|
| Converts data into another format | Protects data using a key |
| No secret key required | Requires a key |
| Easily reversible | Designed for security |
| Used for data representation | Used for protecting information |

Base64 does **not hide secrets**.

Anyone can decode Base64 data back into its original form.

---

# 💻 Commands Used

## 📂 cat

### Purpose

Displays the contents of a file.

### Command

```bash
cat data.txt
```

### Output

Example:

```text
VGhlIHBhc3N3b3JkIGlz...
```

The content looks unreadable because it is Base64 encoded.

---

## 🔓 base64

### Purpose

Encodes or decodes data using Base64.

### Syntax

```bash
base64 [option] filename
```

---

## Decode Base64 Data

To decode the file:

```bash
base64 -d data.txt
```

or:

```bash
base64 --decode data.txt
```

---

# 🧩 Command Breakdown

| Part | Meaning |
|---|---|
| `base64` | Base64 utility |
| `-d` | Decode the input |
| `--decode` | Long version of decode option |
| `data.txt` | File containing encoded data |

---

# 🔍 Checking the File

First, view the contents:

```bash
cat data.txt
```

The output contains Base64 characters:

```text
VGhlIHBhc3N3b3JkIGlz...
```

This indicates that the file is encoded.

---

# 🔓 Decoding Process

The process looks like this:

```text
data.txt
    │
    ▼
Base64 encoded text
    │
    ▼
base64 -d data.txt
    │
    ▼
Original password
```

The `base64` command converts the encoded text back into its original form.

---

# 🧠 What I Learned

- Base64 is an encoding technique, not encryption.
- Encoded data can be easily reversed.
- The `base64` command can decode Base64 files.
- The `-d` option tells Linux to decode the input.
- Data formatting and data security are different concepts.

---

# 📝 Key Observations

- Base64 data often contains letters, numbers, `+`, `/`, and `=` characters.
- Encoding does not provide security.
- The same data can always be decoded back to its original form.
- Linux provides built-in tools for handling Base64 data.

---

# 🧠 Quick Revision

### What is Base64?

A method of converting binary data into readable text.

---

### Is Base64 encryption?

No.

It is only an encoding method.

---

### Which command decodes Base64?

```bash
base64 -d filename
```

---

### What does `-d` mean?

Decode.

---

### Why can Base64 be reversed?

Because encoding does not use a secret key.

---

# ✅ Level Checklist

- [x] Opened the `data.txt` file.
- [x] Identified Base64 encoded content.
- [x] Learned the difference between encoding and encryption.
- [x] Used the `base64` command.
- [x] Decoded the file using `base64 -d`.
- [x] Retrieved the password for Bandit Level 11.

➡️ **Next Level:** Log in as `bandit11` and solve **Bandit Level 11 → Level 12**.
