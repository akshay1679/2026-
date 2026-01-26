## Polymorphic Ransomware — explained simply

**Polymorphic ransomware** is a type of ransomware that **<mark style="background: #ABF7F7A6;">keeps changing its code every time it spreads</mark>**,  **<mark style="background: #ABF7F7A6;">but does the same malicious job</mark>** (encrypting files and demanding ransom).

### Key idea (one-liner 🔑)

👉 _Same attack, different appearance each time._

### How it works (step by step)

1. The ransomware infects a system
2. <mark style="background: #ABF7F7A6;">Before spreading or executing again, it **modifies its own code**</mark>
    - <mark style="background: #FFB8EBA6;">Changes variable names</mark>
    - <mark style="background: #FFB8EBA6;">Reorders instructions</mark>
    - <mark style="background: #FFB8EBA6;">Uses encryption/obfuscation</mark>
3. <mark style="background: #ABF7F7A6;">Antivirus signatures fail because the **code hash looks new**</mark>
4. Files get encrypted → ransom demand appears

### How to defend against it

(Not signatures ❌)

✔ Behavioral analysis  
✔ Heuristic detection  
✔ Least privilege  
✔ Regular backups  
✔ Application whitelisting


