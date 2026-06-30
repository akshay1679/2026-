
==yesterday there was a news Google accidentally exposed details of unfixed Chromium flaw==

This vulnerability affects Chromium-based browsers .
A malicious website can abuse Service Workers to keep JavaScript running in the background even after the browser is closed.
This means an attacker could silently use the victim’s browser for activities like DDoS attacks or command-and-control communication without installing traditional malware.
The attacker doesn’t get full system access, but the browser can behave like part of a botnet.

## Question 1

This attack abuses legitimate browser functionality rather than dropping malware. What do you think behavior-based detection is now more important than signature-based detection?

## Question 2

Would EDR solutions typically see this as malicious behavior, or would it blend into normal browser background processes?


---

