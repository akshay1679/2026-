
# <mark style="background: #FFB8EBA6;">Fix 1</mark>

![[Pasted image 20260323131950.png]]
	
	edit --> virtual network editor
	change settings 
	restore the settings
	press ok

---

# 🧠 Root Cause (in your case)

👉 Your VM network interface `ens33` was **DOWN**

That caused:

- ❌ No IP address
    
- ❌ No default gateway
    
- ❌ No internet
    
- ❌ Error: `Network is unreachable`
    

---

# 🔍 How to Identify This Issue (fast method)

Whenever internet doesn’t work in Linux VM, follow this exact order:

---

## ✅ STEP 1 — Check interface status

```bash
ip a
```

### What to look for:

- ❌ BAD:
    

```bash
ens33: state DOWN
```

- ✅ GOOD:
    

```bash
ens33: state UP
```

👉 If **DOWN → this is your problem**

---

## ✅ STEP 2 — Check IP address

Still in `ip a`, look for:

- ❌ BAD: no `inet`
    
- ✅ GOOD:
    

```bash
inet 192.168.x.x
```

👉 No IP = DHCP failed or interface down

---

## ✅ STEP 3 — Check routing (gateway)

```bash
ip route
```

- ❌ BAD: empty output (like yours)
    
- ✅ GOOD:
    

```bash
default via 192.168.x.x
```

👉 No default route = “Network is unreachable”

---

## ✅ STEP 4 — Test connectivity

```bash
ping 8.8.8.8
```

- If fails → network issue
    
- If works → DNS issue
    

---

# 🛠️ How to Fix (Step-by-Step)

## 🔧 Fix 1 — Bring interface UP

```bash
sudo ip link set ens33 up
```

---

## 🔧 Fix 2 — Get IP from DHCP

```bash
sudo dhclient ens33
```

---

## 🔧 Fix 3 — Verify

```bash
ip a
ip route
ping 8.8.8.8
```

---

# 🔁 Permanent Fix (VERY IMPORTANT)

If this happens after reboot → Netplan is misconfigured.

## Edit config:

```bash
sudo nano /etc/netplan/*.yaml
```

### Correct config:

```yaml
network:
  version: 2
  ethernets:
    ens33:
      dhcp4: true
```

Apply:

```bash
sudo netplan apply
```

---

# 🚨 How to Quickly Diagnose ANY Linux Network Issue

Use this mental checklist:

### 1️⃣ Interface UP?

```bash
ip a
```

### 2️⃣ Got IP?

```bash
ip a
```

### 3️⃣ Gateway exists?

```bash
ip route
```

### 4️⃣ Can reach internet?

```bash
ping 8.8.8.8
```

### 5️⃣ DNS working?

```bash
ping google.com
```

---

# ⚡ Common Scenarios

|Problem|Symptom|Fix|
|---|---|---|
|Interface DOWN|`state DOWN`|`ip link set up`|
|No IP|no `inet`|`dhclient`|
|No route|`ip route` empty|DHCP / add route|
|DNS issue|ping IP works, domain fails|fix `/etc/resolv.conf`|
|VMware issue|no adapter detected|check VM settings|

---

# 🧠 Pro Tip (what you learned)

Your error:

```bash
Network is unreachable
```

👉 ALWAYS means:

> “System has no route to send packets”

Not DNS, not firewall — **routing or interface problem**

---

# 🚀 If you want next level

I can give you:

- 🔥 A **1-minute debugging flowchart**
    
- 🔥 Or simulate **real-world network failures** for practice
    

Just tell me 👍