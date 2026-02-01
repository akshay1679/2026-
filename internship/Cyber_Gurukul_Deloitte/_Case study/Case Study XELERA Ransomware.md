### 1️⃣ **Campaign Overview**

The **XELERA ransomware** campaign is a targeted malicious operation discovered in early 2025 that uses _<mark style="background: #ABF7F7A6;">social engineering</mark>_ to trick victims — particularly **<mark style="background: #ABF7F7A6;">job seekers in India</mark>** — <mark style="background: #ABF7F7A6;">into installing malware disguised as legitimate job notifications</mark>. It uses sophisticated delivery techniques and blends credential theft, remote control, disruptive payloads, and ransomware.

---

### 2️⃣ **Threat Actors & Targeting**

**Target Audience:**

- Individuals seeking employment in technical roles, specifically those responding to fake job messages purportedly from the **Food Corporation of India (FCI)**.
    
-<mark style="background: #ABF7F7A6;"> The campaign leverages the urgency and trust associated with job offers to bypass suspicion.</mark>
    

**Social Engineering Vector:**

- <mark style="background: #ABF7F7A6;">Spear-phishing emails</mark> containing a malicious Word document (titled **FCEI-job-notification.doc**) are sent to potential victims.
    
- The document <mark style="background: #ABF7F7A6;">contains</mark> realistic recruitment details (<mark style="background: #ABF7F7A6;">vacancies, eligibility, exam instructions</mark>) to look convincing.
    

---

### 3️⃣ **Infection Lifecycle**

#### 🔹 **Stage 1 — Delivery & Initial Execution**

1. **Malicious Document:**
    
    - The <mark style="background: #ABF7F7A6;">Word file contains a hidden OLE object that embeds a compressed executable named </mark>**jobnotification2025.exe**.
        
    - When opened, this executable runs on the victim’s machine.
        
2. **PyInstaller Payload:**
    
    - The executable is a **<mark style="background: #ABF7F7A6;">PyInstaller-packed Python program</mark>**.
        
    - <mark style="background: #ABF7F7A6;">It extracts and runs Python bytecode that orchestrates later behavior</mark>.
        

---

#### 🔹 **Stage 2 — Malware Core & Command-and-Control**

3. **Discord-Based C2:**
    
    - The <mark style="background: #ABF7F7A6;">malware uses a **Discord bot** as the command-and-control (C2) channel</mark> — <mark style="background: #ABF7F7A6;">hiding malicious traffic within seemingly normal Discord communications</mark>.
        
    -<mark style="background: #ABF7F7A6;"> This lets attackers issue remote commands and collect data without traditional C2 infrastructure</mark>.
        
4. **Capabilities of the Bot:**
    
    - Stealing browser credentials and local files
        
    - Locking or restarting the system
        
    - Capturing screenshots and webcam images
        
    - Spamming, graphical effects, disrupting user input
        
    - System info extraction
        
    - Many commands that go beyond typical ransomware behavior (e.g., <mark style="background: #ABF7F7A6;">controlling mouse/keyboard, BSOD triggers</mark>)
        

---

#### 🔹 **Stage 3 — Ransomware Activation**

5. **Execution of XELERA Ransomware:**
    
    - The final payload is the **XELERA ransomware module**, which shows a ransom note demanding payment in **<mark style="background: #ABF7F7A6;">Litecoin</mark>** to a specified wallet.
        
    - Although not always using strong cryptographic encryption, it disrupts systems by deleting files and dropping images and messages.
        
6. **Destructive Tactics:**
    
    - Terminates critical processes (like Windows Explorer) repeatedly
        
    - Alters desktop wallpaper
        
    - Uses or downloads an external MBR-corrupting tool (_e.g._, MEMZ.exe), which can make systems unbootable
        
    - Audio and visual disruptions to harass the victim further
        

---

### 4️⃣ **Technical Traits and Indicators**

**File Artifacts / Names:**

- **FCEI-job-notification.doc** – initial lure
    
- **jobnotification2025.exe** – PyInstaller executable
    
- **mainscript.pyc** – compiled Python logic
    

**Tech Stack:**

- Python scripts with libraries like **psutil**, **aiohttp**, **asyncio** for system interaction and network tasks
    
- Discord bot for C2 operations
    
- Litecoin wallet specified for ransom demands
    

**Attack Behavior:**

- Spear-phishing → document → embedded executable → Python payload → Discord C2 → ransomware & disruptive commands.
    

---

### 5️⃣ **Impact**

This campaign represents a blend of tactics that combine:

- **Credential theft**
    
- **Data exfiltration**
    
- **System disruption**
    
- **Potential data ransom/extortion**
    

Although primarily focused on individuals currently, the same techniques could scale to corporate networks if poorly protected.

---

### 6️⃣ **Lessons Learned**

#### 🛡 Prevention & Defense

**User Awareness:**

- Verify job offers through official channels — especially unsolicited ones with attachments.
    
- Be skeptical of documents that prompt you to run executables.
    

**Technical Defenses:**

- Keep **endpoint protection** up to date to catch suspicious PyInstaller binaries and OLE-based exploits.
    
- Deploy **email filtering** to block phishing attachments.
    
- Monitor outgoing connections for nonstandard C2 channels, such as Discord traffic from unknown processes.
    

**Incident Response:**

- Maintain backups and offline copies of critical data
    
- Prepare to isolate infected machines quickly to prevent lateral spread
    

---

### 7️⃣ **Strategic Insights**

XELERA demonstrates several evolving threat trends:

- **Social engineering weaponizes job search trust.**
    
- **Use of legitimate platforms (Discord) as C2 evasion.**
    
- **Multi-stage delivery combining malware types (stealer + ransomware).**
    

These trends make modern ransomware more than just file-encryption — it’s now an _end-to-end intrusion_ and _control_ threat that emphasizes psychological lure and technical stealth.

---

If you want a **visual diagram** of the infection chain or **IOC (Indicator of Compromise)** lists you can use for your security tools (hashes, domains), just let me know!