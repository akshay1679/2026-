
## What is EDR?

**EDR** stands for **Endpoint Detection and Response**
It is security software installed **directly on computers and servers** to monitor their behavior.

Endpoints include:

- Laptops
- Workstations
- Servers
    

Example tools:

- CrowdStrike Falcon
- Microsoft Defender for Endpoint
- SentinelOne
    

---

## What EDR Monitors

EDR tracks activities like:

- Process execution
- File creation
- Registry changes
- Network connections
- PowerShell commands
    

This helps detect **malware behavior**.

---

## Example EDR Alert

Alert:

Suspicious PowerShell execution detected  
Process: powershell.exe  
Command: DownloadString  
Parent process: winword.exe

This is suspicious because:

- Word should not normally launch PowerShell
    
- Could indicate **macro malware**
    

---

## Process Tree Example

EDR shows attack chain like this:

winword.exe  
   ↓  
powershell.exe  
   ↓  
malware.exe  
   ↓  
connects to malicious IP

This helps analysts **see how the attack happened**.

---

# Difference Between SIEM and EDR

|Feature|SIEM|EDR|
|---|---|---|
|Focus|Entire network|Individual devices|
|Data Source|Logs from many systems|Endpoint activity|
|Purpose|Detect patterns across network|Detect malware behavior|
|Example|Login failures|Suspicious PowerShell|