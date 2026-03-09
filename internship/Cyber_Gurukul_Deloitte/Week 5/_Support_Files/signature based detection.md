	gck file signature 
https://www.garykessler.net/library/file_sigs_GCK_latest.html

**Signature-based detection** is a method used in cybersecurity and digital forensics to identify known threats by comparing data against a database of _predefined patterns_ (called **signatures**). If something in the system — like a file, network packet, or program behavior — matches one of these signatures, the system flags it as suspicious or malicious.

## 🔍 What Signature-Based Detection Means

### ✅ In Malware & Intrusion Detection

- Security tools (like antivirus or IDS/IPS) maintain a _library of signatures_ representing known malware samples or attack behaviors.
    
- Each signature is a unique pattern — usually a sequence of bytes, code characteristics, or behavior traits — derived from previously analyzed malicious software.
    
- When the tool scans a file or monitors activity, it compares what it sees with these signatures.
    
    - **Match → threat detected**
        
    - **No match → considered safe (for now)**
        

**Example:**  
An antivirus sees a file with a specific byte pattern it knows belongs to a virus. Because it matches a stored signature, it quarantines the file.


snort → tool used for intrusion detection

https://www.youtube.com/watch?v=iBsGSsbDMyw

how IDS detects an intrusion ?
