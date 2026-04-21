![[Pasted image 20260413120208.png]]

 four main steps in analyzing malware:
 1. **basic static analysis**, 
 2. **basic dynamic analysis**, 
 3. **advanced static analysis**, and 
 4. **advanced dynamic analysis**.

Here are the **minimal points** version:

### 🔹 Basic Static Analysis

- Analyze malware without running it
- Check file structure, headers, and code

### 🔹 Basic Dynamic Analysis

- Run malware in a safe environment
- Observe system activity, network, and processes

### 🔹 Advanced Dynamic Analysis

- Use advanced tools/sandboxes
- Detect hidden or evasive behavior

### 🔹 Advanced Static Analysis

- Analyze obfuscated/hidden code
- Use deobfuscation and code emulation techniques

 key objectives of advanced static analysis are to discover the malware's capabilities, identify its attack vectors, and determine its evasion techniques.

Tools → disassemblers such as IDA Pro, Binary Ninja, and radare2 are commonly used

## steps..

### 🔹 Advanced Static Analysis Steps

- Identify entry point and system calls
- Examine code sections using tools (debuggers, hex editors)
- Analyze control flow graph (execution path)
- Study system calls to understand behavior
- Determine evasion techniques and potential impact