
It deals with 
1. creating,
2. scheduling, and 
3. coordinating processes
to <mark style="background: #ABF7F7A6;">ensure efficient CPU utilization and smooth system performance</mark>

Key points to understand:

- <mark style="background: #ABF7F7A6;">Single-tasking systems</mark>: Easy to manage since only one process runs at a time.
- <mark style="background: #ABF7F7A6;"> Multiprogramming/multitasking systems</mark>: More complex, as multiple processes need to share the CPU efficiently.
- <mark style="background: #ABF7F7A6;">Resource sharing</mark>: Active processes may share memory and other resources, requiring <mark style="background: #FF5582A6;">careful management</mark>.
- <mark style="background: #ABF7F7A6;">Process synchronization</mark>: Necessary when processes interact or communicate <mark style="background: #FF5582A6;">to avoid conflicts</mark>.



![[Pasted image 20260126184440.png]]

## CPU-Bound vs I/O-Bound Processes

A CPU-bound process requires more CPU time or spends more time in the running state. An I/O-bound process requires more I/O time and less CPU time. An I/O-bound process spends more time in the waiting state.


- **CPU-bound process**
    
    - Requires **more CPU time** to complete its task.
    - Spends **most of its lifetime in the Running state**.
    - Performs **very little I/O operations**.
    - Examples: <mark style="background: #ABF7F7A6;">mathematical calculations</mark>, data compression, scientific simulations.
        
- **I/O-bound process**
    
    - Requires **more I/O time** (disk, keyboard, network, etc.).
    - Spends **less time using the CPU**.
    - Stays **mostly in the Waiting (Blocked) state**, waiting for I/O to complete.
    - Examples:<mark style="background: #ABF7F7A6;"> file reading/writing</mark>, database queries, user input handling.
        
- **Key difference**
    
    - CPU-bound → performance depends on **CPU speed**.
        
    - I/O-bound → performance depends on **I/O device speed**.

[[CPU Scheduling in Operating Systems]]