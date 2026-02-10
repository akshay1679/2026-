What BIOS means

BIOS <mark style="background: #FFB8EBA6;">stands for Basic Input/Output System</mark>. It’s low-level firmware stored on a chip on the motherboard. When you power on a PC, the BIOS is the very first thing that runs. It:

1. checks hardware (CPU, RAM, drives)

2. initializes devices

3. hands control to the operating system (Windows, Linux, etc.)


Modern systems technically use UEFI, which is the newer, more capable successor, but people still casually call it “the BIOS.”

Typical things controlled there:

boot order

CPU / memory settings

virtualization options

security features like passwords or Secure Boot



---

What it means to “change the BIOS”

This can mean two different jobs:

1. Change settings → like enabling virtualization or changing boot priority.


2. Update/flash the firmware → installing a new version from the motherboard manufacturer.



They are very different in terms of risk and how remote access works.


---

Can you remotely change BIOS on another computer?

Short answer: usually not, at least not in the way people imagine.

Because BIOS/UEFI runs before the operating system and network tools, remote access software (Remote Desktop, TeamViewer, etc.) normally can’t see or control it.

But there are special cases.


---

1) Enterprise / server hardware (possible)

Business machines sometimes include out-of-band management hardware that works even when the OS is off.

Examples:

Intel AMT / vPro

Dell iDRAC

Hewlett Packard Enterprise iLO


With those, an admin can:

open a remote console

enter BIOS

change settings

mount virtual media

update firmware


This is common in corporate IT and data centers.

If the target PC doesn’t already have this configured → you can’t magically enable it remotely.


---

2) Normal home / office PCs (very limited)

If it’s a regular consumer computer, options are much narrower.

Changing settings

Usually requires:

someone physically at the keyboard, or

remote hands (a person there pressing keys)


You can guide them via video call.

Updating BIOS

Some manufacturers provide Windows tools that can stage an update and reboot automatically.
But:

it still reboots into firmware

if something goes wrong, you may need physical recovery

not every change can be scripted


So it’s “semi-remote,” not true remote control.


---

3) Risk warning (important)

Bad BIOS settings or a failed flash can make a machine unbootable (“bricked”).

If you’re helping another computer remotely, you need:

exact model

correct firmware

stable power

a recovery plan


Otherwise you can create a very expensive paperweight.


---

Reality check

If you’re imagining sitting at home and freely navigating another PC’s BIOS like remote desktop → that typically only happens with enterprise management features that were set up before.


---

If you want, tell me:

the computer or motherboard model

what setting you’re trying to change


…and I can suggest the safest practical way to accomplish it remotely (or the closest workaround).