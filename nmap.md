```
nmap 192.168.140.133 -p- -sV -sC -oX metasploitable
```

| Option               | Meaning                                                               |
| -------------------- | --------------------------------------------------------------------- |
| `192.168.140.133`    | Target IP address                                                     |
| `-p-`                | Scan **all 65,535 TCP ports**                                         |
| `-sV`                | Detect service versions running on open ports                         |
| `-sC`                | Run default NSE (Nmap Scripting Engine) scripts                       |
| `-oX metasploitable` | Output results in **XML format** to a file named `metasploitable.xml` |

---

```
nmap 192.168.140.133 -p 21 -sV --script ftp* -oX metaFTP
```

### 🔎 What It Does

- **`192.168.140.133`** → Target IP address (likely a local machine).
    
- **`-p 21`** → Scan only **port 21** (default FTP port).
    
- **`-sV`** → Perform **service/version detection** to identify the FTP server software and version.
    
- **`--script ftp*`** → Run all **Nmap NSE scripts starting with "ftp"**.  
    These typically include:
    
    - `ftp-anon`
    - `ftp-bounce`
    - `ftp-syst`
    - `ftp-vsftpd-backdoor`
    - `ftp-proftpd-backdoor`
    - etc.
    
- **`-oX metaFTP`** → Save the output in **XML format** to a file named `metaFTP.xml`.
    

---

### 📌 Important Note

Running `ftp*` scripts may:

- Attempt **anonymous login**
- Check for **known FTP backdoors**
- Probe for **misconfigurations*

⚠️ Make sure you have **explicit authorization** to scan that host. Unauthorized scanning can be illegal.

---

### 📂 Where to Find the Output

After completion, you will have:

```
metaFTP.xml
```

You can:

- Open it in a browser
- Convert it to HTML using:

```bash
xsltproc /usr/share/nmap/nmap.xsl metaFTP.xml -o metaFTP.html
```

---

