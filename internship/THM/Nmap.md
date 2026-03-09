`man nmap`
`nmap -h`
[[Nmap- The Basics]]

 Network connections are made between two ports – an open port listening on the server and a randomly selected port on your own computer.

For example, when you connect to a web page, your computer may open port 49534 to connect to the server’s port 443.

![[Pasted image 20260307192844.png]]

As in the previous example, the diagram shows what happens when you connect to numerous websites at the same time. Your computer opens up a different, <mark style="background: #FF5582A6;">high-numbered port </mark>(at random), which it uses for all its communications with the remote server

Every computer has a total of 65535 available ports;


many of these are registered as standard ports.

HTTP Webservice →  port 80
HTTPS Webservice can be found on port 443
 Windows NETBIOS  → 139
  SMB --> 445

 <mark style="background: #D2B3FFA6;">we begin any attack with a port scan.</mark>


Depending on how the port responds, it can be determined as being open, closed, or filtered (usually by a firewall)

### Port Categories Overview

| Port Range        | Category                | Number of Ports | Description                                            |
| ----------------- | ----------------------- | --------------- | ------------------------------------------------------ |
| **0 – 1023**      | Well-Known Ports        | **1024**        | Reserved for standard protocols (HTTP, FTP, DNS, etc.) |
| **1024 – 49151**  | Registered Ports        | 48,128          | Assigned to specific applications/services             |
| **49152 – 65535** | Dynamic / Private Ports | 16,384          | Temporary ports used by client applications            |
### Examples of Well-Known Ports

| Port  | Service |
| ----- | ------- |
| 20–21 | FTP     |
| 22    | SSH     |
| 23    | Telnet  |
| 25    | SMTP    |
| 53    | DNS     |
| 80    | HTTP    |
| 110   | POP3    |
| 143   | IMAP    |
| 443   | HTTPS   |


## TCP Connect Scans

We have covered the TCP (Transmission Control Protocol) three-way handshake [here](https://medium.com/o/YhUyby9yRWtr5g4pbccz/s/IncHpQE9Q1Ax4cr7Wbpu/~/changes/35/complete-beginner-pathway/network-exploitation-basics/introductory-networking#the-tcp-ip-model) and [here](https://medium.com/@hammaadm/tryhackme-introductory-networking-061c505ed9a9). Nmap tries to connect to each specified TCP port and determines whether it is open or not via the response it receives:

1. If Nmap were to send a TCP request with the SYN flag set to be closed, the target will respond with a TCP RST (Reset) flag set and therefore, nmap can establish that the port is closed.
2. If however, Nmap were to send the request to an open port, the target will respond with a TCP SYN/ACK flag set. This marks that the port is open and nmap will send an ACK flag set back.
3. If nothing is sent back after a request is sent, then the port is protected by a firewall and the port is considered to be filtered.


## UDP Scans

UDP (User Datagram Protocol) connections are stateless. This means that UDP connections rely on sending packets to a target port and hoping that they make it. This is why UDP is very good for connections which rely on speed but the lack of acknowledgement makes UDP scans a lot slower. Due to it being slow, it is recommended to just run the scan on the top ports, not all of them.



When a packet is sent to a UDP port, there should be no response. Nmap will then mark the port as open/filtered (i.e. open but could be firewalled). If it gets a UDP response, then the port is marked as open. However, this is uncommon and generally, a second packet is sent to double-check that the port is open/filtered.

When a packet is sent to a closed UDP port, the target port should respond with an ICMP packet. This clearly identifies the port as a closed port.

The switch for a UDP scan is `-sU`.

![[Pasted image 20260307195120.png]]

### Basic Scan Types

- **TCP Connect Scan (`-sT`)**
    
    - Completes the full TCP **3-way handshake** (SYN → SYN/ACK → ACK).
    - Used when **root/administrator privileges are not available**.
    - Easier for systems to **detect in logs**.
        
- **SYN Scan / Half-Open Scan (`-sS`)**
    
    - Sends **SYN** and waits for **SYN/ACK** response but **does not complete the handshake**.
    - Faster and **stealthier** than TCP Connect.
    - Requires **root/admin privileges**.
        
- **UDP Scan (`-sU`)**
    
    - Scans **UDP ports** instead of TCP.
    - Slower because UDP often **does not send responses**
    - Used to find services like **DNS, SNMP, DHCP**.

---

### Less Common Scan Types

- **TCP Null Scan (`-sN`)**
    
    - Sends a TCP packet **with no flags set**.
    - Used to **bypass some firewalls**.
    - Closed ports usually respond with **RST**.

- **TCP FIN Scan (`-sF`)**
    
    - Sends packets with the **FIN flag**.
    - Closed ports reply with **RST**, open ports ignore it.
    
- **TCP Xmas Scan (`-sX`)**
    
    - Sends packets with **FIN, PSH, and URG flags set** (like a “lit Christmas tree”).
    - Used for **stealth scanning** and firewall evasion.

## TCP Connect scans -sT

###  _TCP three-way handshake_

![[Pasted image 20260307213511.png]]


![[Pasted image 20260307213529.png]]

<mark style="background: #ABF7F7A6;">if port is closed</mark>

![[Pasted image 20260307214108.png]]

- **Nmap sends a TCP packet** with the **SYN flag** to a port.
- If the port is **closed**, the target server replies.
- The reply contains a **TCP packet with the RST (Reset) flag**.
- This response tells **Nmap that the port is closed**.

<mark style="background: #ABF7F7A6;">if the port is open, but hidden behind a firewall?</mark>

- Many firewalls **drop (ignore)** incoming packets.
- **Nmap sends a TCP SYN request** to the target port.
- **No response is received** from the port.
- This usually means a **firewall is blocking the packet**.
- Therefore, Nmap marks the port as **filtered**.

Which RFC defines the appropriate behaviour for the TCP protocol?
RFC9293

## SYN scan

referred to as "_Half-open"_ scans, or _"Stealth"_ scans.

![[Pasted image 20260307215519.png]]

- TCP scans perform a full three-way handshake with the target.  
- SYN scans do not complete the handshake.  
- When the <mark style="background: #ADCCFFA6;">server replies with SYN/ACK, Nmap sends a RST (Reset) packet</mark>.  
-<mark style="background: #ADCCFFA6;"> This stops the connection and prevents the server from continuing the request</mark>.  
- So, the sequence for scanning an open port is:  
  
	1. Nmap sends SYN  
	2. Server replies with SYN/ACK  
	3. Nmap sends RST (connection terminated)

advantages of SYN scans
1. SYN scans are often not logged by applications listening on open ports
2. used to bypass older Intrusion Detection systems
3. significantly faster than a standard TCP Connect scan.

Disadvantages of SYN scans

1. require sudo permissions[1] in order to work correctly in Linux.


SYN scans are the<mark style="background: #FFB86CA6;"> default scans used by Nmap</mark>

**without** sudo permissions, Nmap defaults to the TCP Connect scan


---

## UDP scans -sU

 UDP connections rely on sending packets to a target port and essentially hoping that they make it.
 UDP  connections are for  speed not for quality



| ccondition                           | recives          | Nmap marks     |
| ------------------------------------ | ---------------- | -------------- |
| a packet is sent to an open UDP port | no response      | open\|filtered |
| a packet is sent to an open UDP port | get UDP response | open           |
|                                      |                  |                |

 filtered :- ie port is open but firewalled

When a packet is sent to a _closed_ UDP port, the target should respond with an ICMP (ping) packet containing a message that the port is unreachable

 