
## 🐄 Dirty COW (CVE-2016-5195) — Explained Simply

**Dirty COW** is a serious Linux kernel vulnerability discovered in 2016.  
Its official ID is **CVE-2016-5195**.

It allows a normal (low-privileged) user to gain **root privileges** (full system control).

---

## 🔎 What Does “Dirty COW” Mean?

- **COW = Copy-On-Write**
    
- "Dirty" refers to a race condition bug in the Linux memory system.
    

So **Dirty COW = a bug in how Linux handles Copy-On-Write memory operations.**

---

## 🧠 What is Copy-On-Write (COW)?

In Linux, when a process copies memory (like when using `fork()`), the kernel:

1. Doesn't immediately duplicate memory.
    
2. Instead, both processes share the same memory.
    
3. If one process tries to modify it, Linux creates a private copy.
    

This saves memory and improves performance.

---

## 💥 What Was the Problem?

Due to a **race condition** in the Linux kernel’s memory subsystem:

- A user could write to **read-only memory**
    
- Modify files they shouldn’t be able to change
    
- Escalate privileges to **root**
    

Even if the file was:

- Owned by root
    
- Marked read-only
    
- Protected by permissions
    

---

## ⚙️ How the Exploit Works (High-Level)

The attacker:

1. Uses a memory mapping (`mmap()`)
    
2. Triggers a race condition between:
    
    - `madvise()` (mark memory invalid)
        
    - Writing to `/proc/self/mem`
        
3. Overwrites protected files like `/etc/passwd`
    

After that, the attacker can:

- Change root password
    
- Create a root shell
    
- Fully control the system
    

---

## 📁 Example Target File

A common target was:

```
/etc/passwd
```

Attackers modified it to give themselves UID 0 (root).

---

## 🖥 Affected Systems

Dirty COW affected:

- Most Linux distributions
    
- Kernels from **2007 to 2016**
    
- Android devices using vulnerable kernels
    

Examples:

- Ubuntu
    
- Debian
    
- Red Hat
    
- CentOS
    
- Android
    

It existed silently for **9 years** before discovery.

---

## 🛡️ How to Protect Against Dirty COW

### 1️⃣ Update Your Kernel

Most systems patched it in late 2016.

Check your kernel version:

```bash
uname -r
```

If it’s modern (5.x or 6.x), you're safe.

---

### 2️⃣ Apply Security Updates

On Ubuntu/Debian:

```bash
sudo apt update
sudo apt upgrade
```

On CentOS/RHEL:

```bash
sudo yum update
```

---

## 🎯 Why Dirty COW Was So Serious

- Very easy to exploit
    
- No special permissions required
    
- Worked on default installs
    
- Allowed full root access
    
- Affected almost all Linux systems
    

It became one of the most famous Linux privilege escalation vulnerabilities.

---

## 🔐 Simple Summary

Dirty COW was a Linux kernel bug that allowed normal users to gain root access by exploiting a race condition in memory handling.

---

If you'd like, I can:

- Show you a **diagram explaining how the race condition works**
    
- Explain it in even simpler terms
    
- Or show how privilege escalation works in Linux generally


---

attacks where able to escalate the privileges of the user