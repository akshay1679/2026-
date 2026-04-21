

Perfect question 💯 — this is exactly how a real SOC setup is documented.

I’ll give you a **clean startup checklist**:  
👉 _What to turn on → what commands → where → why_

---

# 🖥️ 🔥 **SYSTEM ARCHITECTURE (Your Setup)**

```
Ubuntu (Snort + Forwarder)
        ↓
Splunk Universal Forwarder
        ↓
Windows (Splunk Enterprise)
```

---

# ⚡ **STEP 1: Power ON Systems**

### ✅ 1. Start **Windows Machine** (Main System)

👉 This runs Splunk Enterprise

### ✅ 2. Start **Ubuntu VM**

👉 This runs:

- Snort (IDS)
    
- Splunk Forwarder
    

---

# 🧠 **Order Matters**

👉 Windows FIRST → then Ubuntu  
(So forwarder has a server to connect to)

---

# 🪟 **STEP 2: Start Splunk Enterprise (Windows)**

### 📍 Run in **Windows CMD (Admin)**:

```cmd
"C:\Program Files\Splunk\bin\splunk.exe" start
```

---

### ✅ Why?

👉 Starts Splunk server  
👉 Opens port **9997** to receive logs

---

### 🌐 Check:

Open browser:

```
http://localhost:8000
```

---

# 🐧 **STEP 3: Start Splunk Forwarder (Ubuntu)**

### 📍 Run in **Ubuntu terminal**:

```bash
sudo /opt/splunkforwarder/bin/splunk start
```

---

### ✅ Why?

👉 Starts log forwarding  
👉 Connects to Windows Splunk

---

# 🐧 **STEP 4: Start Snort (Ubuntu)**

### 📍 Run in **Ubuntu terminal**:

```bash
sudo snort -A fast -q -c /etc/snort/snort.conf -i eth0
```

---

### ⚠️ Replace `eth0` if needed:

```bash
ip a
```

---
### ⚠️⚠️ if it doesnt work

step 1 

run:
```
ip a
```


![[Screenshot 2026-04-15 062419.png]]

this shows that the it is using ens33 so we need to replace the eth0 with ens33

step 2:

```
sudo snort -A fast -q -c /etc/snort/snort.conf -i ens33
```

![[Pasted image 20260415063134.png]]

⬆ now it is working properly

---

### ✅ Why?

👉 Starts IDS (Intrusion Detection System)  
👉 Generates security logs

---

# 🔍 **STEP 5: Verify Forwarding (Ubuntu)**

```bash
sudo /opt/splunkforwarder/bin/splunk list forward-server
```

---

### ✅ Expected:

```
Active forwards:
10.1.20.76:9997
```

![[Pasted image 20260415063533.png]]

⬆ this  is the old ip address so we need to add the new ip address

your issue is clear:

👉 Old IP (`10.1.20.76`) is now **inactive**  
👉 New Windows IP = **`10.1.28.209`**  
👉 Forwarder is still trying old IP → so it shows **inactive**

---

### Adding new ip to splunk forworder

```
sudo nano /opt/splunkforwarder/etc/system/local/outputs.conf
```

replace the server ip address with new one

![[Pasted image 20260415063943.png]]


restart the splunk forwarder:

```
sudo /opt/splunkforwarder/bin/splunk restart
```

then list all  the forworder ip address

```
sudo /opt/splunkforwarder/bin/splunk list forward-server
```

![[Pasted image 20260415064314.png]]

# ⭐ Best and fastest method

```
sudo /opt/splunkforwarder/bin/splunk remove forward-server 10.1.20.76:9997
sudo /opt/splunkforwarder/bin/splunk add forward-server 10.1.28.209:9997
sudo /opt/splunkforwarder/bin/splunk restart
sudo /opt/splunkforwarder/bin/splunk list forward-server
```

---

### ✅ Why?

👉 Confirms connection to Splunk server

---

# 🌐 **STEP 6: Verify Logs in Splunk (Windows)**

Go to Splunk → Search

```spl
index=* | stats count by host
```

---

### ✅ Why?

👉 Confirms logs are arriving

---

# 🧪 **STEP 7: Test Everything**

### 📍 On Ubuntu:

```bash
logger "SYSTEM START TEST"
```

---

### 📍 In Splunk:

```spl
SYSTEM START TEST
```

---

### ✅ Why?

👉 Confirms pipeline is working end-to-end

---

# 🔁 **OPTIONAL: Auto-Start (So You Don’t Do This Every Time)**

## 🔹 Enable Splunk Forwarder Auto Start (Ubuntu)

```bash
sudo /opt/splunkforwarder/bin/splunk enable boot-start
```

---

## 🔹 Enable Splunk Enterprise Auto Start (Windows)

```cmd
sc config Splunkd start= auto
```

---

# 🎯 **FULL STARTUP SUMMARY**

|Step|Machine|Command|Purpose|
|---|---|---|---|
|1|Windows|Power ON|Run Splunk server|
|2|Windows|`splunk start`|Start log receiver|
|3|Ubuntu|`splunk start`|Start forwarder|
|4|Ubuntu|`snort ...`|Generate security logs|
|5|Ubuntu|`list forward-server`|Check connection|
|6|Windows|Splunk search|Verify logs|

---

# 🧠 **SHORT EXPLANATION (Interview Ready)**

👉  
“First, I start the Splunk Enterprise server on Windows to receive logs. Then I start the Splunk Universal Forwarder on Ubuntu to send logs, followed by Snort to generate security events. Finally, I verify log ingestion using Splunk queries.”

---

# 🚀 **Pro Tip (Real SOC Behavior)**

Always check:

```spl
index=* | stats count by host
```

👉 If Ubuntu host appears → system is healthy ✅

---



