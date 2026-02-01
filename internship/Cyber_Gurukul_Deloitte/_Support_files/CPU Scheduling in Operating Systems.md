CPU scheduling is the process of deciding which process will own the CPU to use while another process is suspended.

Different purposes of a CPU scheduling time.
1. Maximize the CPU utilization
2. Minimize the [[response]] and waiting time of the process.


<mark style="background: #FFB8EBA6;">Arrival Time</mark> The time at which the <mark style="background: #FF5582A6;">process arrives in the ready queue</mark>.
<mark style="background: #FFB8EBA6;">Completion Time</mark> The time at which the <mark style="background: #FF5582A6;">process completes its execution</mark>.
<mark style="background: #FFB8EBA6;">Burst Time</mark> Time required by a process for CPU execution.
<mark style="background: #FFB8EBA6;">Turn Around Time</mark> Time<mark style="background: #FF5582A6;"> Difference between completion time and arrival time</mark>.

<mark style="background: #FFB8EBA6;">Waiting Time</mark> = Turn Around Time  –  Burst Time

### **1. CPU Utilization**

This means **how busy the CPU is**.

- If the CPU is working all the time → utilization is high
    
- If the CPU is idle or waiting → utilization is low
    

👉 The goal --> <mark style="background: #FFB8EBA6;">keep the CPU busy as much as possible</mark>, but not overloaded.  
In <mark style="background: #ADCCFFA6;">real systems,  usually stays between 40% and 90% </mark>depending on how much work there is.

---

### **2. Throughput**

Throughput means <mark style="background: #ABF7F7A6;">how much work the CPU gets done in a given time</mark>.

- Example: If the <mark style="background: #ABF7F7A6;">CPU completes 10 processes in 1 second, the throughput is high</mark>
    
- If it completes **only 2 processes**, throughput is low
    

👉 More completed processes in less time = **better throughput**.

---

### **3. Turnaround Time**

Turnaround time is **the <mark style="background: #ABF7F7A6;">total time taken by a process from start to finish</mark> .

It includes:

- <mark style="background: #FFB8EBA6;">Time waiting in line
    
- Time using the CPU
    
- Time waiting for input/output</mark>
    
👉 In simple words:  
**“How long did the process take overall?”**

---

### **4. Waiting Time**

Waiting time is <mark style="background: #FFB8EBA6;">how long a process waits before getting the CPU. </mark>

- It does **not** include the time when the process is actually running

- It only includes time spent waiting in the ready queue

👉 Scheduling mainly tries to **reduce waiting time**.

---

### **5. Response Time**

Response time is **<mark style="background: #FFB8EBA6;">how quickly the system reacts to a request</mark>**.

- It is the time from when a process is submitted

- Until the **first output or response appears**

👉 This is very important in **interactive systems** (like typing commands, using apps), where users want **quick feedback**, even if the process isn’t finished yet.

---

![[Pasted image 20260126200829.png]]


https://www.geeksforgeeks.org/operating-systems/introduction-of-process-management/

