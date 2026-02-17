**DLL hijacking** (sometimes called _binary planting_ or _DLL search order hijacking_) is a technique where an attacker places a malicious Dynamic Link Library in a location that a program will check **before** the legitimate one. The application then loads the attacker’s file and runs their code.

It’s common on Windows because many programs load DLLs by **name** instead of by full path.

---

## How it works (simple view)

When a program asks Windows for something like:

```
LoadLibrary("version.dll")
```

the system searches a list of directories in order. If an attacker can put a fake `version.dll` earlier in that list, the fake one wins.

Typical search locations include:

1. The folder the application runs from
2. System folders
3. Windows folder
4. Current working directory
5. Directories in the PATH

(Exact behavior can change depending on safe-loading settings.)

---

## Real-world flow

1. Victim downloads or opens a legitimate program.
2. In the same folder sits a malicious DLL with the expected name.
3. The app starts → Windows finds the malicious DLL first.
4. Attacker code executes with the app’s privileges.

If that program runs as admin, the attacker just escalated privileges.

---

## What attackers usually aim for

- Initial execution after a user opens a file/app
- Privilege escalation
- Persistence
- Bypassing application whitelisting

---
## Famous example: Stuxnet

Stuxnet used DLL hijacking among several techniques to get its payload executed on targeted systems.

---

## Why it’s still common

Because developers still:

- Reference DLLs without absolute paths
- Forget to use secure loading flags
- Ship software that runs from writeable directories

---

## How developers prevent it

Good defensive practices include:

✅ Use fully qualified paths  
✅ Use `LoadLibraryEx` with safe flags  
✅ Digitally sign and verify libraries  
✅ Remove write permissions from program folders  
✅ Use Safe DLL Search Mode

---

## How defenders detect it

Security teams often look for:

- DLL files in unusual application directories
    
- Unsigned libraries where signed ones are expected
    
- Programs loading modules from user-writeable paths
    
- EDR alerts on suspicious module loads
    

---

If you want, I can also explain:

- how red teamers test for DLL hijacking opportunities
    
- how to audit software for it
    
- common DLL names attackers abuse
    
- or step-by-step defensive hardening
    

What would you like to dive into?