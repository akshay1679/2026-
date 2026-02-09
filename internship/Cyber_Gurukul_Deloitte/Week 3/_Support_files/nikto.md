**Nikto** is a **<mark style="background: #ABF7F7A6;">web server vulnerability scanner</mark>** that comes **pre-installed in Kali Linux**. It’s mainly used in **penetration testing** and **security assessments** to quickly find common and known weaknesses in web servers.

![Image](https://www.ivoidwarranties.tech/img/nikto/nikto.png)

![Image](https://www.kali.org/tools/nikto/images/nikto-logo.svg)

![Image](https://upload.wikimedia.org/wikipedia/commons/c/c2/Nikto2.png)

### What Nikto does

Nikto scans a target web server and checks for:

- ❌ **Outdated server software**
    
- 🧱 **Misconfigurations** (like dangerous default files)
    
- 🔓 **Known vulnerabilities** (from its large database)
    
- 📁 **Sensitive files & directories** (e.g. `/admin`, `/backup`)
    
- ⚠️ **Insecure HTTP headers**
    
- 🧪 Test scripts and sample files left behind
    

### What Nikto is _good_ at

- Fast, **broad vulnerability checks**
    
- Identifying **low-hanging fruit**
    
- Recon during early phases of a pentest
    
- Learning how web security issues look in practice
    

### What Nikto is _not_ good at

- ❌ Stealth (it’s **very noisy** and easy to detect)
    
- ❌ Exploitation (it **finds** issues but doesn’t exploit them)
    
- ❌ Deep app logic bugs (like business-logic flaws)
    

### Basic usage

```bash
nikto -h http://example.com
```

Common options:

```bash
nikto -h example.com -p 80,443
nikto -h example.com -o report.html -Format html
```

### When to use Nikto

- Ethical hacking labs
    
- Authorized penetration tests
    
- Security audits of your **own** servers
    
- Learning web security concepts


