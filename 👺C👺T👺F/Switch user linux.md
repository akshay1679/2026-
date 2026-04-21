Here’s what each of these commands means in a Linux/Unix shell (Bash) and how they relate to switching users and checking privileges.


---

1. Switch User → su username

su username

What it does

su stands for substitute user or switch user.

It allows you to start a shell as another user account.

Example:

su john

This attempts to switch from your current user to the user john.


---

What happens after running it

The system asks for the target user’s password (not your password):

Password:

If correct, your shell changes to that user.

Example prompt:

alice@server:~$

after:

su john

becomes:

john@server:/home/john$


---

Common Variants


---

su - username

su - john

This is better than plain su.

It gives you:

full login shell

target user’s environment

target user’s PATH

target user’s home directory


This behaves like the user logged in normally.


---

su

su

Without specifying a username, it switches to:

root

(the superuser)

So:

su

means:

su root


---

Important Notes

Requires password

You usually need:

root password

or target user password


depending on system configuration.


---

Example

whoami

Output:

student

Now:

su root

then:

whoami

Output:

root


---

2. Check Sudo Privileges → sudo -l

sudo -l

What it does

This shows:

what commands you are allowed to run using sudo

without actually running them.

-l means:

list privileges


---

What is sudo?

sudo means:

SuperUser DO

It allows normal users to execute commands as:

root

another user


if permitted in the sudoers file

located at:

/etc/sudoers


---

Example

sudo -l

Possible output:

Matching Defaults entries for john on server:
    env_reset, mail_badpass

User john may run the following commands on server:
    (ALL : ALL) ALL


---

Meaning of This Output

(ALL : ALL) ALL

means:

User can run:

any command

as any user

as any group


This is basically:

full root access


---

Another Example

User john may run the following commands:
    (root) /usr/bin/systemctl

This means:

John can only run:

sudo systemctl

but not:

sudo rm -rf /


---

Very Useful for Privilege Escalation

Security professionals and penetration testers use:

sudo -l

to check:

Can this user become root?

Sometimes dangerous permissions exist like:

(root) NOPASSWD: /usr/bin/vim

This can lead to:

privilege escalation

to root.


---

NOPASSWD

Example:

(root) NOPASSWD: /usr/bin/python3

means:

You can run:

sudo python3

without entering a password.

Very powerful.


---

Quick Comparison

Command	Purpose

su username	Switch to another user
su - username	Full login shell as another user
su	Switch to root
sudo command	Run one command as root
sudo -l	List sudo permissions



---

Real-World Example

whoami
sudo -l
su root
id

This helps determine:

current user

sudo access

root access

user groups



---

Security Note

Never give unrestricted:

(ALL) ALL

unless absolutely necessary.

Least privilege is best practice.


---

Related Commands

Useful with this topic:

whoami
id
groups
sudo -i
sudo su
passwd
visudo


---

Summary

su username

→ switch shell to another user

sudo -l

→ list what commands you can run with elevated privileges

These are foundational Linux administration and cybersecurity commands.