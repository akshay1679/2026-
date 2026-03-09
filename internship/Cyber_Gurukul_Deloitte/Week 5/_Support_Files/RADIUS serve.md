## 🔐 RADIUS Server (Remote Authentication Dial-In User Service)

A **RADIUS server** is a networking protocol and server system used for **centralized authentication, authorization, and accounting (AAA)**. It is widely used by ISPs, enterprises, and Wi-Fi networks to control access to networks.

---

## 📌 What Does RADIUS Do?

RADIUS provides three main functions:

1. **Authentication** – Verifies user identity (username/password, certificates, tokens).
    
2. **Authorization** – Determines what the user is allowed to access.
    
3. **Accounting** – Tracks usage (login time, data usage, session duration).
    

---

## 🖥️ How RADIUS Works (Basic Flow)

1. A user connects to a network (Wi-Fi, VPN, switch port).
    
2. The network device (called a **NAS – Network Access Server**) sends login credentials to the RADIUS server.
    
3. The RADIUS server checks credentials (local database, Active Directory, LDAP, etc.).
    
4. It responds with:
    
    - **Access-Accept**
        
    - **Access-Reject**
        
    - **Access-Challenge**
        

---

## 📡 Where RADIUS Is Commonly Used

- Enterprise Wi-Fi (WPA2/WPA3-Enterprise)
    
- VPN authentication
    
- ISP broadband authentication
    
- Network switches (802.1X port authentication)
    
- Firewall access control
    

---

## 🛠 Popular RADIUS Server Implementations

### 1️⃣ FreeRADIUS

![Image](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Freeradius_logo.svg/960px-Freeradius_logo.svg.png)

![Image](https://www.magofog.com/assets/img/servers/server-services/radius/radius-server1.png)

![Image](https://documentation.meraki.com/%40api/deki/files/787/FreeRADIUS_configuration_file.jpg?revision=2)

![Image](https://www.freeradius.org/documentation/freeradius-server/3.2.9/concepts/_images/request_flow.svg)

- Open-source
    
- Very flexible and powerful
    
- Runs on Linux/Unix
    
- Most widely used RADIUS server globally
    

---

### 2️⃣ Microsoft Network Policy Server

![Image](https://www.sysadmintutorials.com/images/st/microsoft/windows-2008-r2/nps-install-and-configure/01-microsoft-nps-install.jpg)

![Image](https://learn-attachment.microsoft.com/api/attachments/155249-ad01-nps.png?platform=QnA)

![Image](https://static.tp-link.com/image004_1572250380746z.jpg)

![Image](https://static.tp-link.com/image003_1572250370667j.jpg)

- Built into Windows Server
    
- Integrates with Active Directory
    
- Common in enterprise environments
    

---

### 3️⃣ Cisco Identity Services Engine

![Image](https://www.cisco.com/c/dam/en/us/td/i/400001-500000/410001-420000/416001-417000/416962.tif/_jcr_content/renditions/416962.jpg)

![Image](https://www.cisco.com/en/US/i/200001-300000/230001-240000/239001-240000/239530.jpg)

![Image](https://www.cisco.com/c/dam/en/us/td/i/200001-300000/280001-290000/282001-283000/282089.jpg)

![Image](https://www.cisco.com/c/dam/en/us/td/i/200001-300000/280001-290000/282001-283000/282088.eps/_jcr_content/renditions/282088.jpg)

- Enterprise-grade solution
    
- Advanced access control
    
- Device profiling and security policies
    

---

## 🔒 RADIUS vs TACACS+

- **RADIUS**: Encrypts only the password; commonly used for network access.
    
- **TACACS+**: Encrypts entire payload; commonly used for device administration (routers/switches).
    

---

## 📦 Common Protocol Details

- Default ports:
    
    - UDP 1812 → Authentication
        
    - UDP 1813 → Accounting
        
- Uses shared secret between NAS and RADIUS server
    
- Supports EAP (Extensible Authentication Protocol)
    

---

## 🎯 Example Use Case

A company Wi-Fi network:

- Employees connect using username/password.
    
- Access is checked against Active Directory.
    
- Different VLANs assigned based on department.
    
- Login time and bandwidth usage recorded.
    

---

If you'd like, I can also explain:

- How to set up FreeRADIUS step-by-step
    
- RADIUS configuration example
    
- RADIUS vs LDAP
    
- RADIUS in ISP environments
    
- 802.1X explained clearly
    

Just tell me your goal 🙂