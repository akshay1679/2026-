`grep` is a command-line tool used to **search for text patterns inside files**. It’s extremely common in Linux, macOS, and other Unix-like systems.

---

## 🔎 Basic Syntax

```bash
grep [options] "pattern" filename
```

Example:

```bash
grep "hello" file.txt
```

This searches for the word **hello** inside `file.txt`.

---

## 📂 Common Examples

### 1️⃣ Search in a Single File

```bash
grep "error" app.log
```

Finds lines containing `"error"` in `app.log`.

---

### 2️⃣ Case-Insensitive Search

```bash
grep -i "error" app.log
```

Matches `Error`, `ERROR`, `error`, etc.

---

### 3️⃣ Search Recursively in a Folder

```bash
grep -r "TODO" .
```

Searches for `"TODO"` in all files in the current directory and subdirectories.

---

### 4️⃣ Show Line Numbers

```bash
grep -n "main" script.py
```

Displays matching lines with their line numbers.

---

### 5️⃣ Match Whole Words Only

```bash
grep -w "cat" file.txt
```

Matches `cat` but not `category`.

---

### 6️⃣ Invert Match (Find lines that DO NOT match)

```bash
grep -v "debug" app.log
```

---

### 7️⃣ Use Regular Expressions

```bash
grep "^start" file.txt
```

Finds lines that start with `start`.

---

## ⚡ Very Common Combo

```bash
grep -rin "error" .
```

- `-r` → recursive
- `-i` → ignore case
- `-n` → show line numbers

---

If you'd like, tell me:

- Your OS (Linux/macOS?)
- What exactly you want to search for?
- In one file or a whole project?

And I’ll give you the exact command 👍