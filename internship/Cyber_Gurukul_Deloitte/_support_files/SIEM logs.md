## What is SIEM?

![[Pasted image 20260310125413.png]]

**SIEM** stands for **Security Information and Event Management**.

A SIEM is a system that **collects logs from many devices in a network and analyzes them for suspicious activity**.

Think of it like a **central security monitoring system**.

---

## Where SIEM Gets Logs From

SIEM collects logs from:

1. Firewalls
2. Servers
3. Endpoint devices (laptops, desktops)
4. Applications
5. Authentication systems (Active Directory)
6. Network devices (routers, switches)
    

Example tools:

- Splunk
- IBM QRadar
- Microsoft Sentinel
    

---

## Example of SIEM Logs

Example log entry:

User: john.doe  
Source IP: 192.168.1.10  
Destination IP: 45.155.205.3  
Action: Login Failed  
Time: 10:22:13

This tells the SOC analyst:

- Who attempted login
- From where
- When it happened
- What action occurred
    

---

## What SIEM Does With Logs

SIEM systems:

1. **Collect logs**
    
2. **Correlate events**
    
3. **Detect suspicious patterns**
    
4. **Generate alerts**
    

Example rule:

If login fails 10 times in 1 minute → Trigger alert

Possible attack:

- **Brute force login attack**
    

