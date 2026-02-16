![[Pasted image 20260211100104.png]]

three main features of an EDR,

## Visibility

This is one of the features of **EDR** that makes it unique from other endpoint security solutions

collects detailed data from the endpoints
presents this information in a very structured format to the analyst
The analyst can also access the historical data of any endpoint for threat hunting or any other purpose.
<mark style="background: #ABF7F7A6;">process trees</mark>

## Detection

t incorporates <mark style="background: #ABF7F7A6;">signature-based</mark> detections as well as <mark style="background: #ABF7F7A6;">behavior-based</mark> detections like unexpected user activities
It can also detect fileless malware that resides in memory. 

## Response

empowers analysts to take action on detected threats.
Imagine getting a detection on the EDR with full-fledged details on when, where, and what happened, and you have to opt for the best possible action for that detection.

As an analyst, you may decide to isolate a complete endpoint, terminate a process, or quarantine some files.


# Why do we need an EDR when we already have an Antivirus (AV) on the endpoints?

EDR agent that will collect data from the devices

the VM → vulnerability management

EOL → end of life → check wether the system is updated at the corect time

vulnerability scanning 2 typ
1. [[credential vulnerability scan]]
2. [[non credential vulnerability scan]]

when we need to perform the vulnerability scan we need to make a scope
and also we need o create a list of critical assets and so that the server wont be down by eating up the resources while performing the vulnerability scanning

tools for the resource 
1. ___
2. ___

then we will be performing risk assessment
ie wether the vulnerability is 
1. critical
2. high 
3. medium 
4. low


tis will help the organization say that which one we should we fix first

time to fix it

1. critical  --> immediately ASAP
2. high --> 1 or 2 days
3. medium 
4. low --> 1 to 2 months

