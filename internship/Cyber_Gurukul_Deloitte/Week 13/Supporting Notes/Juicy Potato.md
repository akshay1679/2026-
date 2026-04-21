**Juicy Potato** is a <mark style="background: #FFB8EBA6;">**privilege escalation exploit for Windows</mark> systems**. It’s used by attackers (and penetration testers) to **gain SYSTEM-level access** from a lower-privileged account

## ⚙️ How it works (simplified)

Juicy Potato abuses how Windows handles:

- 🧩 **COM/DCOM services**
- 🔑 **Token impersonation**

### Basic idea:

1. A Windows service running as **SYSTEM** is tricked
2. It authenticates to a malicious process
3. The attacker **captures and impersonates that SYSTEM token**
4. 💥 They now run commands as SYSTEM