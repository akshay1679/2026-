- **IDS = ==Passive monitoring system**==
    - It only **observes network activity**, does not stop attacks
- **Detects:**
    - Malicious activities
    - Unusual behavior
    - Policy violations
- **What it does:**
    - ==Generates **alerts**== when something suspicious is found

---

### 🔸 Types of IDS

#### 1. Network IDS (NIDS)

- Monitors **entire network traffic (subnet)**
- Looks at data from multiple devices
- Sends alert if suspicious pattern found

👉 Example: Monitoring all computers in an office network

---

#### 2. Host-based IDS (HIDS)

- Monitors **single device (host)**
- Focuses on activity inside one system

👉 Example: Monitoring only your laptop

---

# 🛡️ Intrusion Prevention System (IPS)

## 🔹 What is IPS?

- **IPS = Active protection system**
- It not only detects but also **stops attacks immediately**
- **What it does:**
    - Detects threats
    - **Blocks / terminates** malicious activity

---

## 🔸 Types of IPS

### 1. Network IPS (NIPS)

- Protects the **whole network**
- Stops malicious traffic across subnet

---

### 2. Behaviour-based IPS (NBA)

- Learns **normal network behavior (training phase)**
- Detects **abnormal activity**

👉 Important:

- Needs training (“baselining”)
- Can detect **new/unknown attacks**
- Risk: Wrong training → false alerts

---

### 3. Wireless IPS (WIPS)

- Protects **wireless networks (Wi-Fi)**
- Stops attacks coming from wireless sources

---

### 4. Host-based IPS (HIPS)

- Protects **single device**
- Similar to HIDS but:
    - HIDS → alerts
    - HIPS → **blocks attacks**

---

# ⚙️ Detection Techniques

## 🔹 1. Signature-Based

- Uses **predefined rules (signatures)**
- Detects **known attacks**

👉 Limitation: Cannot detect new threats

---

## 🔹 2. Behaviour-Based

- Compares:
    - Normal behavior vs abnormal behavior
- Detects **unknown/new attacks**

---

## 🔹 3. Policy-Based

- Checks if activity violates **security rules/policies**

👉 Example: Blocking access to restricted websites

---

# 🔁 IDS vs IPS (Simple Difference)

- **IDS**
    - Detects threats
    - Sends alerts
    - Needs human action
- **IPS**
    - Detects + **blocks threats automatically**

👉 Easy memory trick:

- IDS = **Alarm 🔔**
- IPS = **Security guard 🚫**

---

# 🐷 SNORT – Extra Points

## 🔹 What SNORT can do

- Analyze **live network traffic**
- Detect attacks and probes
- Log packets (store data)
- Analyze protocols
- Give **real-time alerts**
- Works on Linux & Windows

---

## 🔹 SNORT Modes

### 1. Sniffer Mode

- Reads packets and shows them on screen

---

### 2. Packet Logger Mode

- Saves network traffic into logs

---

### 3. NIDS/NIPS Mode

- Uses rules to:
    - Detect threats
    - Log or **drop malicious packets**

---

# ✅ Super Simple Summary

- **IDS → Detects & alerts**
- **IPS → Detects & blocks**
- **SNORT → Tool that can do both**
- Uses **rules + traffic analysis**
- Can monitor:
    - Whole network (NIDS/NIPS)
    - Single device (HIDS/HIPS)

---

If you want next level help, I can:

- Turn this into **short revision notes (1-page)**
- Create **MCQs for exam practice**
- Or give **real-world examples for each concept**