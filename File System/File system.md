## Linux file system (simple explanation)

![[Pasted image 20260211145153.png]]

![[Pasted image 20260211145225.png]]



In **Linux**, everything is organized in **one single tree**, starting from the **root directory**:

```
/
```

There are **no drive letters** like `C:` or `D:`. All disks, USBs, and partitions are _mounted_ somewhere inside this tree.

---

### 🔹 Key directories you must know

|Directory|What it’s for|
|---|---|
|`/`|Root of the entire system|
|`/bin`|Essential user commands (`ls`, `cp`, `mv`)|
|`/sbin`|System/admin commands|
|`/etc`|Configuration files|
|`/home`|Users’ personal folders|
|`/root`|Home directory of the root (admin) user|
|`/var`|Variable data (logs, mail, cache)|
|`/usr`|User programs and libraries|
|`/lib`|Shared libraries needed to boot|
|`/tmp`|Temporary files|
|`/dev`|Device files (disks, USB, keyboard)|
|`/proc`|Virtual files showing system info|
|`/mnt`|Temporary mount point|
|`/media`|Mounted removable devices|

---

### 🔹 Example layout

```
/
├── bin
├── etc
├── home
│   ├── alice
│   └── bob
├── var
│   └── log
├── usr
└── tmp
```

---

### 🔹 Important concepts

**1. Everything is a file**

- Hardware (disks, USB, printer) → files in `/dev`
- System info → files in `/proc`

**2. Case-sensitive**

- `File.txt` ≠ `file.txt`

**3. Permissions**  
Each file has:

- **Owner**
- **Group**
- **Others**

With permissions:

- `r` (read)
- `w` (write)
- `x` (execute)

Example:

```
-rwxr-xr--
```

---

### 🔹 Mounting

Storage devices are attached to folders:

```
/dev/sdb1 → /media/usb
```

---

### 🔹 Common commands

```bash
ls        # list files
cd        # change directory
pwd       # show current path
cp        # copy
mv        # move/rename
rm        # delete
df -h     # disk usage
mount     # mount devices
```

---


shaodw and passwd inside etc

suid → super user id
set grp id → set group id

==**User** (owner), **Group**, and **Others**==.


[[permission granding]]

ctrl + alt + D → terminal

ctrl + alt + F1

