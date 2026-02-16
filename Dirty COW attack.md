**Dirty COW** (short for *Dirty Copy-On-Write*) is a long-lived privilege-escalation vulnerability in the entity["software","Linux kernel","operating system component"], disclosed in **2016** as **entity["software","CVE-2016-5195","linux kernel vulnerability"]**.

### The idea in plain English
Linux uses a memory optimization called **copy-on-write (COW)**. If two processes share the same memory page and one tries to modify it, the kernel is supposed to make a private copy so the original stays unchanged.

Dirty COW is a race condition that lets an attacker **write to memory that should be read-only**. By winning the race, they can modify files or mappings they aren’t supposed to change.

### Why it’s serious
With that unintended write access, a normal user can often:
- overwrite parts of a root-owned executable,
- inject code,
- and end up with **root / administrator privileges**.

### How the race works (simplified)
Two actions happen at nearly the same time:
1. One thread tries to write to a read-only memory mapping.
2. Another invalidates or remaps the page.

Because of a flaw in how the kernel handled this situation, the write could hit the original page instead of a private copy.

### Who was affected
The bug existed for **many years** (since around 2007) and affected a huge number of Linux distributions until patches were released in 2016.

### How it was fixed
Kernel updates changed how the memory subsystem handles these write attempts, ensuring the copy happens reliably and the original read-only data can’t be altered.

---

If you want, I can also explain:

- how a typical exploit chain turns this into root access,  
- how to check whether a system is vulnerable, or  
- why race conditions like this are so hard to catch.

What would you like to dig into next?


---

attacks where able to escalate the privileges of the user