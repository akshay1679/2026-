A **hypervisor** is the core technology behind virtualization. It's the software that creates and manages virtual machines.


it is a special piece of software that:

- Divides a physical computer into multiple virtual ones.
- Gives each virtual machine its own share of CPU, memory, and storage.
- Keeps everything isolated and safe.
- Manages the lifecycle of virtual machines (start, stop, pause, clone, delete).

Hypervisors have two main types of implementation:

- **Type 1** hypervisors run directly on the physical hardware, making them fast, efficient, and ideal for servers and professional environments.
- - **Type 2** hypervisors run within an existing operating system, making them easier to install and ideal for learning, testing, or small setups.

![[Pasted image 20260209123615.png]]

using virtualization to test malicious files → One approach is to use different operating systems for the guest and host machines, or to isolate the guest machine so that it does not communicate with the host.

What does virtualization enable multiple applications to share?
physical server

## Containers (The Rooms Inside the Apartment)

[[container]]

Containers behave like small, self-contained spaces because:

- They package the application and its dependencies (libraries, tools, versions).
- They share the host’s operating system, so they start almost instantly.
- They remain isolated from each other, so a misbehaving container doesn’t affect the others.
- They can run consistently on any machine, making them perfect for development, testing, and scalable deployments.


![[Pasted image 20260209124139.png]]


## Managing Virtual Machines

