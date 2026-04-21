
`chown` and `chgrp` are Linux/Unix commands used to change **ownership** and **group ownership** of files and directories.

---

# 1. `chown` → Change Owner

Syntax:

```bash
chown user file
```

Example:

```bash
chown john report.txt
```

This changes the owner of `report.txt` to user **john**.

### What happens?

Every file in Linux has:

- an **owner** (a user)
    
- a **group** (a set of users)
    

When you use `chown`, you change who “owns” that file.

---

## Change owner and group together

Syntax:

```bash
chown user:group file
```

Example:

```bash
chown john:developers report.txt
```

This changes:

- owner → john
    
- group → developers
    

---

## Change ownership recursively

Syntax:

```bash
chown -R user directory
```

Example:

```bash
chown -R john project/
```

This changes ownership of:

- the folder `project/`
    
- all files inside it
    
- all subfolders inside it
    

`-R` means **Recursive**

---

# 2. `chgrp` → Change Group

Syntax:

```bash
chgrp group file
```

Example:

```bash
chgrp developers report.txt
```

This changes only the **group ownership** of the file.

Owner stays the same.

---

# Easy Difference

|Command|Changes|
|---|---|
|`chown`|Owner (and optionally group)|
|`chgrp`|Only group|

---

# Example with `ls -l`

Suppose:

```bash
-rw-r--r-- 1 mike staff 500 Jul 10 file.txt
```

Here:

- owner = mike
    
- group = staff
    

After:

```bash
chown john file.txt
```

it becomes:

```bash
-rw-r--r-- 1 john staff 500 Jul 10 file.txt
```

After:

```bash
chgrp developers file.txt
```

it becomes:

```bash
-rw-r--r-- 1 john developers 500 Jul 10 file.txt
```

---

# Important Note

Usually only:

- root user
    
- or superuser using `sudo`
    

can change ownership.

Example:

```bash
sudo chown john file.txt
```

---

# Memory Trick

### `chown`

→ “change owner”

### `chgrp`

→ “change group”

---

# Super Short Exam Answer

```text
chown is used to change file owner.

Example:
chown user file

chgrp is used to change file group.

Example:
chgrp group file
```

This is a very common Linux viva question.