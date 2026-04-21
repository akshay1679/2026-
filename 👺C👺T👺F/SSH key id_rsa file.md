In CTFs, SSH files under ~/.ssh/ are common targets because they can reveal access to other machines or help with privilege escalation.

~/.ssh/

This is the hidden SSH configuration directory inside a user’s home folder.


---

Important SSH Files

1. id_rsa

This is the private SSH key.

~/.ssh/id_rsa

Purpose

Used to authenticate from this machine to another machine without typing a password.

Example

If user alice has:

~/.ssh/id_rsa

she can do:

ssh bob@target-machine

and SSH uses that private key automatically.

Why important in CTF

If you find someone’s id_rsa, you may be able to:

log in as that user on another machine

pivot to another box

escalate privileges


Permissions

Usually:

chmod 600 id_rsa

because private keys must stay secret.

Related file

Usually paired with:

id_rsa.pub

which is the public key.


---

2. authorized_keys

~/.ssh/authorized_keys

Purpose

This file tells SSH:

> “These public keys are allowed to log into this account.”



Example

If your public key is inside:

/home/user/.ssh/authorized_keys

you can SSH into that account using your matching private key.

Why important in CTF

If you can write to this file, you can often get instant shell access.

Example attack:

echo "YOUR_PUBLIC_KEY" >> ~/.ssh/authorized_keys

Now you can SSH in using your private key.

This is a classic persistence technique.


---

3. known_hosts

~/.ssh/known_hosts

Purpose

Stores fingerprints of remote servers previously connected to.

Example

When you first SSH to a host:

ssh user@server

you see:

Are you sure you want to continue connecting?

After accepting, its fingerprint is saved here.

Why useful in CTF

Can reveal:

internal hostnames

pivot targets

infrastructure layout

previously accessed machines


Sometimes it leaks hidden machines.


---

Quick CTF Checklist

When you get shell access, check:

ls -la ~/.ssh/
cat ~/.ssh/id_rsa
cat ~/.ssh/authorized_keys
cat ~/.ssh/known_hosts

Also check other users:

/home/*/.ssh/

especially:

/root/.ssh/

(if readable)


---

Common PrivEsc Trick

Writable:

/root/.ssh/authorized_keys

= basically root access.

Add your key → SSH as root.

Very common in misconfigured boxes.


---

Summary Table

File	Meaning	CTF Value

id_rsa	private key	login to other systems
id_rsa.pub	public key	usually less useful
authorized_keys	allowed login keys	persistence / shell access
known_hosts	trusted remote servers	recon / pivoting



---

CTF Mindset

Always think:

> “Can this SSH file help me become another user?”



That’s usually the winning path.


