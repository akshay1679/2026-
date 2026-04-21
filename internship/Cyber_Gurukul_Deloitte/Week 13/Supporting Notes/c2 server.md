### Command-and-Control (C2) Server

A **C2 server (Command-and-Control server)** is a system used by attackers to **<mark style="background: #FFB8EBA6;">remotely control malware</mark>** running on infected machines.

###  What it does

- Acts as a <mark style="background: #FFB8EBA6;">**central communication hub** between attacker and malware</mark>
- <mark style="background: #FFB8EBA6;">Sends</mark> **instructions (<mark style="background: #FFB8EBA6;">commands</mark>)** to <mark style="background: #FFB8EBA6;">infected systems</mark>
- Receives **data** stolen by the malware

### 🔹 How it works

1. A device gets infected with malware
2. The <mark style="background: #FFB8EBA6;">malware connects to the **C2 server over the internet**</mark>
3. The attacker can then:
    - Execute commands
    - Download/upload files
    - Control the infected machine remotely