
name: **akshay**
roll no: **71**
id: **imf202601dusi279**
### Network Traffic Analysis Overview

This report examines a PCAP file using ntopng and Wireshark to identify suspicious network behavior. The analysis reveals multiple HTTP POST requests sent repeatedly to suspicious domains, containing binary data that appears to be encoded or compressed. This traffic pattern suggests possible malware communication with command-and-control (C2) servers, along with potential data exfiltration activities. These findings indicate that the system may be compromised and require immediate further investigation.

1. We need to download a pcap file from the link https://www.malware-traffic-analysis.net/2025/06/13/2025-06-13traffic-analysis-exercise.pcap.zip 
2.  We have to unzip the file using the password as `infected_20250613`

![[Pasted image 20260422210953.png]]

3. If ntopng instance is running just stop it so that it not create the problem when we try to upload pcap file manually 

![[Pasted image 20260422211930.png]]


4. Then we need to run the ntopng and at the same time upload the pcap file 

![[Pasted image 20260422212057.png]]

5. We can access the ntopng by the localhost:3000 and we can see the uploaded file 

![[Pasted image 20260422212227.png]]

![[Pasted image 20260422212430.png]]

6. We need to apply filters to identify suspicious hosts from the list. We can sort the hosts based on certain criteria to find potentially malicious activity, such as:
	- If the total bytes are high, it means there is a large amount of communication with that host. This may indicate heavy data transfer, which could be suspicious depending on the context. 
	-  If the score is high, it means many packets or flows are marked as suspicious. This suggests that the host may be involved in malicious activity or could be a potential command-and-control (C2) server.  


7. We can see the packets of the malicious host by clicking on Actions corresponding to the Ip address. 
![[Pasted image 20260422212743.png]]
8. Now we need to look for the suspicious traffic for that we can apply filters of ‘HTTP’ and can check the suspicious IPs 
![[Pasted image 20260422212856.png]]


9. We can put the IPs in the website like ‘www.abuseipdb.com’ and can check the authenticity of the IPs 

ip used is 104.21.16.1

![[Pasted image 20260422213313.png]]


ip used is 104.21.80.1

![[Pasted image 20260422213430.png]]


We found that all these IPs were reported as malicious multiple times.


## Analysis based on the packet/network behaviour  

PCAP analysis using ntopng indicates that the host machine is repeatedly making HTTP connections to several suspicious external domains. Many of these domains mimic legitimate services such as Microsoft or use random cloud-hosted addresses. The traffic mainly consists of POST requests, suggesting that data may be transmitted from the infected machine to external servers. The communication is frequent, short-lived, and involves small data transfers, which is consistent with malware beaconing or data exfiltration activity. Based on these observations, the traffic strongly indicates that the system is compromised and is communicating with command-and-control (C2) infrastructure.

9. Now we can use wireshark to view the what types of data carrying inside each malicious packets
![[Pasted image 20260422213753.png]]

10. We are looking for the suspicious domain or IPs like:- eventdata-microsoft.live  windows-msgas.com  trycloudflare.com So, we need to apply filter as :- http.host contains "Microsoft" || http.host contains "cloudflare" 

![[Pasted image 20260422213833.png]]


11. We are interested only in POST request as ‘POST request carries stolen data’ so we can apply filter as the http.host contains "microsoft" || http.host contains "cloudflare" || http.request.method == "POST" 

![[Pasted image 20260422213856.png]]

12. By inspecting a malicious packet such as 104.16.230.132, we can obtain important details such as the POST request path (for example, `/something`), the Host header (for example, `suspicious-domain`), the User-Agent, Content-Type, and Content-Length. We can also identify the full URL of the malicious site, such as `http://varying-rentals-calgarypredict.trycloudflare.com/bmvLMt6UaBCc/22jMpHiZLgaCY4&354f9148f3b439a1433a5327275539f4/r`, which helps in confirming suspicious communication and potential command-and-control (C2) activity.

![[Pasted image 20260422214002.png]]

13. Now, we will try to view the actual data which is carried over here For that we need to view by ‘HTTP stream’ and saving the data as ‘RAW’  

![[Pasted image 20260422214035.png]]


The PCAP file was analyzed using Wireshark and ntopng. The analysis revealed repeated HTTP POST requests from the infected host to multiple suspicious domains, including cloud-hosted and Microsoft lookalike domains. The traffic used the content type `application/octet-stream`, indicating that binary data was being transmitted. Inspection of the HTTP stream showed non-readable payloads, suggesting that the data was compressed or encoded. The repeated communication pattern, along with consistent payload sizes, indicates automated behavior typical of malware beaconing or data exfiltration. Based on these observations, the system is likely compromised and communicating with a command-and-control (C2) server. The presence of compressed or encoded payloads further suggests an attempt to evade detection and conceal transmitted data.
