## Linux file system (simple explanation)

![Image](https://miro.medium.com/0%2AbFnHaO8eYpW3dSuz)

![Image](https://linuxhandbook.com/content/images/2020/06/linux-directory-structure.png)

![Image](https://www.linuxfoundation.org/hs-fs/hubfs/Imported_Blog_Media/standard-unix-filesystem-hierarchy-1.png?height=1001&name=standard-unix-filesystem-hierarchy-1.png&width=1817)

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

If you want:

- a **comparison with Windows file system**
- a **diagram-based explanation**
- or **interview-style notes**