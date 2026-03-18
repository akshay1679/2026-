
Below is a **clean documentation-style guide** of the whole troubleshooting process you performed to make **VirusTotal enrichment appear in MISP 2.4**.  
I organized it as a **step-by-step decision tree (IF / ELSE)** so someone else can follow it easily.

---

# MISP VirusTotal Enrichment Troubleshooting Guide (Step-by-Step)

## Goal

Enable **VirusTotal enrichment module** in MISP and configure the **API key**.

---

# 1️⃣ Verify misp-modules Service

VirusTotal enrichment requires **misp-modules**.

### Check if misp-modules is running

```bash
misp-modules
```

Expected output:

```
misp-modules server started on localhost:6666
```

---

### Decision

**IF misp-modules starts successfully**

➡ Go to **Step 2**

**ELSE**

Install misp-modules.

---

# 2️⃣ Install misp-modules (If Missing)

Install dependencies

```bash
sudo apt update
sudo apt install python3-pip python3-dev python3-venv libpq5 libjpeg-dev -y
```

Install misp-modules

```bash
sudo pip3 install misp-modules
```

Start the service

```bash
misp-modules
```

---

### Decision

**IF server starts**

```
misp-modules server started on localhost:6666
```

➡ Go to **Step 3**

**ELSE**

Check installation path:

```bash
which misp-modules
```

Fix python installation if needed.

---

# 3️⃣ Verify Modules Are Available

Check module list:

```bash
curl http://127.0.0.1:6666/modules | grep virus
```

Expected output example:

```
virustotal
virustotal_public
virustotal_private
virustotal_upload
```

---

### Decision

**IF VirusTotal modules appear**

➡ Go to **Step 4**

**ELSE**

Update misp-modules:

```bash
pip3 install --upgrade misp-modules
```

Restart service.

---

# 4️⃣ Configure Enrichment in MISP GUI

Go to:

```
MISP → Administration → Server Settings → Plugin
```

Locate **Enrichment section**.

---

### Set these parameters

Enable enrichment services

```
Plugin.Enrichment_services_enable = true
```

Set service URL

```
Plugin.Enrichment_services_url = http://127.0.0.1
```

Set service port

```
Plugin.Enrichment_services_port = 6666
```

Save settings.

---

### Decision

**IF enrichment services disabled**

VirusTotal modules **will NOT appear**.

Enable them and refresh page.

---

# 5️⃣ Verify Connection

Go to:

```
MISP → Administration → Server Settings → Diagnostics
```

Check:

```
MISP modules connection
```

Expected result:

```
OK
```

---

### Decision

**IF status = OK**

➡ Go to **Step 6**

**ELSE**

Check service

```bash
curl http://127.0.0.1:6666/modules
```

Restart modules.

---

# 6️⃣ Configure VirusTotal API Key

Go to:

```
MISP → Administration → Server Settings → Plugin
```

Find:

```
Plugin.Enrichment_virustotal_apikey
```

Add your API key:

```
YOUR_VIRUSTOTAL_API_KEY
```

Save.

---

# 7️⃣ Test VirusTotal Enrichment

Open an event.

Select an attribute such as:

```
IP
Domain
Hash
URL
```

Click:

```
Actions → Enrich
```

You should see modules like:

- VirusTotal lookup
    
- VirusTotal upload
    
- URLScan
    
- CVE lookup
    

---

# 8️⃣ Run misp-modules as Background Service (Recommended)

Running manually stops when terminal closes.

Create a service.

---

## Create systemd service

```bash
sudo nano /etc/systemd/system/misp-modules.service
```

Add:

```
[Unit]
Description=MISP Modules Service
After=network.target

[Service]
Type=simple
User=www-data
ExecStart=/usr/local/bin/misp-modules
Restart=always

[Install]
WantedBy=multi-user.target
```

---

Reload systemd

```bash
sudo systemctl daemon-reload
```

Enable service

```bash
sudo systemctl enable misp-modules
```

Start service

```bash
sudo systemctl start misp-modules
```

Check status

```bash
sudo systemctl status misp-modules
```

Expected:

```
Active: active (running)
```

---

# 9️⃣ Final Verification

Test modules:

```bash
curl http://127.0.0.1:6666/modules
```

Test enrichment in GUI.

---

# Complete Troubleshooting Decision Tree

```
START
 │
 │
 ├─ Is misp-modules installed?
 │      │
 │      ├─ NO → Install misp-modules
 │      │
 │      └─ YES
 │
 ├─ Does misp-modules start?
 │      │
 │      ├─ NO → Fix python installation
 │      │
 │      └─ YES
 │
 ├─ Do modules list correctly?
 │      │
 │      ├─ NO → Update misp-modules
 │      │
 │      └─ YES
 │
 ├─ Is Plugin.Enrichment_services_enable = true ?
 │      │
 │      ├─ NO → Enable it
 │      │
 │      └─ YES
 │
 ├─ Does Diagnostics show "MISP modules connection: OK"?
 │      │
 │      ├─ NO → Fix service URL/port
 │      │
 │      └─ YES
 │
 ├─ Add VirusTotal API key
 │
 └─ Enrichment works
```

---

# Final Result

You successfully:

- Installed **misp-modules**
    
- Verified module service
    
- Enabled **enrichment services**
    
- Connected MISP to modules
    
- Added **VirusTotal API key**
    
- Enabled enrichment in GUI
    
- Configured **automatic service**
    

---

If you want, I can also show you a **complete MISP architecture diagram (MISP + Redis + Workers + Modules + Feeds)** so you fully understand how the system works. It makes troubleshooting much easier.