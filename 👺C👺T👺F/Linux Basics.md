
## 1. Linux Basics

Must know:

### Topics covered

- permissions
- users/groups
- SSH
- processes
- cron jobs
- SUID
- PATH hijacking
- environment variables
- file system navigation

---
# 1. Linux Basics for CTFs (Detailed)

These topics are extremely important because most CTF machines are Linux-based.

If you understand Linux well, privilege escalation becomes much easier.

---

# A. File System Navigation

Linux file system starts from:

```bash
/
```

This is called the **root directory**.

Everything exists inside it.

Important folders:

```bash
/home       -> user files
/root       -> root user's home
/etc        -> configuration files
/var        -> logs, databases
/tmp        -> temporary files
/usr        -> programs
/bin        -> essential commands
/sbin       -> system binaries
/dev        -> devices
/proc       -> process information
```

---

## Important Commands

### Show current directory

```bash
pwd
```

Example:

```bash
/home/akshay
```

---

### List files

```bash
ls
ls -la
```

```bash
-l  -> detailed list
-a  -> hidden files
```

Example:

```bash
ls -la
```

Shows:

- permissions
    
- owner
    
- group
    
- size
    
- hidden files
    

---

### Change directory

```bash
cd /etc
cd ..
cd ~
```

```bash
.. -> previous directory
~  -> home directory
```

---

### Create file

```bash
touch file.txt
```

---

### Create folder

```bash
mkdir test
```

---

### Copy files

```bash
cp file1 file2
```

---

### Move / Rename

```bash
mv old.txt new.txt
```

---

### Delete

```bash
rm file.txt
rm -r folder
```

---

## CTF Importance

You must know where to look:

- password files
    
- SSH keys
    
- cron jobs
    
- logs
    
- SUID binaries
    
- config files
    

This is critical.

---

# B. Permissions

Linux permissions decide:

> Who can read, write, or execute files

Example:

```bash
-rwxr-xr--
```

Breakdown:

```text
Owner | Group | Others
rwx   | r-x   | r--
```

Meaning:

```text
r = read
w = write
x = execute
```

---

## Permission Numbers

```text
r = 4
w = 2
x = 1
```

Examples:

```bash
777 -> rwxrwxrwx
755 -> rwxr-xr-x
644 -> rw-r--r--
600 -> rw-------
```

---

## Change Permissions

```bash
chmod 777 file
chmod +x script.sh
```

---

## Change Ownership

[[Change Ownership Lenux]]

```bash
chown user file
chgrp group file
```

---

## CTF Importance

<mark style="background: #FF5582A6;">Misconfigured permissions </mark>often lead to:

- writable sensitive files
    
- privilege escalation
    
- password theft
    

Very common.

---

# C. Users and Groups

Linux uses:

- users
    
- groups
    

to manage access.

Example:

```bash
whoami
id
```

Output:

```bash
uid=1000(user) gid=1000(user)
```

---

## Important Files

### User info

```bash
/etc/passwd
```

### Password hashes

```bash
/etc/shadow
```

(only root can read)

---

## Switch User

```bash
su username
sudo -l
sudo -ll  --> more detailed informations
```

[[Switch user linux ]]

![[Pasted image 20260421124044.png]]

This means:

- User `Akshay` can run **any command**
- As **any user**
- On this machine

![[Pasted image 20260421124326.png]]

---

## CTF Importance

Privilege escalation often means:

> becoming another user

or

> becoming root

Understanding users is mandatory.

---

# D. SSH (Secure Shell)

SSH allows remote login.

[[SSH  remote login]].

Example:

```bash
ssh user@192.168.1.10
```

Used constantly in CTFs.

---

## SSH Keys

[[SSH key id_rsa file]]

Stored in:

```bash
~/.ssh/
```

Important files:

```bash
id_rsa
authorized_keys
known_hosts
```

---

## CTF Importance

Sometimes you find:

```bash
id_rsa
```

This can give direct access.

Huge privilege escalation path.

---

# E. Processes

Everything running is a process.

Check:

```bash
ps aux
top
htop
```

Kill process:

```bash
kill PID
```

---

## Background Jobs

```bash
jobs
bg
fg
```

---

## CTF Importance

Processes may reveal:

- credentials
    
- scripts
    
- cron jobs
    
- hidden services
    

Very useful.

---

# F. Cron Jobs

Cron runs scheduled tasks automatically.

Example:

```bash
* * * * * /script.sh
```

Meaning:

> every minute run script.sh

Check:

```bash
crontab -l
cat /etc/crontab
ls /etc/cron.*
```

---

## CTF Importance

If root runs a writable script:

> you can inject commands

and become root.

Very famous privilege escalation.

---

# G. SUID (Super Important)

SUID means:

> run file as file owner

instead of current user.

If owned by root:

> program runs as root

Huge CTF topic.

---

## Find SUID Files

```bash
find / -perm -4000 2>/dev/null
```

Example:

```bash
/usr/bin/passwd
```

---

## Dangerous Example

If something like:

```bash
vim
bash
find
python
```

has SUID:

> easy root shell

Check GTFOBins for common abuses.

---

# H. PATH Hijacking

Linux searches commands using:

```bash
$PATH
```

Check:

```bash
echo $PATH
```

Example:

```bash
/usr/local/bin:/usr/bin:/bin
```

---

## Attack Idea

If root runs:

```bash
backup
```

instead of:

```bash
/usr/bin/backup
```

and writable PATH exists:

you place fake `backup`

→ root executes yours

→ root shell

Very common in CTFs.

---

# I. Environment Variables

Variables stored in shell.

Example:

```bash
echo $PATH
echo $HOME
echo $USER
env
```

Common variables:

```bash
PATH
HOME
USER
SHELL
PWD
```

---

## CTF Importance

Bad scripts trust environment variables.

This leads to:

- PATH hijacking
    
- command injection
    
- privilege escalation
    

---

# J. Why These Matter

Most Linux privilege escalation follows:

```text
Enumeration
→ Find weakness
→ Abuse permissions / SUID / cron / PATH
→ Become root
```

That is the real game.

---

# Beginner Commands You Must Practice Daily

```bash
pwd
ls -la
cd
find
grep
cat
chmod
chown
ps aux
sudo -l
id
whoami
env
crontab -l
ssh
```

Master these first.

---

Next after Linux Basics should be:

# 2. Networking Basics

because Linux + Networking together form the foundation of CTFs.