this is used in the company bic there is no down time
so in company we cant allow the downtime to occour
soo we use this more

`systemctl start kpatch`

is the command used on systems that have **Kpatch** installed to start the service responsible for managing live kernel patches.


in environments like **BIC** (or any large enterprise), downtime is often unacceptable. That’s exactly where **live kernel patching** with **Kpatch** becomes important.

## 🔧 What Is Dynamic (Live) Patching?

**Dynamic patching** (also called _live kernel patching_) allows you to apply security updates and bug fixes to the Linux kernel **<mark style="background: #ABF7F7A6;">without rebooting the system</mark>**.

Normally:

- Kernel update ➜ **Reboot required** ➜ Downtime

With live patching:

- Kernel update ➜ **No reboot** ➜ **No downtime**