## Linux User Switching and Privilege Checking

These commands are essential in Linux/Unix (especially Bash) for switching users and checking administrative privileges.

---

# 1. Switch User → `su username`

```bash
su username
```

## What it does

`su` stands for:

**substitute user**  
or  
**switch user**

It allows you to start a shell as another user account.

### Example

```bash
su john
```

This attempts to switch from your current user to the user `john`.

---

## What happens after running it

The system asks for the **target user’s password** (not your current password):

```bash
Password:
```

If the password is correct, your shell changes to that user.

### Example prompt

Before:

```bash
alice@server:~$
```

After:

```bash
su john
```

Becomes:

```bash
john@server:/home/john$
```

---

# Common Variants of `su`

---

## `su - username`

```bash
su - john
```

This is better than plain `su`.

It provides:

- Full login shell
    
- Target user’s environment
    
- Target user’s `PATH`
    
- Target user’s home directory
    

This behaves as if the user logged in normally.

---

## `su`

```bash
su
```

Without specifying a username, it switches to:

# `root`

(the superuser)

So:

```bash
su
```

means:

```bash
su root
```

---

# Important Notes

## Password Requirement

You usually need:

- the **root password**, or
    
- the **target user’s password**
    

depending on system configuration.

---

## Example

```bash
whoami
```

Output:

```bash
student
```

Now run:

```bash
su root
```

Then:

```bash
whoami
```

Output:

```bash
root
```

---

# 2. Check Sudo Privileges → `sudo -l`

```bash
sudo -l
```

---

## What it does

This shows:

**what commands you are allowed to run using `sudo`**

without actually running them.

`-l` means:

# list privileges

---

# What is `sudo`?

`sudo` stands for:

# SuperUser DO

It allows normal users to execute commands as:

- `root`
    
- another user
    

if permitted in the **sudoers file**

located at:

```bash
/etc/sudoers
```

---

# Example

```bash
sudo -l
```

Possible output:

```bash
Matching Defaults entries for john on server:
    env_reset, mail_badpass

User john may run the following commands on server:
    (ALL : ALL) ALL
```

---

# Meaning of This Output

## `(ALL : ALL) ALL`

This means:

The user can run:

- any command
    
- as any user
    
- as any group
    

This is basically:

# Full root access

---

# Another Example

```bash
User john may run the following commands:
    (root) /usr/bin/systemctl
```

This means:

John can only run:

```bash
sudo systemctl
```

but not:

```bash
sudo rm -rf /
```

---

# Very Useful for Privilege Escalation

Security professionals and penetration testers use:

```bash
sudo -l
```

to check:

## Can this user become root?

Sometimes dangerous permissions exist like:

```bash
(root) NOPASSWD: /usr/bin/vim
```

This can lead to:

# privilege escalation

to root.

---

# `NOPASSWD`

Example:

```bash
(root) NOPASSWD: /usr/bin/python3
```

This means:

You can run:

```bash
sudo python3
```

without entering a password.

Very powerful.

---

# Quick Comparison

|Command|Purpose|
|---|---|
|`su username`|Switch to another user|
|`su - username`|Full login shell as another user|
|`su`|Switch to root|
|`sudo command`|Run one command as root|
|`sudo -l`|List sudo permissions|

---

# Real-World Example

```bash
whoami
sudo -l
su root
id
```

This helps determine:

- current user
    
- sudo access
    
- root access
    
- user groups
    

---

# Security Note

Never give unrestricted:

```bash
(ALL) ALL
```

unless absolutely necessary.

## Least privilege is best practice.

---

# Related Commands

Useful commands related to this topic:

```bash
whoami
id
groups
sudo -i
sudo su
passwd
visudo
```

---

# Summary

## `su username`

→ Switch your shell to another user

## `sudo -l`

→ List what commands you can run with elevated privileges

These are foundational Linux administration and cybersecurity commands.