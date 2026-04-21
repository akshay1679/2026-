
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