SSH (Secure Shell) is a network protocol used to securely access and manage another computer over a network.

It allows:

Remote login to another machine

Secure command execution

File transfers (using tools like SCP/SFTP)

Secure tunneling and port forwarding


Example:

ssh user@192.168.1.10

This command connects to the remote system at IP 192.168.1.10 using the username user.

In CTFs, SSH is used constantly for:

Accessing compromised machines

Logging into target lab environments

Pivoting between systems

Transferring exploit files and scripts

Maintaining stable shell access after gaining credentials


Since traffic is encrypted, SSH is much safer than older protocols like Telnet.