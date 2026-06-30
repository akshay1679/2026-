[[Linux Basics]]
[[Networking Basics]]

```
root:x:0:0:root:/root:/bin/bash
```

This is one entry from the `/etc/passwd` file.  
Each line represents **one user account** on the Linux system.

| Field    | Value     | Meaning                               |
| -------- | --------- | ------------------------------------- |
| Username | root      | superuser account                     |
| Password | x         | real password stored in `/etc/shadow` |
| UID      | 0         | root privileges                       |
| GID      | 0         | belongs to root group                 |
| Comment  | root      | account description                   |
| Home     | /root     | root’s home directory                 |
| Shell    | /bin/bash | Bash terminal access                  |
