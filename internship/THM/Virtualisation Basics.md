
## Learning Objectives

- Understand why managing applications on individual physical servers is inefficient.
- Learn how virtualization addresses hardware utilization and scalability challenges.
- Understand the components of a virtual machine.
- Learn how containers have further optimized hardware utilization for applications.

it was “<mark style="background: #ABF7F7A6;">One server = one application</mark>.”

This meant that if a company wanted to run a website, a database, an email service, and an internal app, they would need separate physical servers for each one. The problems were obvious:

- **High cost**: 
- **Low utilization**: 
- **Slow deployment**: 
- **Hard to scale**: 

virtualization → What if multiple applications could share the same physical server safely?

A virtualization layer, called a **[[hypervisor]]**,was introduced to act as a referee between virtual machines and allow each virtual computer to behave independently, like a physical computer.


![[Pasted image 20260209123008.png]]

**This is virtualization:**

- The building = the physical server
- The apartments = virtual machines
- The tenants = applications or operating systems
- The building manager = the hypervisor (the software that divides the building safely)

Each virtual computer, known as a Virtual Machine (VM)  **acts as an independent system**

