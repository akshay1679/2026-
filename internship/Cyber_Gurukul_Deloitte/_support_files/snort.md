
open-source, rule-based Network Intrusion Detection and Prevention System

It is a ==Network Intrusion Detection and Prevention System== (NIDS/NIPS)

[[NIDS]]

[[NIPS]]

- **Rule-based system**
    - SNORT works using **rules (instructions)**
    - These rules define what “bad” or suspicious activity looks like

## Official Idea (Simplified)

- SNORT:
    - Uses **rules to identify malicious activity**
    - Checks **network packets (data traveling on network)**
    - If a packet matches a rule → **alert is generated**

[[Intrusion Detection System]] (IDS)

![[Drawing 2026-04-03 10.02.58.excalidraw]]

[[Intrusion Prevention System]] (IPS)

# ⚙️ Detection Techniques

### 1. Signature-Based

- ==Uses **predefined rules== (signatures)**
- Detects **known attacks**

👉 Limitation: <mark style="background: #ADCCFFA6;">Cannot detect new threats</mark>

---

### 🔹 2. Behaviour-Based

- Compares:
    - Normal behavior vs abnormal behavior
- <mark style="background: #ADCCFFA6;">Detects **unknown/new attacks**</mark>

---

### 🔹 3. Policy-Based

- <mark style="background: #ADCCFFA6;">Checks if activity violates **security rules/policies**</mark>

👉 Example: Blocking access to restricted websites


---

_Snort has three primary uses:
1. As a packet sniffer like tcpdump, as 
2. A packet logger, which is useful for network traffic debugging or 
3.  used as a full-blown network intrusion prevention system_

**Capabilities of Snort**:

- Live traffic analysis
- Attack and probe detection
- Packet logging
- Protocol analysis
- Real-time alerting
- Modules & plugins
- Pre-processors
- Cross-platform support! (Linux & Windows)

**Snort Modes**

- **Sniffer Mode**: Read and prompt IP packets in the console application.
- **Packet Logger Mode**: Log all IP packets (inbound and outbound) that visit the network.
- **NIDS (Network Intrusion Detection System)  and NIPS (Network Intrusion Prevention System) Modes**: Log/drop the packets deemed malicious according to the user-defined rules.

