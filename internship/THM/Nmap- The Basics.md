
`ping` →
`arp-scan` -->
`ping` won’t give any information if the target system’s firewall blocks ICMP traffic
 `arp-scan` only works if your device is connected to the same network, i.e., over Ethernet or WiFi.
 `telnet` →

IP <mark style="background: #FFB8EBA6;"> range using</mark> `-`  → scan all the IP addresses from 192.168.0.1 to 192.168.0.10, you can write `192.168.0.1-10`

- IP subnet using `/` --> scan a subnet, you can express it as `192.168.0.1/24`, and this would be equivalent to `192.168.0.0-255`

- Hostname: You can also specify your target by hostname, for example, `example.thm`

`nmap -sn 192.168.66.0/24` 

- similar to arp-scan
- When scanning a directly connected network, Nmap starts by sending ARP requests. When a device responds to the ARP request, Nmap labels it with “Host is up”.


- `192.168.11.1`
- `192.168.11.2` 


`nmap -sL 192.168.0.1/24`

This scan only lists the targets to scan without actually scanning them


 Common network services include web servers, which usually listen on TCP ports 80 and 443, and DNS servers, which typically listen on UDP (and TCP) port 53.
### Scanning TCP Ports

how `telnet` will scan (diff tool)

 `telnet` attempt to complete the TCP three-way handshake with every target port; however, only open TCP ports would respond appropriately and allow a TCP connection to be established.

how `nmap` will scan

The connect scan can be triggered using `-sT`. It tries to complete the TCP three-way handshake with every target TCP port. If the TCP port turns out to be open and Nmap connects successfully, Nmap will tear down the established connection.

#### SYN Scan (Stealth)

Unlike the connect scan, which tries to **connect** to the target TCP port, i.e., complete a three-way handshake, the SYN<mark style="background: #D2B3FFA6;"> scan only executes the first step: it sends a TCP SYN packe</mark>t. Consequently, the TCP three-way handshake is never completed. The advantage is that <mark style="background: #D2B3FFA6;">this is expected to lead to fewer logs</mark> as the connection is never established, and hence, it is considered a relatively stealthy scan. You can select the SYN scan using the `-sS` flag.

### Scanning  Ports

- `-p[range]` allows you to specify a range of ports to scan. For example, `-p10-1024` scans from port 10 to port 1024, while `-p-25` will scan all the ports between 1 and 25. Note that `-p-` scans all the ports and is equivalent to `-p1-65535` and is the best option if you want to be as thorough as possible.
- 

| Option      | Explanation                                                   |
| ----------- | ------------------------------------------------------------- |
| `-sT`       | TCP connect scan – complete three-way handshake               |
| `-sS`       | TCP SYN – only first step of the three-way handshake          |
| `-sU`       | UDP scan                                                      |
| `-F`        | Fast mode – scans the 100 most common ports                   |
| `-p[range]` | Specifies a range of port numbers – `-p-` scans all the ports |

Find the listening web server on `10.49.172.185` and access it with your browser. What is the flag that appears on its main page?

![[Pasted image 20260305070947.png]]

8008 ? --> ![[Pasted image 20260305071027.png]]


### OS Detection -O


### Service and Version Detection -sV

 discovered several open ports and want to know what services are listening on them. `-sV` enables version detection. This is very convenient for gathering more information about the target

| Option | Explanation                                          |
| ------ | ---------------------------------------------------- |
| `-O`   | OS detection                                         |
| `-sV`  | Service and version detection                        |
| `-A`   | OS detection, version detection, and other additions |
| `-Pn`  | Scan hosts that appear to be down                    |


Nmap provides various options to control the scan speed and timing.

Running your scan at its normal speed might trigger an IDS(intrusion detection system)

`nmap -sS MACHINE_IP -F`

| Timing          |
| --------------- |
| T0 (paranoid)   |
| T1 (sneaky)     |
| T2 (polite)     |
| T3 (normal)     |
| T4 (aggressive) |

# Verbosity and Debugging

to enable verbose output by adding `-v` →  to get more updates about what’s happening
can increase the verbosity level by adding another “v” such as `-vv` or even `-vvvv`. 

`-d` for debugging

# Saving Scan Report

`grep` command. ?

- `-oN <filename>` - Normal output
- `-oX <filename>` - XML output
- `-oG <filename>` - `grep`-able output (useful for `grep` and `awk`)
- `-oA <basename>` - Output in all major formats

---

`-sC` = **Default NSE (Nmap Scripting Engine) scripts**

These scripts help gather **extra information about the target** such as:

- Service details
- Server configurations
- Known vulnerabilities
- Authentication methods
- Banner information
