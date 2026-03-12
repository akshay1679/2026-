
https://tryhackme.com/room/cyberthreatintel


Threat intelligence provides the context that helps an analyst decide which of those two hundred alerts represents genuine danger.

# Cyber Threat Intelligence (CTI) for SOC Analysts – Simple Notes

## 1. Why CTI is Important in a SOC

- SOC analysts receive **many alerts daily**.
- <mark style="background: #ABF7F7A6;">CTI</mark> helps analysts **<mark style="background: #ABF7F7A6;">identify which alerts are real threats</mark>**.
- It gives **context and background** about suspicious activity.
- Helps analysts **respond faster and more accurately**.


### CTI answers three key questions:

1. **Who or what generated the alert?**
2. **What behaviour has it shown before?**
3. **What should the organisation do now?**

---

# Data → Information → Intelligence

| Layer            | Meaning             | Example                   | L1 Analyst Action    |
| ---------------- | ------------------- | ------------------------- | -------------------- |
| **Data**         | Raw observable      | IP: 45.155.205.3          | Capture the artifact |
| **Information**  | Data + details      | IP belongs to Hetzner     | Add attributes       |
| **Intelligence** | Meaningful analysis | Known BumbleBee C2 server | Escalate / block     |

<mark style="background: #ADCCFFA6;">Goal of L1 analysts: **Enrich data until it becomes intelligence**.</mark>



---

# Key Security Terms

### 1. Indicator of Compromise (IOC)

Evidence that a system **has been breached**.

Examples:

- Malicious IP
- Malware file hash
- Suspicious domain
    

---

### 2. Indicator of Attack (IOA)

Shows that a **malicious action is happening now**.

Examples:

- PowerShell launching suspicious process
- Multiple failed login attempts
    

---

### 3. Tactics, Techniques, and Procedures (TTP)

Methods used by attackers, mapped to **MITRE ATT&CK**.

Example:

- **T1110.003 – Password Guessing**
    

---

# Common Indicator Types

When a security alert appears in the SOC, it usually contains an **indicator** (something suspicious).  
Your job as an L1 analyst is to **investigate that indicator using threat-intelligence tools**.

### IP Address

Alert says:

`Employee PC connected to 45.155.205.3:443`

You check:

- VirusTotal → flagged by 20 vendors
- Shodan → shows SSH server
- WHOIS → hosting provider known for abuse

Possible attack:

- SSH brute force
    

---

### Domain

### Example

`malicious-updates.net`

Check:

Tools:

- **WHOIS lookup** → domain age
- **SecurityTrails / Passive DNS** → IP history
- **urlscan.io** → website behaviour

Possible attack:

- Newly registered phishing domain


---

### URL Indicator

### Example

`http://malicious-updates.net/login`

A **specific page** on a website.
A URL is **more detailed than a domain**.

Example:

- Domain → google.com
- URL → google.com/login


### What an Analyst Checks

Tools:

- **URLhaus**
- **urlscan.io**
- **Any.Run sandbox**

### Example Investigation

Alert shows browser activity:

```
POST request to /gateway.php
```

Sandbox shows:

- Fake login page
- Sends credentials to attacker server


### Possible Attack

- **Credential phishing**
- **Malware download**

---

### File Hash Indicator 

### Example

``e99a18c428cb38d5f260853678922e03``

A **file hash** is a unique fingerprint of a file.
Even if the file name changes, **the hash stays the same**.

### What an Analyst Checks

Tools:

- **VirusTotal**
- **Hybrid Analysis**
- **MalShare**
    

### Example Investigation

Alert shows:

File executed: invoice.exe  
``Hash: e99a18c428cb38d5``

VirusTotal results:

- 45 engines detect malware
- Malware family: **BumbleBee**

### Possible Attack

- **Malware execution**
- **Process injection**
    

Example MITRE technique:

- **T1055 – Process Injection**

---

### Email Address

### Example

```
billing@evil-corp.com
```

A suspicious email sender.

### What an Analyst Checks

Tools:

- **MXToolbox** → email header analysis
- **HaveIBeenPwned** → data breach info
    

### Example Investigation

Phishing email received:

```
From: billing@evil-corp.com  
Subject: Invoice attached
```

Checks show:

- Domain registered yesterday
- SPF failure
- Known phishing campaign
    

### Possible Attack

- **Business Email Compromise**
- **Invoice phishing**
    

---

### Local Artifact

Example:

```
HKCU\Software\Run\updater.exe
```

Check:

- Sigma rules
    
- EDR query
    

Possible attack:

- Persistence via registry
    

---

# Threat Intelligence Feeds vs Platforms

### Feeds

- Continuous stream of threat indicators.
- Formats: **CSV, JSON, STIX, TAXII**
- Example: Malware IP feed.
    

⚠ Too many feeds can cause **false positives**.

---

### Platforms

Systems that **store and manage threat intelligence**.

Examples:

- **MISP**
- **OpenCTI**
    

Purpose:

- Store indicators
- Enrich data
- Track relationships
    

---

# Sources of Threat Intelligence

### 1. Internal Sources

Most relevant to the organisation.

Examples:

- [[SIEM logs]]
- [[EDR alerts]]
- Phishing mailbox
    

---

### 2. Commercial Sources

Paid threat intelligence services.

Examples:

- Vendor feeds
- Paid sandboxes
    

Advantages:

- High accuracy
- Detailed analysis
    

---

### 3. Open-Source Intelligence (OSINT)

Examples:

- AbuseIPDB
    
- URLhaus
    
- Security blogs
    

⚠ Must **verify before using**.

---

### 4. Communities & ISACs

Industry intelligence sharing groups.

Example:

- **FS-ISAC** (Financial sector)

Benefits:

- Shared threat insights
    
- Industry-specific intelligence
    

---

# Types of Threat Intelligence

### 1. Strategic Intelligence

High-level insights for **business decisions**.

Example:

- Annual ransomware trends report.
    

---

### 2. Tactical Intelligence

Focuses on **attacker techniques (TTPs)**.

Example:

- New PowerShell abuse method.
    

---

### 3. Operational Intelligence

Information about **specific attack campaigns**.

Example:

- APT targeting healthcare sector.
    

---

### 4. Technical Intelligence

Atomic indicators used in detection.

Examples:

- IP addresses
    
- Domains
    
- File hashes
    

---

# Role of an L1 SOC Analyst

- Investigate **technical indicators (IOCs)**.
    
- Identify **suspicious behaviours (IOAs)**.
    
- Enrich alerts with CTI tools.
    
- Escalate real threats to **incident response teams**.
    

---

If you want, I can also make a **super-short SOC analyst revision sheet (1-page cheat sheet)** that most **SOC interview questions come from.**


---
# Cyber Threat Intelligence (CTI) Lifecycle – Simple Notes

CTI follows a **6-phase lifecycle** that converts **raw security data into useful intelligence** to help SOC analysts detect and respond to threats.

Example scenario:  
SOC analyst **Alex** is protecting **TryHatMe company's PostgreSQL database**.



```
Traffic Light Protocol (TLP)
⬇️
```

---


# Important Concepts Before CTI Lifecycle

## 1. Traffic Light Protocol (TLP)

TLP controls **how threat intelligence can be shared**.

ie use to control **who can share threat information and with whom**.

|TLP|Meaning|SOC Analyst Action|
|---|---|---|
|**TLP:CLEAR**|Public information|Share anywhere|
|**TLP:GREEN**|Share within trusted community|Share with partner SOCs|
|**TLP:AMBER**|Internal organisation use|Keep inside company|
|**TLP:RED**|Very sensitive|Only specific people|

⚠ Analysts must **respect TLP labels** when sharing indicators.

---

## 2. STIX (Threat Intel Format)

**STIX – Structured Threat Information Expression**

- Standard format for sharing threat intelligence
- Machine-readable **JSON format**
- Describes indicators, attacks, and relationships

---

# 6 Phases of the CTI Lifecycle

---

# 1. Direction (Planning)

Define **what intelligence is needed**.

Alex identifies:

- **Asset to protect:** PostgreSQL database
    
- **Risk:** Data breach & GDPR fines
    
- **Security controls:**
    
    - Firewall (block IP/domain)
        
    - EDR (block malicious file hashes)
        

Key questions:

1️⃣ Which **IPs/domains attack PostgreSQL servers?**  
2️⃣ Which **malware targets PostgreSQL credentials?**

---

# 2. Collection (Gathering Data)

Collect threat data from different sources.

Sources Alex uses:

|Source|Example Data|
|---|---|
|Commercial threat feed|37 malicious IP addresses|
|AbuseIPDB (OSINT)|15 IPs and 4 domains|
|Internal MISP platform|2 malware hashes|
|Vendor threat report|1 malware hash and 3 domains|

Data is saved in **STIX or CSV format**.

---

# 3. Processing (Cleaning Data)

Prepare the data for analysis.

Tasks include:

- Normalize data format
    
- Remove duplicates
    
- Tag indicators with:
    
    - Source
        
    - Date
        
    - TLP label
        

Outputs created:

- **Firewall blocklist**
    
- **EDR malware hash rules**
    

Example:

```
firewall_blocklist.csv
edr_hash_rules.yar
```

---

# 4. Analysis (Understanding Threats)

Determine **which indicators are relevant**.

Alex checks:

- **Splunk logs** for past activity
    
- **OpenCTI** for threat context
    
- **Sandbox analysis** for malware behaviour
    

Indicators are graded:

|Level|Criteria|Action|
|---|---|---|
|High|Multiple sources + local activity|Block immediately|
|Medium|Trusted source only|Alert|
|Low|Only OSINT|Monitor|

Result:

- **7 IPs blocked**
    
- **1 malware hash blocked**
    

---

# 5. Dissemination (Sharing Intelligence)

Share results with the correct teams.

|Team|Information Shared|
|---|---|
|Firewall team|Blocklist CSV|
|Endpoint team|YARA rules|
|CTI platform|Indicator records|
|Management|Short risk report|

Goal: **Ensure each team receives actionable intelligence**.

---

# 6. Feedback (Improvement)

Evaluate results and improve the process.

After 2 weeks:

|Metric|Before|After|
|---|---|---|
|Attack dwell time|48 hours|0 hours|
|False positives|Unknown|0%|

Result:

- System blocks threats **before they reach the database**.
    

Next step:

- Add **DNS tunneling detection**.
    

---

# Simple Way to Remember the CTI Lifecycle

1️⃣ **Direction** – Define intelligence goals  
2️⃣ **Collection** – Gather threat data  
3️⃣ **Processing** – Clean and organise data  
4️⃣ **Analysis** – Understand threats  
5️⃣ **Dissemination** – Share intelligence  
6️⃣ **Feedback** – Improve the process

---

✅ **One-line summary**

CTI lifecycle helps SOC teams **collect, analyse, and use threat intelligence to detect and stop cyber attacks faster**.

---

If you want, I can also show you a **very easy real-world SOC example of the CTI lifecycle (like an actual malware attack investigation)** that makes this topic **much easier to remember for exams or interviews.**