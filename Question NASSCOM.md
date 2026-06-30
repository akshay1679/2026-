All your answers are correct. Here is the answer key for quick revision:

Q1
An attacker views and copies 40,000 patient records from a hospital database but modifies nothing, and the system stays fully operational. Which CIA property is primarily violated?
1
Non-repudiation
2
Confidentiality
3
Availability
4
Integrity
+1.00 / -0.00
Q2
A botnet of compromised IoT devices floods a logistics company's order-tracking site, taking it offline for six hours with no data theft or alteration. Which attack type and CIA property does this best match?
1
DDoS, violating Availability
2
Man-in-the-Middle, violating Integrity
3
Phishing, violating Confidentiality
4
SQL injection, violating Confidentiality
+1.00 / -0.00
Q3
A SHA-256 hash computed on a file before transfer does not match the hash computed after transfer, even though the file size looks unchanged. What should the analyst conclude, and which CIA property does this test?
1
The transfer protocol failed completely; this tests Confidentiality
2
No conclusion is possible; this tests Non-repudiation
3
Transfer was successful; this tests Availability
4
The file may have been tampered with in transit; this tests Integrity
+1.00 / -0.00
Q4
A free 'productivity tool' downloaded from a third-party site is later found silently logging keystrokes and uploading them to a remote server, with no self-replication and no ransom demand. How should this be classified?
1
A worm
2
Ransomware
3
Spyware with keylogging functionality
4
A logic bomb
+1.00 / -0.00
Q5
A former contractor's script sits dormant inside a payroll batch job for over a year, then deletes the historical payroll database on the exact anniversary of their termination. Which characteristic best identifies this malware type?
1
It remains inactive until a specific predefined trigger condition is met
2
It self-replicates across all connected systems before activating
3
It requires a host file to spread from system to system
4
It is exclusively delivered through phishing emails
+1.00 / -0.00
Q6
An Indian fintech firm suffers a breach exposing Aadhaar numbers and bank details. Under which regulation must the incident be reported, and within what timeframe?
1
RPWD Act 2016, within 24 hours
2
IT Act 2000, Section 43A, within 72 hours
3
CERT-In Directive 2022, within 6 hours of noticing the incident
4
GDPR, within 30 days, applicable globally
+1.00 / -0.00
Q7
Attackers encrypt a manufacturer's file servers, but before encrypting, they quietly exfiltrated copies of sensitive design documents, then threaten to both destroy the decryption key AND publish the stolen files unless paid. What is this extortion technique called?
1
Standard Denial of Service
2
Double extortion ransomware
3
A Man-in-the-Middle attack combined with phishing
4
Simple ransomware with no extortion element
+1.00 / -0.00
Q8
An organisation's policy requires authentication strength to scale with data classification. Which pairing is correct?
1
Public data should require the strongest authentication
2
Both tiers should use identical, moderate-strength authentication
3
Authentication strength should depend on file size, not sensitivity
4
Top Secret/Restricted data should require the strongest authentication, such as MFA or hardware tokens
+1.00 / -0.00
Q9
A trainee says a trojan 'gallops through networks infecting every machine without user action.' What is the correct explanation for why a trojan is named after the Trojan Horse?
1
Because it disguises itself as legitimate software to trick a user into installing it voluntarily
2
Because it self-replicates and spreads automatically like a worm
3
Because it only targets horse-racing industry systems
4
Because it encrypts files in rhythmic stages
+1.00 / -0.00
Q10
A server hosting valuable customer financial data has several unpatched vulnerabilities and has been repeatedly scanned by known threat actor infrastructure. Using the standard risk equation, how should this risk be expressed?
1
Threat plus Asset Value
2
Threat multiplied by Vulnerability multiplied by Impact
3
Vulnerability multiplied by Asset Value alone
4
Impact divided by Control Strength only
+1.00 / -0.00
Q11
Packets reach a server's NIC but the application processes them incorrectly because segments arrive out of order and duplicated. At which OSI layer does reliable, ordered segment delivery primarily occur?
1
Layer 3, Network
2
Layer 2, Data Link
3
Layer 7, Application
4
Layer 4, Transport
+1.00 / -0.00
Q12
An analyst suspects a compromised Linux server is making an outbound connection to a C2 server and wants to see all active connections and listening ports. Which command provides this?
1
chmod
2
passwd
3
tail /var/log/auth.log
4
netstat -a
+1.00 / -0.00
Q13
A critical database server cannot tolerate any disruption from a false positive blocking legitimate traffic, but the team still needs visibility into attacks. Which deployment choice fits best?
1
Deploy an IDS, since it passively logs suspicious activity without auto-blocking, avoiding disruption risk
2
Deploy an IPS, since it blocks traffic automatically without analyst review
3
Deploy both IDS and IPS with identical rules to eliminate false positives
4
Use only a firewall; neither IDS nor IPS is relevant
+1.00 / -0.00
Q14
A firewall rule blocks all traffic on TCP port 23 while permitting port 22. Why does this configuration make sense?
1
Port 23 is Telnet, which sends credentials in plaintext, while port 22 is SSH, which encrypts traffic
2
Port 23 is reserved for database replication unrelated to remote access
3
Both ports run the same protocol, so the rule has no effect
4
Port 23 is SSH, being blocked in favour of less secure Telnet on port 22
+1.00 / -0.00
Q15
Before applying a downloaded security patch to production, an analyst wants strong assurance the file matches exactly what the vendor published. Which method gives the strongest assurance?
1
Computing SHA-256 hash and comparing it against the vendor's independently published hash
2
Opening the file in a text editor to check it looks reasonable
3
Visually comparing file size to the vendor's download page
4
Running a basic antivirus scan with no detections found
+1.00 / -0.00
Q16
A sensitive provisioning file containing credentials must be transferred to a remote server. Choosing between FTP, unencrypted HTTP, and SFTP, which should the analyst pick and why?
1
Any option is equally secure since all use standard ports
2
FTP, since it separates control and data channels
3
SFTP, since it encrypts both commands and data over SSH on port 22
4
Unencrypted HTTP, since it is widely supported
+1.00 / -0.00
Q17
An analyst suspects ARP poisoning within the LAN and wants to inspect current IP-to-MAC mappings on an affected host for inconsistencies. Which command should be used?
1
ipconfig or ifconfig
2
traceroute or tracert
3
arp -a (or arp -an)
4
netstat -a
+1.00 / -0.00
Q18
A data centre architect wants the failure of any single device or link to NOT bring down communication for the remaining servers. Comparing star versus mesh topology, which offers better fault tolerance and why?
1
Both are functionally identical in fault tolerance
2
Mesh topology, because multiple interconnections reduce single points of failure
3
Star topology, because a failed central device automatically reroutes traffic
4
Bus topology offers the best fault tolerance here
+1.00 / -0.00
Q19
Employees must provide a password plus a time-based OTP from their registered device to access the VPN. Why is this 2FA requirement valuable even if the password is already complex?
1
It removes the need for a password entirely
2
It simply doubles password length, making guessing harder
3
It only protects against malware, not credential theft
4
It requires a second factor the user possesses, so a stolen password alone is insufficient without the device
+1.00 / -0.00
Q20
Firewall log timestamps are consistently nine minutes ahead of Active Directory log timestamps for the same events, and several devices haven't synced their clocks in weeks. Which protocol failure and impact does this describe?
1
NTP failure, undermining accurate timestamp correlation across log sources
2
SNMP malfunction causing clock drift
3
A misconfigured VPN tunnel unrelated to time sync
4
Expected behaviour with no real impact
+1.00 / -0.00
Q21
Investigators seize a suspect's smartphone in a fraud case. Beyond internal flash storage, which component can independently retain call logs and contacts?
1
The SIM card
2
The protective case
3
The external power adapter
4
The display screen
+1.00 / -0.00
Q22
An e-commerce site slows down during flash sales because one web server gets overwhelmed even though multiple identical servers exist. Which component should be added to distribute requests evenly?
1
A VPN concentrator
2
A load balancer
3
A passive IDS
4
A more powerful firewall
+1.00 / -0.00
Q23
A travelling employee connects to corporate resources over untrusted public Wi-Fi. Which technology protects traffic from interception on that network?
1
Disabling Wi-Fi with no alternative
2
Telnet
3
A Virtual Private Network (VPN)
4
Standard unencrypted HTTP
+1.00 / -0.00
Q24
A high-frequency trading platform needs low-latency cabling immune to electromagnetic interference from nearby industrial equipment. Which cable type best satisfies both requirements?
1
Fiber optic cable
2
Coaxial cable
3
Cat6 twisted-pair cable
4
Wireless (Wi-Fi)
+1.00 / -0.00
Q25
An analyst wants to see the exact hop-by-hop path packets take to a remote server, to identify where a connection is failing. Which tool reveals this?
1
arp -a
2
ipconfig
3
chmod
4
traceroute (or tracert)
+1.00 / -0.00
Q26
A service account that normally only logs in once nightly for backups suddenly generates 480 failed logins in two minutes at 3:47 PM from an unfamiliar external IP. What does this pattern suggest?
1
A benign DNS resolution delay
2
A brute-force or credential-stuffing attack targeting the account
3
An undocumented maintenance window
4
A user accidentally triggered the backup manually
+1.00 / -0.00
Q27
Logs arrive at the SIEM from a Windows server, a Linux server, and a cloud app, each using different timestamp formats. What process must occur before meaningful cross-source correlation?
1
Log compression for storage savings only
2
Log encryption
3
Log normalisation, converting formats into a consistent structure
4
Log deletion of redundant entries
+1.00 / -0.00
Q28
A highly secure, bandwidth-constrained network zone needs log filtering applied locally on each device before transmission. Which log collection method best fits this?
1
SNMP traps only
2
No collection method is needed
3
Agent-based log collection, which can filter locally before forwarding
4
Agentless log collection
+1.00 / -0.00
Q29
A CISO wants a platform that aggregates logs from firewalls, servers, endpoints, and cloud services, correlates them, and surfaces prioritised alerts. Which platform type matches this?
1
An endpoint antivirus console only
2
A standalone next-gen firewall
3
A Security Information and Event Management (SIEM) platform
4
A manual spreadsheet log tracker
+1.00 / -0.00
Q30
During a live incident, an analyst needs to capture and inspect network packets at a granular level, including headers and payload, between a suspected host and an external IP. Which tool is built for this?
1
Wireshark
2
A password manager
3
SailPoint
4
Nessus
+1.00 / -0.00
Q31
User 'r.singh' logs in successfully from Bengaluru at 10:02 AM, then from São Paulo at 10:09 AM IST — a physically impossible travel time. What does this anomaly suggest?
1
Normal behaviour for international offices
2
Account credentials are likely compromised and used from two illegitimate locations
3
A logging hardware fault
4
Normal remote work behaviour
+1.00 / -0.00
Q32
Which organisation specifically issues early-warning advisories about newly discovered vulnerabilities and best-practice guidance, distinct from a simple CVE listing database?
1
The CERT Coordination Centre (CERT)
2
A commercial antivirus marketing site
3
A generic social media platform
4
NASSCOM, a skill development body
+1.00 / -0.00
Q33
Comparing signature matching against behavioural baselining, which method can detect a brand-new attack technique with no existing signature?
1
Neither method can ever detect new attacks
2
Anomaly detection based on behavioural baselining
3
Signature-based matching, due to its comprehensive database
4
Both are equally capable since they use the same data
+1.00 / -0.00
Q34
A SOC integrates a commercial threat intelligence feed of known malicious IPs and hashes directly into the SIEM's correlation engine. What is the primary benefit during alert triage?
1
It eliminates the need for any manual analyst review at all
2
It replaces the need for a SIEM entirely
3
It enriches internal events with external context, helping analysts quickly recognise known IOCs and prioritise response
4
It guarantees zero false positives forever
+1.00 / -0.00
Q35
Firewall logs show 200 connection attempts from one external IP to 200 different ports on the same server within three minutes, mostly reset immediately. What does this resemble?
1
An authorised scan that always follows this exact pattern
2
A routine DNS lookup process
3
Port scanning reconnaissance mapping the attack surface
4
Normal application traffic from one client
+1.00 / -0.00
Q36
An organisation wants a tool that analyses protocols, applications, and behavioural patterns to produce rich connection metadata (like Zeek), beyond simple signature matching. Which category fits?
1
A simple endpoint antivirus scanner
2
A password auditing tool
3
A physical badge reader system
4
A network traffic analysis (NTA) tool
+1.00 / -0.00
Q37
A junior analyst argues that a few minutes of clock drift across servers 'shouldn't matter much.' Why is accurate time synchronisation actually critical in a SOC?
1
It is mainly a cosmetic concern for reports
2
SIEM tools automatically correct for any drift
3
It only matters for billing systems
4
Inconsistent timestamps make it hard to correctly sequence and correlate events, hindering investigation and forensics
+1.00 / -0.00
Q38
Outbound traffic from a subnet rises 300% above baseline over four hours with no signature alert triggering. What should the analyst's next step be?
1
Dismiss it since no signature fired
2
Shut down the entire network immediately
3
Investigate further, since a significant baseline deviation can indicate exfiltration even without a matching signature
4
Wait exactly 24 hours before acting
+1.00 / -0.00
Q39
How do SNMP traps differ from continuous polling for collecting status from network devices?
1
A trap is generated by the device itself and sent in real time when a significant event occurs, rather than relying on polling
2
Traps exclusively encrypt log data in transit
3
Traps only work on Windows-based devices
4
Traps require the collector to query each device every few seconds
+1.00 / -0.00
Q40
A firewall log shows an inbound connection from a known malicious IP, an IDS flags a matching exploit signature, and an endpoint log shows a new process spawning shortly after. What technique combines these into one picture?
1
Log encryption, unrelated to combining sources
2
Backup verification of recent backups
3
Time correlation across multiple log sources
4
Log deletion to save storage
+1.00 / -0.00
Q41
A workstation repeatedly sends DNS queries containing long, random-looking subdomain strings to an external server throughout the day. What technique does this resemble?
1
A misconfigured printer hostname lookup
2
Normal web browsing DNS lookups
3
A routine software licence check
4
DNS tunnelling, used to covertly exfiltrate data or maintain C2 communication
+1.00 / -0.00
Q42
A SOC manager wants to retain baseline visibility into critical authentication events even during a major SIEM outage. Which design principle addresses this risk?
1
Disabling logging during maintenance windows
2
Storing all logs exclusively within the SIEM with no other copy
3
Relying on weekly manual dashboard screenshots
4
Maintaining redundant log storage, such as local retention or a secondary platform, independent of a single SIEM's availability
+1.00 / -0.00
Q43
What is the key distinction between 'log monitoring' and 'real-time threat detection' as SIEM capabilities?
1
Log monitoring covers centralised collection and historical review, while real-time detection analyses incoming data as it arrives to alert promptly
2
Log monitoring only applies to firewalls, detection only to antivirus
3
They are identical with no distinction
4
Real-time detection is impossible without deleting historical logs
+1.00 / -0.00
Q44
An account lockout threshold is reached for a privileged account, then minutes later that account logs in successfully from an unfamiliar workstation, followed by creation of a new domain admin account. What does this sequence suggest?
1
A routine, scheduled AD health check
2
A benign software licence renewal
3
A likely brute-force compromise followed by privilege escalation via an unauthorised admin account
4
A user who simply forgot their password and got IT help
+1.00 / -0.00
Q45
An organisation wants to ensure an attacker with admin access to a compromised server cannot quietly erase that server's security logs to cover their tracks. Which approach best mitigates this?
1
Disabling logging on privileged accounts
2
Storing logs only locally on each server
3
Giving all admins unrestricted write access to the central log store
4
Forwarding logs in near real time to a centrally access-controlled SIEM, so forwarded copies remain protected even if the source is compromised
+1.00 / -0.00
Q46
A SIEM alert flags a 15 GB outbound transfer from the Finance file server at 2:15 AM on a Sunday, when no activity is scheduled. What should the analyst's first step be?
1
Publicly announce the incident on social media
2
Investigate related logs to determine if this is authorised, such as a backup, or potential exfiltration
3
Disregard the alert since large transfers happen occasionally
4
Permanently delete the server's network configuration
+1.00 / -0.00
Q47
An analyst is given a file hash, a suspicious domain, and an IP seen communicating with a compromised host. What category of data do all three represent?
1
Compliance audit checklist items
2
User credentials requiring reset
3
Standard, benign configuration parameters
4
Indicators of Compromise (IOCs)
+1.00 / -0.00
Q48
A SOC maps detections to MITRE ATT&CK categories like 'Initial Access' and 'Privilege Escalation' rather than relying only on malware signatures. What is the primary benefit?
1
It provides a structured taxonomy of attacker TTPs, enabling broader behaviour-based detection coverage
2
It replaces the need for any SIEM
3
It is used only for marketing the SOC's capabilities
4
It guarantees complete prevention of all future attacks
+1.00 / -0.00
Q49
A vulnerability assessment finds a critical, actively exploited CVE on an internet-facing portal with a public exploit. How should this be prioritised against lower-severity internal findings?
1
Deprioritised, since internal findings are always more sensitive
2
Ignored until the next quarterly patch cycle
3
All findings remediated strictly in discovery order regardless of severity
4
Treated as highest priority given public exposure and active exploitation
+1.00 / -0.00
Q50
A CND analyst receives an automated intrusion alert. What should they do before formally escalating it?
1
Conduct initial triage, correlating with other sources and threat intel to assess credibility before deciding on escalation
2
Assume every alert is a false positive and close it
3
Wait exactly one week regardless of severity
4
Notify the press and regulators immediately without internal review
+1.00 / -0.00
Q51
A database server's query volume from one application account triples versus its 30-day baseline for that time of day, with no matching signature triggering. What principle allows this to still be flagged?
1
Baseline behaviour profiling, flagging significant deviations from established normal activity
2
Log encryption, unrelated to behavioural deviation
3
Manual visual inspection of hardware temperature
4
Random sampling with no statistical basis
+1.00 / -0.00
Q52
Deep packet inspection reveals a huge volume of TCP SYN packets from thousands of distinct source IPs hitting one port, with very few handshakes completing. Which attack does this indicate?
1
A misconfigured DNS resolver retrying harmlessly
2
A routine database backup generating noise
3
A SYN flood DDoS attack exhausting server connection resources
4
A legitimate spike in customer traffic during a launch
+1.00 / -0.00
Q53
Several Finance workstations, which normally only contact a small whitelist of banking IPs, begin making low-volume connections to one new external IP roughly every 60 seconds. What does this resemble?
1
Command-and-control (C2) beaconing from compromised hosts
2
A benign NTP synchronisation request
3
Normal whitelisted banking integration traffic
4
A simultaneous, benign Windows Update check
+1.00 / -0.00
Q54
An analyst has already aggregated and normalised log data with contextual enrichment. According to the standard threat-identification methodology, what is the next step before threat correlation?
1
Deleting the normalised data to save storage
2
Generating the final report before patterns are identified
3
Identifying trends and patterns using baselines, real-time monitoring, and statistical or ML techniques
4
Immediately initiating containment without further analysis
+1.00 / -0.00
Q55
An analyst combines automated scanning, limited manual testing, and severity-based ranking to find exploitable weaknesses before they're exploited. What broader activity does this represent?
1
Incident response documentation, occurring only after an incident
2
Data backup verification, unrelated to weaknesses
3
Vulnerability assessment
4
Employee performance review
+1.00 / -0.00
Q56
An analyst documents a detected event's timestamp, hostname, severity, description, and initial containment action in detail. Why capture this level of structured detail rather than a brief note?
1
To satisfy a purely bureaucratic requirement
2
To support accurate tracking, shift handoff, and a reliable historical record for trend analysis and audits
3
To replace any further technical investigation
4
To intentionally make the incident look more severe
+1.00 / -0.00
Q57
Antivirus flags a legitimate, digitally signed admin tool used daily for remote management, based on a generic heuristic rather than confirmed malicious behaviour. How should this be classified and handled?
1
As a confirmed, high-severity ransomware infection requiring full isolation
2
Left unresolved with no documentation
3
As a false positive; document it and consider tuning the rule or creating an exception
4
Escalated directly to law enforcement
+1.00 / -0.00
Q58
An employee account slowly exfiltrates data in small increments over weeks, never triggering volume-based alerts. Which SIEM capability specifically addresses this gap?
1
Monitoring network hardware temperature only
2
Pure signature-based malware scanning
3
UEBA, which detects subtle, gradual deviations from a user's normal behaviour over time
4
Automatic account termination after 90 days
+1.00 / -0.00
Q59
An employee in Accounts Payable can both create AND independently approve vendor payments with no second approver. Which principle is violated, and why is it high risk?
1
No recognised principle, since both relate to one function
2
Only Least Privilege, since they have more access than needed
3
Separation of Duties, since a single person can both create and approve without oversight, risking undetected fraud
4
Only physical security policy
+1.00 / -0.00
Q60
A graph visualisation tool maps IPs, domains, and accounts, revealing a hidden cluster of three hosts communicating with the same external IPs resembling lateral movement. What does this graph approach reveal that a flat list of log entries would not?
1
It only works for exactly two hosts
2
It automatically blocks flagged IPs without review
3
It eliminates the need to review any underlying log data
4
It visually surfaces relationships and clusters across entities, exposing attack pathways harder to spot in isolated entries
+1.00 / -0.00
Q61
A colleague suggests a single automated vulnerability scan alone is sufficient for assessing cyber health. Why is this insufficient under a comprehensive cyber health assessment?
1
Because cyber health also requires risk assessment, controls evaluation, incident response readiness, and continuous threat intel monitoring
2
Because automated scans are always inaccurate
3
Because scans only apply to cloud systems
4
Because risk assessment and controls evaluation are redundant
+1.00 / -0.00
Q62
An audit finds 40% of servers run end-of-life operating systems no longer receiving patches. Why does this represent an ongoing rather than one-time risk?
1
End-of-life status only affects licensing cost
2
These systems remain permanently vulnerable to newly discovered flaws with no vendor patches ever coming
3
This finding has no bearing on security posture
4
End-of-life systems become more secure as fewer people use them
+1.00 / -0.00
Q63
A VPN login from an unfamiliar country at 1 AM is followed by an obfuscated PowerShell process, then an attempt to access an HR share the account has never touched. What does this sequence suggest, and what action follows?
1
A likely multi-stage attack warranting immediate escalation and full investigation
2
A routine, undocumented software deployment
3
An unannounced penetration test requiring no action
4
Three unrelated, benign coincidences requiring no action
+1.00 / -0.00
Q64
A risk framework classifies risks into technical, operational, compliance, and strategic categories before scoring them. Why categorise rather than rank everything in one undifferentiated list?
1
Categorisation has no practical benefit
2
Categorisation only applies to low-priority risks
3
It routes risks needing different remediation expertise and ownership to the right teams rather than treating them identically
4
Categorisation is solely a legal formality
+1.00 / -0.00
Q65
A policy prioritises the customer payment platform highest, internal inventory systems medium, and internal chat tools lowest. A vulnerability affects both the payment platform and the chat tool with limited resources. Which approach matches the policy?
1
Defer both until the next annual review
2
Prioritise the payment platform first given its direct customer and compliance impact
3
Remediate only the chat tool, since internal systems are inherently more sensitive
4
Remediate both with exactly equal priority
+1.00 / -0.00
Q66
An analyst records a new event's timestamp, source, and observations. Which stage of standard threat handling comes immediately after recording?
1
Ticket closure
2
Post-incident analysis
3
Detection, analysing the event to determine its nature and impact
4
Remediation
+1.00 / -0.00
Q67
An alert is confirmed as triggered by an authorised vulnerability scan during an approved window. Beyond closing the ticket, what reflects mature SOC practice to reduce future alert fatigue?
1
Escalating it to executive management as a critical incident
2
Taking no further action beyond closing the ticket
3
Reviewing and tuning the detection rule or documenting an exception for this recurring activity
4
Permanently disabling the rule for all future activity of any kind
+1.00 / -0.00
Q68
A critical incident exceeds its SLA due to complexity requiring specialised forensic skills the analyst lacks. What is the appropriate next step?
1
Reassign it to an unrelated department such as HR
2
Close it and mark it resolved regardless of actual status
3
Continue working alone indefinitely without informing anyone
4
Escalate per the defined matrix to a specialised IR team or external experts
+1.00 / -0.00
Q69
A junior analyst consults the SOC's validated knowledge base entry matching a current incident. What is the primary benefit compared to investigating from scratch?
1
It eliminates the need for any human review permanently
2
It guarantees the new incident is identical in every respect
3
It lets the analyst leverage validated root-cause analysis and proven steps, reducing resolution time, while still verifying the match
4
It only helps with hardware failures, not security threats
+1.00 / -0.00
Q70
A SOC manager argues 24x7 monitoring (not just business hours) is essential for a healthcare org handling PHI under HIPAA. What is the best compliance justification?
1
Continuous monitoring is purely a marketing differentiator
2
Compliance frameworks expect continuous controls; gaps outside business hours risk delayed breach detection and penalties
3
Compliance only applies to physical security, not monitoring
4
HIPAA has no requirements related to monitoring or detection capability
+1.00 / -0.00
Q71
Ticket A is an active, spreading ransomware infection; Ticket B is a low-risk USB-use policy question. How should turnaround time differ?
1
Ticket B should be prioritised since it's simpler to resolve
2
Ticket A should get a much shorter, urgent TAT; Ticket B can have a longer TAT
3
TAT should depend only on which analyst is free first
4
Both should receive identical turnaround times regardless of content
+1.00 / -0.00
Q72
A confirmed breach of customer financial data may trigger mandatory regulatory notification. Based on defined escalation criteria, what should the analyst do?
1
Escalate to executive leadership and legal/compliance teams, given the regulatory and business impact
2
Resolve only the technical issue and avoid contacting legal entirely
3
Wait until the next quarterly review meeting
4
Handle it entirely alone without informing anyone else
+1.00 / -0.00
Q73
Following a phishing incident, which action belongs to the 'eradication' phase specifically, as distinct from containment or recovery?
1
Isolating the affected workstation from the network
2
Removing malware and addressing the root cause such as the phishing vector
3
Holding a lessons-learned review weeks later
4
Restoring the workstation to normal business operation
+1.00 / -0.00
Q74
A board member asks why detailed metrics like MTTD and MTTR are necessary in weekly SOC reports rather than a simple 'everything is fine.' What is the best justification?
1
It provides transparency into actual posture, supports informed resource decisions, and creates an auditable, compliance-relevant record
2
Metrics like MTTD and MTTR don't reflect SOC effectiveness
3
Such reports are required only for organisations under 50 employees
4
Detailed reporting exists purely to look busier
+1.00 / -0.00
Q75
Under Zero Trust, which scenario best illustrates the gap it closes compared to a legacy perimeter-trust model?
1
An attacker who has already compromised one internal workstation attempting lateral movement to a sensitive database, which legacy models might implicitly trust due to internal location
2
A user accessing a public, unauthenticated company website
3
A scenario involving only physical access controls
4
An external attacker with no valid credentials at all, blocked by both models equally
+1.00 / -0.00
Q76
An analyst documents a full incident timeline from alert to closure. Beyond a historical record, what additional analytical value does this provide?
1
It serves only as an ISO formality with no operational benefit
2
It enables calculating response time metrics to benchmark SOC performance and identify process bottlenecks
3
No value beyond a basic log entry
4
It is useful only for calculating overtime pay
+1.00 / -0.00
Q77
An incident has moderate asset criticality but matches early-stage tactics of a known sophisticated threat group per recent intel. What is the most defensible classification decision?
1
Always default to lowest priority when ambiguity exists
2
Ignore threat intel and classify based only on asset age
3
Lean toward higher priority given the threat intel context, since underestimating could let a serious attack escalate
4
Classification should be decided by a coin flip in ambiguous cases
+1.00 / -0.00
Q78
Executive summaries go to senior management while detailed technical reports go to IT security teams for the same incident. What is the rationale for this differentiated communication?
1
Tailoring is purely a formality with no benefit
2
Technical teams should never receive business impact context
3
Senior management is legally barred from any technical detail
4
Different audiences need different depth and framing to make decisions relevant to their role, improving actionability
+1.00 / -0.00
Q79
An incident response playbook outlines predefined roles and steps for a phishing-to-credential-compromise scenario. What is the primary benefit of following this playbook during a live matching incident?
1
It enables a faster, more consistent response by predefining roles and proven steps, reducing decision time under pressure
2
It eliminates the need for any analyst judgement under all circumstances
3
Following a playbook removes any need for further review at all
4
Playbooks help only with incidents that have never occurred before
+1.00 / -0.00
Q80
A post-incident review finds detection was delayed for hours because a critical log source was never integrated into the SIEM. What is the most appropriate concrete outcome?
1
Keep the finding confidential and never document it
2
Disband the post-incident review process entirely
3
No action needed, since the incident is already resolved
4
Prioritise integrating the missing log source and updating monitoring procedures to close the blind spot
+1.00 / -0.00
Q81
An investigator must decide whether to capture RAM contents first or power down a suspect workstation first. What is the biggest risk of powering down before capturing RAM?
1
RAM contents are automatically saved to disk before shutdown
2
Volatile data in RAM, like running processes and decryption keys, will be permanently lost once powered off
3
Powering down has no effect on RAM data
4
Powering down automatically encrypts the hard drive
+1.00 / -0.00
Q82
Web application logs show SQL-syntax fragments in a parameter, and a matching IDS alert flags it as a known exploit signature. What attack is being attempted, and what's the first verification step?
1
A man-in-the-middle attack; replace all network cabling
2
A logic bomb activation; review employee termination records
3
A DDoS attack; shut down all web servers immediately
4
A SQL injection attempt; review access and database logs to see if malicious queries actually executed
+1.00 / -0.00
Q83
An admin logs in during an approved maintenance window versus an unknown external IP successfully authenticating outside that window with credentials not belonging to the admin. How should these be classified?
1
The admin's login as benign; the unknown external login as a likely malicious compromise needing investigation
2
Both as benign, since both involve successful logins to the same server
3
Both as malicious regardless of context
4
The benign event as the more serious incident
+1.00 / -0.00
Q84
A government agency's breach exposing Aadhaar and biometric data could likely have been prevented by routine vulnerability assessment. What does this illustrate about proactive assessment?
1
Proactive assessment allows weaknesses to be identified and fixed before attackers exploit them, reducing breach likelihood and impact
2
This case shows vulnerability assessments are ineffective
3
Aadhaar-related systems are exempt from such assessments
4
Vulnerability assessments are only useful retroactively to assign blame
+1.00 / -0.00
Q85
A confirmed breach of customer financial data has regulatory and reputational implications. Which stakeholder combination is most appropriate to validate the full scope?
1
IT Operations, Legal/Compliance, and Business Continuity or Executive Leadership, alongside the Security Analyst team
2
Only the SOC analyst who first detected the alert
3
Only the marketing department
4
Only external law enforcement, with no internal involvement
+1.00 / -0.00
Q86
Ransomware encrypts a file server, disrupts a switch's routing capacity, and corrupts domain controller authentication records simultaneously. What does this illustrate?
1
Only physical security systems were affected
2
Only software components were affected
3
Only cloud components were affected
4
Data, network, and authentication components were all impacted, showing how a single incident cascades across multiple ICT categories
+1.00 / -0.00
Q87
An attacker exploits a previously undisclosed vulnerability with no available patch. Why does this zero-day classification make defence harder?
1
Zero-days only affect unsupported operating systems
2
With no patch or known signature, traditional defences are ineffective, requiring behavioural detection and defence-in-depth instead
3
Zero-days are documented in CVE databases before being used
4
Zero-days are always less sophisticated and easier to detect
+1.00 / -0.00
Q88
A suspicious document's metadata shows a modification date predating its claimed acquisition date, with an inconsistent author name. What investigative value does this provide?
1
Metadata only applies to image files, not documents
2
It can reveal inconsistencies that raise questions about the document's true origin and authenticity
3
Metadata is permanently destroyed once a file is opened
4
Metadata has no evidentiary value and should be disregarded
+1.00 / -0.00
Q89
A colleague suggests skipping impact assessment and jumping straight to severity categorisation during CND triage, to save time. Why is this risky?
1
Impact assessment only matters for physical hardware damage
2
Severity categorisation not grounded in proper impact assessment risks over- or under-prioritising the incident
3
Skipping it has no consequence since categorisation is arbitrary
4
Impact assessment should only happen after full resolution
+1.00 / -0.00
Q90
An investigator uses disassemblers and debuggers to dissect a malicious binary's functionality and C2 mechanisms. What insight does this provide beyond a simple signature match?
1
Reverse engineering only recovers deleted files
2
Deeper understanding of the malware's behaviour and exploit techniques, informing more targeted countermeasures
3
No additional insight beyond a basic antivirus scan
4
It automatically removes the malware from all systems
+1.00 / -0.00
Q91
A contractor with legitimate access quietly copies sensitive reports to personal cloud storage, planning to share them with a competitor. Why is this an insider threat, and why is it hard to detect?
1
This scenario doesn't qualify as any recognised threat category
2
It's external since the contractor isn't full-time
3
Insider threats can only be accidental, never deliberate
4
It's an insider threat because the individual has legitimate access; such activity can resemble normal usage, making detection harder
+1.00 / -0.00
Q92
Beyond confirming a DDoS, what extra value does packet-attribute analysis (SYN flags, spoofed IPs, botnet sources) provide?
1
Attribute analysis is only useful for encrypted traffic
2
It can identify the specific technique used and trace botnet infrastructure, informing more targeted mitigation
3
No additional value beyond a basic traffic volume graph
4
It's used solely for bandwidth billing purposes
+1.00 / -0.00
Q93
Multiple failed logins are followed by a success from the same IP, and the employee confirms they simply forgot their password. How should this event be classified?
1
A confirmed insider threat requiring termination
2
Malicious, since any failed attempt indicates an attack
3
A critical zero-day exploit regardless of explanation
4
Benign, since intent, impact, and context all point to unintentional, authorised activity
+1.00 / -0.00
Q94
An organisation with a large hybrid cloud footprint is choosing between a continuous, cloud-aware monitoring tool and a traditional, scheduled, on-premises-only scanner. Which factor should weigh most heavily?
1
Tool selection is irrelevant since all tools are identical
2
Only the lower upfront licensing cost matters
3
The on-prem scanner is always superior since manual review eliminates false positives entirely
4
The continuous, cloud-aware tool likely fits better, since it tracks frequently changing cloud assets that the on-prem scanner would miss
+1.00 / -0.00
Q95
An analyst documents log excerpts, packet captures, and a file hash that may later support legal proceedings. Why does maintaining a clear chain of custody matter here?
1
Chain of custody is unnecessary unless evidence is shown to executives
2
It establishes who handled evidence and when, demonstrating it hasn't been tampered with, keeping it credible for legal or regulatory use
3
Chain of custody is solely law enforcement's responsibility, never the SOC's
4
Chain of custody only applies to seized hardware, never digital logs
+1.00 / -0.00
Q96
A SIEM correlates three low-severity events across three systems within 15 minutes — an unusual allowed connection, a new scheduled task, and a group membership change for the same user — flagging it as a potential coordinated attack. What capability is this, and why is it valuable?
1
A hardware failure in storage infrastructure
2
Basic log storage with no analytical capability
3
The SIEM's billing module, unrelated to detection
4
Event correlation, identifying multi-stage patterns across systems that isolated review might miss
+1.00 / -0.00
Q97
As log volume grows, the SIEM experiences hours-long processing delays before new logs become searchable. What limitation does this illustrate, and what typically causes it?
1
This is a strength, since delays improve accuracy
2
A licensing cost issue unrelated to processing
3
Scalability limitation, where some platforms struggle with high-volume data, undermining real-time detection
4
A problem unique only to cloud SIEM deployments
+1.00 / -0.00
Q98
An automated rule blocking any IP with 5+ high-severity alerts per hour accidentally blocks a legitimate partner integration, disrupting business. What risk does this illustrate?
1
This incident has no bearing on how rules should be reviewed
2
Automation must be carefully tuned and tested, since overly broad rules can disrupt legitimate traffic alongside the intended benefit
3
SIEM platforms should never include automation
4
Automated actions carry no risk and need no testing
+1.00 / -0.00
Q99
An analyst validates an IPS alert via Wireshark and determines it was a legitimate, authorised penetration test. What should be documented, and what follow-up is appropriate?
1
Document it as a false positive and consider adjusting or whitelisting the rule during future authorised test windows
2
Permanently disable the IPS for the rest of the year
3
Document it as a confirmed exploit and notify law enforcement
4
Take no action at all, including no documentation
+1.00 / -0.00
Q100
A SIEM ties together a WAF SQL injection alert, an EDR alert on the same server, and a cloud storage misconfiguration shortly after. What advantage does this multi-source integration provide?
1
No advantage over reviewing each system's logs in isolation
2
It reconstructs a unified attack timeline across layers, revealing the full scope of one coordinated attack
3
It is useful only for compliance reporting, not active investigation
4
It is only relevant for organisations with no cloud infrastructure
+1.00 / -0.00
Q101
A custom malware variant avoids matching known signatures but still tries to disable security tools and establish persistence. Which detection approach is most likely to still catch it, and why?
1
Only signature-based detection, since it's most reliable regardless of novelty
2
Anomaly-based detection always fails against custom malware
3
None of the approaches can ever detect unseen malware
4
Heuristic analysis, which flags suspicious behavioural patterns even without a matching signature
+1.00 / -0.00
Q102
Beyond network and endpoint logs, an organisation integrates ERP logs into its SIEM to catch unauthorised financial module access. Why is this added integration justified?
1
ERP logs are redundant with endpoint logs
2
Application-layer integration only matters for tiny organisations
3
Application logs reveal business-logic-level threats, like fraudulent transactions, invisible at the network or endpoint layer
4
Application-specific logs add no visibility beyond network/endpoint logs
+1.00 / -0.00
Q103
An IPS alert turns out to be from a newly deployed but undocumented internal vulnerability scanner, wasting investigation time. What process fix best addresses the root cause?
1
Increasing IPS sensitivity further
2
Improving change management so new internal tools and their behaviour are documented and communicated to the SOC in advance
3
Disabling the IPS entirely to avoid future false positives
4
Firing the analyst who investigated the alert
+1.00 / -0.00
Q104
The SIEM automatically logs every analyst action and status change across an incident's lifecycle. Beyond the immediate investigation, what long-term value does this audit trail provide?
1
It supports process improvement, compliance evidence, and training material for future similar incidents
2
Audit trails are never actually reviewed by anyone
3
Audit trails matter only for incidents resulting in termination
4
No value beyond resolving the specific incident
+1.00 / -0.00
Q105
A vendor argues only the licensing fee matters when comparing SIEM options. Why is this narrow framing misleading?
1
Licensing fees are always the only relevant cost factor
2
Hardware and training costs are always negligible
3
It ignores hardware, training, and maintenance costs that together form the true TCO, and a cheaper licence could cost more overall
4
TCO only matters for cloud SIEM, never on-premises
+1.00 / -0.00
Q106
A WAF flags a request with a script tag embedded in a public forum comment, designed to run in other users' browsers. Which attack is this, and what's its typical goal?
1
A man-in-the-middle attack intercepting server-database traffic
2
SQL injection targeting the database directly
3
DDoS, aiming to overwhelm the server
4
Cross-Site Scripting (XSS), typically aiming to steal cookies or perform actions on a victim's behalf
+1.00 / -0.00
Q107
NetFlow data shows a print server unusually contacting many distinct external IPs in a short period. What value does NetFlow provide here versus full packet capture?
1
NetFlow data can only come from cloud infrastructure
2
NetFlow contains decrypted application payload identical to full capture
3
No meaningful value beyond what system logs already show
4
An efficient, high-level summary of communication patterns, well suited to spotting unusual connections without analysing full payloads
+1.00 / -0.00
Q108
A privileged account has a failed login from one external IP, then a success from a different external IP 40 minutes later, then disables several audit logging settings. What should the analyst's immediate action be?
1
Treat it as low priority, since password attempts are common
2
Immediately contain the affected account and server, then escalate for full investigation given the likely compromise and cover-up attempt
3
Close it as routine, since logging changes are sometimes legitimate
4
Wait for the next scheduled weekly review
+1.00 / -0.00
Q109
A login redirect feature blindly trusts a user-supplied URL parameter, letting attackers craft a legitimate-looking link that redirects victims to a malicious site post-login. Which vulnerability is this, and what's the best mitigation?
1
Broken authentication; mitigated by MFA
2
Cross-Site Scripting; mitigated by a Content Security Policy
3
SQL injection; mitigated by parameterised queries
4
Unvalidated redirects and forwards; mitigated by validating URLs against expected destinations or using server-side redirect logic
+1.00 / -0.00
Q110
An app exposes invoice IDs directly in URLs, and incrementing the ID lets a logged-in user view other customers' invoices without any authorisation check. Which vulnerability is this?
1
A Distributed Denial of Service vulnerability
2
Broken authentication from weak passwords
3
Insecure Direct Object Reference, lacking proper authorisation checks on predictable object identifiers
4
Security misconfiguration from an outdated server
+1.00 / -0.00
Q111
An audit finds default admin passwords on legacy devices, an overly permissive firewall rule, and disabled optional security features left at default. What single category covers all three findings?
1
SQL injection vulnerabilities
2
Security misconfigurations, creating exploitable weaknesses despite no inherent software flaw
3
Zero-day exploits, since none were previously identified
4
Insider threats
+1.00 / -0.00
Q112
A junior analyst proposes performing Eradication before Containment to remove malware as fast as possible. Why is this sequence considered incorrect?
1
Eradicating before containing risks letting the threat keep spreading while remediation is underway; containment should generally come first
2
The proposed sequence is actually correct in all scenarios
3
Eradication and containment are identical with no real sequencing difference
4
Recovery must occur before both stages in all cases
+1.00 / -0.00
Q113
An incident needs specialised malware reverse-engineering skills the team lacks, and also involves a likely PII breach with regulatory notification implications. Which resources should be engaged?
1
No escalation; the team should develop missing skills on demand
2
A specialised IR team or external forensic experts for the technical gap, plus Legal/Compliance for the regulatory dimension
3
Only the marketing team, since public messaging is most urgent
4
Only external law enforcement, with no internal involvement
+1.00 / -0.00
Q114
A SIEM health check reveals the primary firewall stopped sending logs three weeks ago due to an unnoticed config change. What is the most appropriate immediate priority?
1
Restore the log forwarding immediately and assess whether incidents may have occurred undetected during the blind spot
2
Wait for the next annual health check cycle
3
Decommission the SIEM entirely over one missing log source
4
No action required, since the SIEM itself works normally
+1.00 / -0.00
Q115
A full backup runs Sunday, with incremental backups each other night. Ransomware hits the SIEM server Thursday afternoon. Which backups must be restored, and in what order?
1
Only the Sunday full backup; incrementals are never required
2
Backups in reverse order, newest first
3
Only the most recent Wednesday incremental, with no reference to the full backup
4
The Sunday full backup first, then each incremental in order (Mon, Tue, Wed) to rebuild the latest pre-attack state
+1.00 / -0.00
Q116
RPO is 4 hours and RTO is 1 hour for a firewall platform, but backups run only every 24 hours with a manual ~3-hour restore process. What gap does this reveal?
1
RPO and RTO describe encryption standards, not backup frequency
2
The 24-hour backup frequency far exceeds the 4-hour RPO, and the 3-hour restore exceeds the 1-hour RTO, showing both need improvement
3
Only the RTO target is missed; RPO is fully satisfied
4
No gap; the current strategy fully meets both targets
+1.00 / -0.00
Q117
A SOC manager insists on periodic restore tests even though backup jobs always report 'success.' Why is this still justified?
1
Restore testing is unnecessary if job status always shows success
2
Restore testing only matters for cloud backups, never on-premises
3
A 'success' status only confirms the job ran without error, not that the file is uncorrupted or actually restorable; restore testing is the only real validation
4
Restore testing should only happen once, right after implementation
+1.00 / -0.00
Q118
An organisation prioritises minimal restoration complexity for its financial database, even at the cost of more storage. Should it choose incremental or differential backups, and why?
1
Both require an identical restoration process
2
Incremental, since it always uses less storage and is simplest in every scenario
3
Neither is relevant; only full backups should ever be used
4
Differential, since restoring needs only the last full backup plus the most recent differential, simpler than chaining multiple incrementals
+1.00 / -0.00
Q119
Proposal A adds a dedicated physical server for every new security tool; Proposal B consolidates tools via virtualisation with dynamic resource allocation. From a sustainability perspective, which is preferable, and why?
1
Proposal A, since dedicated servers always provide better security regardless of energy use
2
Both have identical environmental impact
3
Proposal B, since virtualisation reduces the total physical machines needed, lowering electricity and cooling demands
4
Sustainability has no relevance to data centre decisions
+1.00 / -0.00
Q120
An IP linked by threat intel to a ransomware affiliate logs into the VPN using a finance employee's valid credentials while that employee is on leave; an EDR alert then flags an obfuscated PowerShell process disabling antivirus on their workstation, followed by a large outbound transfer to an unapproved external IP, and finally a new domain admin account appears using derived credentials. What is the most appropriate immediate action?
1
Close it as a false positive since the credentials were technically valid
2
Treat it as a likely active, multi-stage intrusion; immediately contain the workstation and disable affected/new accounts while escalating to incident response
3
Wait until the employee returns from leave in two weeks to ask them directly
4
Dismiss it as routine remote work, since VPN logins and PowerShell are common
+1.00 / -0.00

|Q|Answer|
|---|---|
|1|**2** – Confidentiality|
|2|**1** – DDoS, Availability|
|3|**4** – Integrity|
|4|**3** – Spyware/Keylogger|
|5|**1** – Trigger-based activation (Logic Bomb)|
|6|**3** – CERT-In, 6 hours|
|7|**2** – Double Extortion Ransomware|
|8|**4** – Strongest auth for Top Secret/Restricted|
|9|**1** – Disguises as legitimate software|
|10|**2** – Threat × Vulnerability × Impact|
|11|**4** – Transport Layer|
|12|**4** – `netstat -a`|
|13|**1** – IDS|
|14|**1** – Telnet vs SSH|
|15|**1** – Compare SHA-256 hashes|
|16|**3** – SFTP|
|17|**3** – `arp -a`|
|18|**2** – Mesh topology|
|19|**4** – Second factor possession|
|20|**1** – NTP failure|
|21|**1** – SIM card|
|22|**2** – Load Balancer|
|23|**3** – VPN|
|24|**1** – Fiber Optic|
|25|**4** – Traceroute|
|26|**2** – Brute-force/Credential stuffing|
|27|**3** – Log Normalization|
|28|**3** – Agent-based collection|
|29|**3** – SIEM|
|30|**1** – Wireshark|
|31|**2** – Impossible Travel / Compromised Account|
|32|**1** – CERT|
|33|**2** – Anomaly Detection|
|34|**3** – Threat Intel Enrichment|
|35|**3** – Port Scanning|
|36|**4** – NTA|
|37|**4** – Accurate Event Correlation|
|38|**3** – Investigate anomaly|
|39|**1** – SNMP Trap|
|40|**3** – Time Correlation|
|41|**4** – DNS Tunneling|
|42|**4** – Redundant Log Storage|
|43|**1** – Monitoring vs Real-time Detection|
|44|**3** – Brute-force + Privilege Escalation|
|45|**4** – Centralized Protected Logging|
|46|**2** – Investigate first|
|47|**4** – IOCs|
|48|**1** – ATT&CK maps TTPs|
|49|**4** – Highest Priority|
|50|**1** – Initial Triage|
|51|**1** – Baseline Profiling|
|52|**3** – SYN Flood|
|53|**1** – C2 Beaconing|
|54|**3** – Identify Trends & Patterns|
|55|**3** – Vulnerability Assessment|
|56|**2** – Tracking & Auditing|
|57|**3** – False Positive|
|58|**3** – UEBA|
|59|**3** – Separation of Duties|
|60|**4** – Relationship Visualization|
|61|**1** – Cyber Health is broader|
|62|**2** – No future patches|
|63|**1** – Multi-stage Attack|
|64|**3** – Proper Ownership|
|65|**2** – Prioritize Payment Platform|
|66|**3** – Detection/Analysis|
|67|**3** – Tune Rules|
|68|**4** – Escalate|
|69|**3** – Use Knowledge Base|
|70|**2** – Continuous Monitoring|
|71|**2** – Ransomware gets shortest TAT|
|72|**1** – Escalate to Leadership & Legal|
|73|**2** – Eradication|
|74|**1** – Metrics show effectiveness|
|75|**1** – Lateral Movement (Zero Trust)|
|76|**2** – Measure MTTD/MTTR|
|77|**3** – Higher Priority due to Threat Intel|
|78|**4** – Audience-specific reporting|
|79|**1** – Faster Consistent Response|
|80|**4** – Integrate Missing Logs|
|81|**2** – RAM is Volatile|
|82|**4** – SQL Injection|
|83|**1** – Context-based classification|
|84|**1** – Proactive Security|
|85|**1** – Security + Legal + Business|
|86|**4** – Multi-component Impact|
|87|**2** – No Patch/Signature|
|88|**2** – Metadata reveals inconsistencies|
|89|**2** – Wrong Severity if Impact skipped|
|90|**2** – Reverse Engineering|
|91|**4** – Insider Threat|
|92|**2** – Better Mitigation Intelligence|
|93|**4** – Benign Activity|
|94|**4** – Cloud-aware Continuous Monitoring|
|95|**2** – Chain of Custody|
|96|**4** – Event Correlation|
|97|**3** – Scalability Issue|
|98|**2** – Automation Risk|
|99|**1** – False Positive + Whitelisting|
|100|**2** – Unified Attack Timeline|
|101|**4** – Heuristic Detection|
|102|**3** – Business Logic Visibility|
|103|**2** – Better Change Management|
|104|**1** – Audit Trail Benefits|
|105|**3** – Total Cost of Ownership|
|106|**4** – XSS|
|107|**4** – NetFlow Metadata|
|108|**2** – Immediate Containment|
|109|**4** – Unvalidated Redirects|
|110|**3** – IDOR|
|111|**2** – Security Misconfiguration|
|112|**1** – Containment before Eradication|
|113|**2** – IR Team + Legal|
|114|**1** – Restore Log Source|
|115|**4** – Full + Incrementals|
|116|**2** – Both RPO & RTO Missed|
|117|**3** – Test Restores|
|118|**4** – Differential Backup|
|119|**3** – Virtualization|
|120|**2** – Active Intrusion → Contain & Escalate|

**Score: 120/120 if you selected these answers.**

Key topics heavily tested:

- CIA Triad
    
- Malware Types
    
- Networking & OSI
    
- SIEM/SOC Operations
    
- Incident Response
    
- Vulnerability Management
    
- Threat Intelligence & MITRE ATT&CK
    
- Backups (RPO/RTO)
    
- Zero Trust
    
- Digital Forensics
    
- Authentication & Access Control
    

This is very close to the type of questions commonly asked in SOC Analyst, Cyber Defense Analyst, and NASSCOM cybersecurity assessments.