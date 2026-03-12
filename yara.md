
https://tryhackme.com/room/yara-aoc2025-q9w1e3y5u7

Here is a **very short, easy-to-study version** of the YARA lesson from TryHackMe. I made it **point-by-point so you can quickly remember it for labs or exams.**

---

# 1️⃣ What is YARA

- **YARA** is a tool used to **detect malware or suspicious files**.
    
- It works by **searching patterns (strings, bytes, regex)** inside files or memory.
    
- Think of it like a **malware fingerprint scanner**.
    

---

# 2️⃣ When YARA is Used

Defenders use YARA for:

- 🔹 **Threat hunting** – searching systems for malware traces
    
- 🔹 **Post-incident analysis** – checking if malware exists elsewhere
    
- 🔹 **Memory analysis** – detecting malicious code in RAM
    
- 🔹 **IOC scanning** – finding indicators of compromise
    

---

# 3️⃣ Advantages of YARA

- ⚡ **Fast scanning**
    
- 🧠 **Flexible pattern detection**
    
- 🎯 **Custom rules**
    
- 🤝 **Rules can be shared**
    
- 👁 **Helps connect attack clues**
    

---

# 4️⃣ Structure of a YARA Rule

Every rule has **3 main parts**:

### 1. Metadata

Information about the rule.

Example:

```
meta:
 author = "Akshay"
 description = "Detect malware"
 date = "2026-03-12"
```

---

### 2. Strings

Patterns YARA searches for.

Example:

```
strings:
 $s1 = "rundll32.exe"
 $s2 = "msvcrt.dll"
```

Types of strings:

#### Text Strings

```
$x = "Christmas"
```

Modifiers:

|Modifier|Meaning|
|---|---|
|nocase|ignore uppercase/lowercase|
|wide|Unicode string|
|ascii|ASCII string|
|xor|detect XOR encoded strings|
|base64|detect base64 encoded text|

Example:

```
$x = "Christmas" nocase wide ascii
```

---

#### Hex Strings

Used for **binary patterns**.

Example:

```
$mz = {4D 5A}
```

This detects **Windows executable header (MZ)**.

---

#### Regex Strings

Used for **pattern matching**.

Example:

```
$url = /http:\/\/.*malware.*/
```

---

# 5️⃣ Conditions

Defines **when the rule should trigger**.

### Single String

```
condition:
 $x
```

---

### Any String

```
condition:
 any of them
```

---

### All Strings

```
condition:
 all of them
```

---

### Logical Conditions

```
condition:
 ($s1 or $s2) and not $good
```

---

### File Property Checks

Example:

```
condition:
 any of them and filesize < 700KB
```

---

# 6️⃣ Example YARA Rule

```
rule TBFC_Simple_MZ_Detect
{
 meta:
  author = "SOC L2"
  description = "Detect malware"

 strings:
  $mz = {4D 5A}
  $s1 = "malhare" nocase

 condition:
  all of them and filesize < 10MB
}
```

Meaning:

- Find files that contain
    
    - **MZ header**
        
    - **malhare string**
        
    - **File size < 10MB**
        

---

# 7️⃣ Running YARA

Basic command:

```
yara rule.yar file
```

Scan folder recursively:

```
yara -r rule.yar folder
```

Show matched strings:

```
yara -r -s rule.yar folder
```

Example:

```
yara -r icedid_starter.yar C:\
```

---

# 8️⃣ Practical Task Logic (Important)

You must detect strings like:

```
TBFC:CODE
```

Example:

```
TBFC:HELLO
TBFC:WINTER
TBFC:123ABC
```

Regex pattern:

```
/TBFC:[A-Za-z0-9]+/
```

Meaning:

- `TBFC:` → fixed keyword
    
- `[A-Za-z0-9]` → letters or numbers
    
- `+` → one or more characters
    

---

# 9️⃣ Folder to Scan

TryHackMe machine location:

```
/home/ubuntu/Downloads/easter
```

Run:

```
yara -r rule.yar /home/ubuntu/Downloads/easter
```

---

✅ **Key Idea to Remember**

YARA =  
**Strings + Conditions → Detect malware**

---

https://regex101.com/

![[Pasted image 20260312052532.png]]

```
rule TBFC_Simple MZ Detect
{
	meta:
		author = "TBFC Blue Team_GingerHacker"
		description = "Extracts TBFC message fragments sent by McSkidy"
		date = "2025-12-13"

	strings:
		$tbfc_msg = /TBFC:[A-Za-z0-9]+/ ascii

	condition:
		$tbfc_msg

}
```


---
## yara -h

YARA 4.5.0, the pattern matching swiss army knife.
Usage: yara [OPTION]... [NAMESPACE:]RULES_FILE... FILE | DIR | PID

Mandatory arguments to long options are mandatory for short options too.

       --atom-quality-table=FILE           path to a file with the atom quality table
  -C,  --compiled-rules                    load compiled rules
  -c,  --count                             print only number of matches
  -E,  --strict-escape                     warn on unknown escape sequences
  -d,  --define=VAR=VALUE                  define external variable
  -q,  --disable-console-logs              disable printing console log messages
       --fail-on-warnings                  fail on warnings
  -f,  --fast-scan                         fast matching mode
  -h,  --help                              show this help and exit
  -i,  --identifier=IDENTIFIER             print only rules named IDENTIFIER
       --max-process-memory-chunk=NUMBER   set maximum chunk size while reading process memory (default=1073741824)
  -l,  --max-rules=NUMBER                  abort scanning after matching a NUMBER of rules
       --max-strings-per-rule=NUMBER       set maximum number of strings per rule (default=10000)
  -x,  --module-data=MODULE=FILE           pass FILE's content as extra data to MODULE
  -n,  --negate                            print only not satisfied rules (negate)
  -N,  --no-follow-symlinks                do not follow symlinks when scanning
  -w,  --no-warnings                       disable warnings
  -m,  --print-meta                        print metadata
  -D,  --print-module-data                 print module data
  -M,  --module-names                      show module names
  -e,  --print-namespace                   print rules' namespace
  -S,  --print-stats                       print rules' statistics
  -s,  --print-strings                     print matching strings
  -L,  --print-string-length               print length of matched strings
  -X,  --print-xor-key                     print xor key and plaintext of matched strings
  -g,  --print-tags                        print tags
  -r,  --recursive                         recursively search directories
       --scan-list                         scan files listed in FILE, one per line
  -z,  --skip-larger=NUMBER                skip files larger than the given size when scanning a directory
  -k,  --stack-size=SLOTS                  set maximum stack size (default=16384)
  -t,  --tag=TAG                           print only rules tagged as TAG
  -p,  --threads=NUMBER                    use the specified NUMBER of threads to scan a directory
  -a,  --timeout=SECONDS                   abort scanning after the given number of SECONDS
  -v,  --version                           show version information

Send bug reports and suggestions to: vmalvarez@virustotal.com.

---

## Yara scan perform

![[Pasted image 20260312053551.png]]

