
```linux
apt-get update -y && apt-get upgrade -y --fix-missig
```

A **static patch** (also called a **traditional patch**) means:

> The system or application must be **stopped/restarted** for the patch to take effect.


### How it works

1. Download update
2. Replace old files/binaries
3. Restart service or reboot system
4. Patched code loads into memory