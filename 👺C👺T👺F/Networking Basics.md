# 2. Networking Basics (Full Detailed Explanation)

Networking basics are one of the most important foundations for CTFs, web security, pentesting, bug bounty, and even general cybersecurity.

Most beginners try to learn “hacking tools” first.

That is a mistake.

Because tools only automate what networking already does.

If you understand networking deeply, tools become easy.

This is also emphasized in your CTF roadmap notes .

---

# Why Networking Matters for CTFs

Almost every attack starts with:

> understanding how systems communicate

Examples:

- finding open ports
    
- discovering hidden services
    
- intercepting HTTP requests
    
- stealing cookies
    
- bypassing authentication
    
- understanding proxies
    
- privilege escalation through network services
    

Without networking knowledge:

CTF becomes guessing.

With networking knowledge:

CTF becomes solving.

---

# Topics You Must Learn

We’ll cover:

1. IP Addresses
    
2. Ports
    
3. TCP vs UDP
    
4. DNS
    
5. HTTP
    
6. HTTPS
    
7. Cookies
    
8. Sessions
    
9. Headers
    
10. Proxies
    
11. Request / Response Flow
    

---

# 1. IP Address

## What is an IP?

IP = Internet Protocol Address

It identifies a device on a network.

Like:

> House address for computers

Example:

```text
192.168.1.10
```

or

```text
8.8.8.8
```

---

# Two Types of IP

## Private IP

Used inside local networks.

Examples:

```text
192.168.x.x
10.x.x.x
172.16.x.x – 172.31.x.x
```

Example:

Your laptop → router → local Wi-Fi

---

## Public IP

Visible on the internet.

Given by ISP.

Example:

```text
49.x.x.x
103.x.x.x
```

This is what websites see.

---

# Why It Matters in CTF

You scan targets using IPs:

```bash
nmap 192.168.1.10
```

You connect to services using IPs:

```bash
ssh user@192.168.1.10
```

---

# 2. Ports

## What is a Port?

A port is like:

> a door to a service

One machine = many services

Each service listens on a port.

Example:

|Service|Port|
|---|--:|
|HTTP|80|
|HTTPS|443|
|SSH|22|
|FTP|21|
|MySQL|3306|
|RDP|3389|

---

## Real Example

IP:

```text
192.168.1.10
```

Port:

```text
80
```

Means:

```text
192.168.1.10:80
```

This means:

> connect to the web server running there

---

# Why Ports Matter in CTF

Finding open ports = first step

Example:

```bash
nmap target-ip
```

Output:

```text
22 open ssh
80 open http
3306 open mysql
```

Now you know:

where to attack.

---

# 3. TCP vs UDP

These are communication methods.

---

# TCP

## Full Form

Transmission Control Protocol

---

## TCP is:

Reliable

Connection-based

Ordered

Checks if data arrives

Like:

> phone call

Example:

“Did you hear me?”

“Yes.”

---

## Used By

- HTTP
    
- HTTPS
    
- SSH
    
- FTP
    
- SMTP
    

---

# UDP

## Full Form

User Datagram Protocol

---

## UDP is:

Fast

No connection

No delivery guarantee

Like:

> shouting across a room

Example:

“HEY!”

Maybe heard, maybe not.

---

## Used By

- DNS
    
- Video streaming
    
- Gaming
    
- VoIP
    
- VPNs sometimes
    

---

# CTF Relevance

Nmap scan:

```bash
nmap -sU
```

means UDP scan.

Different attacks work differently depending on TCP/UDP.

---

# 4. DNS

## Full Form

Domain Name System

---

## What It Does

Converts:

```text
google.com
```

into:

```text
142.250.x.x
```

Because computers use IPs, humans use names.

DNS translates.

---

# Real Example

You type:

```text
facebook.com
```

DNS says:

```text
157.240.x.x
```

Then browser connects.

---

# CTF Relevance

Subdomain enumeration:

```text
admin.site.com
dev.site.com
api.site.com
```

DNS misconfigurations often lead to vulnerabilities.

---

# 5. HTTP

## Full Form

HyperText Transfer Protocol

---

## What It Does

Used for websites.

Browser ↔ Server communication

---

# Example

You open:

```text
http://example.com
```

Browser sends:

```http
GET / HTTP/1.1
Host: example.com
```

Server responds:

```http
200 OK
<html>...</html>
```

---

# HTTP is NOT encrypted

Anyone can read it.

Dangerous for passwords.

---

# CTF Relevance

Most web challenges are HTTP-based.

Understanding requests is critical.

---

# 6. HTTPS

## HTTPS = HTTP + TLS/SSL

Encrypted HTTP

Safe version.

---

# What It Protects

- passwords
    
- cookies
    
- sessions
    
- login requests
    
- payment info
    

---

# Example

```text
https://bank.com
```

Safer than:

```text
http://bank.com
```

---

# CTF Relevance

Certificate issues

SSL bypass

MITM concepts

Sometimes challenges involve bad HTTPS configs.

---

# 7. Cookies

## What is a Cookie?

Small data stored by browser.

Sent to server automatically.

---

# Example

After login:

```http
Set-Cookie: session=abc123
```

Browser stores:

```text
session=abc123
```

and sends it every request.

---

# Why Cookies Matter

They often store:

- login state
    
- session ID
    
- preferences
    
- tracking info
    

---

# CTF Relevance

Stealing cookies can mean:

> stealing accounts

This is common in XSS challenges.

---

# 8. Sessions

## What is a Session?

Server-side tracking of a logged-in user.

---

# Example

You login.

Server creates:

```text
Session ID = xyz789
```

Browser stores it in cookie.

Server remembers:

```text
xyz789 = logged in as admin
```

---

# Difference

Cookie = stored in browser

Session = stored on server

---

# CTF Relevance

Session fixation

Session hijacking

Broken authentication

Very common.

---

# 9. Headers

## What are Headers?

Extra information sent with requests/responses.

Like:

> metadata

---

# Example Request Headers

```http
User-Agent
Cookie
Authorization
Host
Referer
Content-Type
```

---

# Example Response Headers

```http
Set-Cookie
Server
Location
Content-Type
Cache-Control
```

---

# CTF Relevance

Header manipulation often breaks security.

Example:

```http
X-Forwarded-For: 127.0.0.1
```

Sometimes leads to admin access.

Huge topic.

---

# 10. Proxies

## What is a Proxy?

A middleman between you and server.

---

# Flow

```text
You → Proxy → Website
```

instead of

```text
You → Website
```

---

# Why Use It

To:

- intercept requests
    
- modify requests
    
- inspect traffic
    
- replay attacks
    

---

# Most Important Tool

Burp Suite

This is one of the most important tools for CTF web challenges.

You will use it constantly.

---

# CTF Relevance

Without a proxy:

you are blind.

With a proxy:

you see everything.

---

# 11. Request / Response Flow

This is the MOST important concept.

Understand this deeply.

---

# Full Flow Example

You visit:

```text
https://site.com/login
```

---

# Step 1 — DNS

Browser asks:

```text
What is site.com IP?
```

DNS answers.

---

# Step 2 — TCP Connection

Browser connects to:

```text
IP:443
```

---

# Step 3 — TLS Handshake

Secure encrypted channel created.

---

# Step 4 — HTTP Request

Browser sends:

```http
POST /login
username=admin
password=123
```

---

# Step 5 — Server Response

Server replies:

```http
200 OK
Set-Cookie: session=abc
```

---

# Step 6 — Browser Stores Cookie

Now browser is logged in.

---

# Step 7 — Future Requests

Browser sends:

```http
Cookie: session=abc
```

Server knows:

same user.

---

# THIS is Web Security

Almost every web attack happens inside this flow.

SQLi

XSS

CSRF

IDOR

Auth bypass

Session hijack

Everything.

---

# Final Beginner Advice

Don’t memorize.

Instead ask:

> what is happening behind the browser?

That question makes people dangerous in CTFs.

---

# What You Should Practice Next

Immediately after this:

learn:

## Wireshark

and

## Burp Suite

These two tools make networking real.

Without them:

theory stays theory.

With them:

you start seeing attacks.

---

Next after Networking Basics should be:

# 3. Web Vulnerabilities

because that’s where all of this becomes weaponized.