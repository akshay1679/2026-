
<mark style="background: #ABF7F7A6;">**IAM policies** are rules that define **who can do what with which resources** in a system</mark>. Most people encounter them in cloud platforms (especially **AWS**, but also Azure and Google Cloud).

![[Pasted image 20260130102411.png]]


https://github.com/kdeldycke/awesome-iam

USER  --> request --> action --> on what particular resource the subject is trying to perform the action

We’ll go in **3 blocks** (same as your PDFs):

1. **Secure Design Principles**
2. **Access Control & Models (DAC, MAC, RBAC, ABAC)**
3. **Federated Identity Management (FIdM)**

---

# 1️⃣ Secure Design Principles (FOUNDATION)

These are **rules for designing secure systems**, proposed by **Saltzer & Schroeder (1975)** — still used today

### 👉 Big idea:

> Security should be built **into the design**, not added later.

---

## 🔹 Principle of Least Privilege (VERY IMPORTANT)

**Definition:**  
Each user/process gets **only the minimum permissions needed**.

**Examples:**

- Linux file → read + write, **not execute**
- Website user → can **read**, cannot **upload or modify**

**Why it matters:**

- Reduces attack surface
- Limits damage if compromised
- Improves accountability

📌 **Exam one-liner:**

> Least privilege limits permissions to reduce risk.

---

### Quick check 🧠

If a student only needs to **view grades**, should they have permission to **edit grades**?  
(Just answer yes/no)

---

## 🔹 Defense in Depth

**Definition:**  
Use **multiple layers of security**, so if one fails, others still protect you.

**Layers include:**

- Physical (ID cards, fingerprint)
- Network (firewalls, IDS)
- Administrative (policies, roles)
- Antivirus
- Behavioral analysis (ML detecting anomalies)

📌 **Key idea:**

> Security failure is often due to **human error**, not just software.

---

## 🔹 Securing the Weakest Link

**Weakest link = easiest thing to attack**

Examples:

- Weak passwords
    
- Default admin credentials
    
- Untrained users
    
- Outdated software
    
- Leaky APIs
    

📌 **Rule:**

> A system is only as secure as its weakest component.

---

## 🔹 Fail-Safe Stance

If a system **fails**, it should:

> **Deny access**, not allow it.

**Default deny** ✅ (secure)  
**Default permit** ❌ (dangerous)

Example:

- Firewall crashes → blocks all traffic
    

---

## 🔹 Secure by Default + Simplicity + Usability

- Secure settings enabled **out of the box**
    
- Simple systems = fewer bugs
    
- If users don’t understand security → they bypass it
    

---

### 🧠 Mini-summary (remember this):

> Least privilege + multiple layers + fail-safe defaults = secure design

---

# 2️⃣ ACCESS CONTROL (WHO can do WHAT on WHICH resource)

### Core terms (VERY EXAM-IMPORTANT)

|Term|Meaning|
|---|---|
|**Subject**|User / process requesting access|
|**Object**|Resource (file, DB, system)|
|**Access Mode**|read, write, execute, delete|

📌 **Formula:**

> **Subject → Action → Object**

---

## 🔹 Access Control Models

### 1️⃣ DAC – Discretionary Access Control

- Owner decides permissions
    
- Uses ACLs, file permissions
    
- Flexible but less secure
    

**Example:**  
Linux file permissions

---

### 2️⃣ MAC – Mandatory Access Control

- Controlled by **central authority**
    
- Users **cannot change permissions**
    
- Very secure, not flexible
    

**Example:**  
SELinux, military systems

---

### 3️⃣ RBAC – Role Based Access Control ⭐

- Permissions → Roles → Users
    
- Most common in companies
    

**Example:**

- Student → view grades
    
- Faculty → upload grades
    
- Admin → manage users
    

---

### 4️⃣ ABAC – Attribute Based Access Control

- Based on attributes:
    
    - user.department
        
    - access time
        
    - location
        

**Policy example:**

> IF user.role = doctor AND location = hospital → allow

---

### 🧠 Quick comparison question

Which is **more flexible**: RBAC or ABAC?  
(Answer one word)

---

## 🔹 Information Flow Control (IFC)

Ensures data **does not flow from high security → low security**

Protects against:

- **Covert channels**
    
- **Timing attacks**
    
- **Storage channels**
    

📌 **Exam line:**

> IFC prevents unauthorized data leakage.

---

# 3️⃣ Federated Identity Management (FIdM)

### Simple meaning:

> **Login once, access many systems across organizations**

Example:

- College login → IEEE, Google Scholar, GitHub Student Pack
    

---

## 🔹 Core Components

|Component|Role|
|---|---|
|**User**|Person logging in|
|**IdP**|Authenticates user (college)|
|**SP**|Service (IEEE)|
|**Token**|Proof of authentication|
|**Trust**|Agreement between IdP & SP|

---

## 🔹 How FIdM Works (Flow)

1. User opens IEEE
    
2. IEEE redirects to college login
    
3. User authenticates
    
4. IdP issues token (SAML / OIDC)
    
5. IEEE verifies token
    
6. Access granted (no new account!)
    

---

## 🔹 Protocols

|Protocol|Used by|
|---|---|
|SAML|Universities|
|OIDC|Google, GitHub|
|WS-Fed|Microsoft (legacy)|

---

## FINAL 10-MARK ANSWER (YOU CAN MEMORIZE)

> Secure design principles guide the construction of secure systems using concepts like least privilege, defense in depth, fail-safe defaults, and usability. Access control restricts resource usage using models such as DAC, MAC, RBAC, and ABAC. Federated Identity Management enables Single Sign-On across organizations using trusted Identity Providers and protocols like SAML and OIDC.

---


1. Subject (who)
⬇️
2. Action (what)
⬇️
3. Resource (on what) -> (File,Database,servers/cloud)
⬇️
4. Effect (Allow or Deny) -> (when/how)
⬇️
5. Condition (when/How)  -->
can access the resource in a particular resource in a particular physical location


[[Types of IAM Policies]]

[[IAM lifecycle]]
