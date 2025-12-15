**Operating systems**
##
Introduction:

This project focuses on developing practical skills in Linux system administration through the deployment and management of a dual-system virtualised environment. The assignment requires the installation, configuration, and documentation of two interconnected systems: a Linux Server (headless, command-line only) and a Workstation System used to administer the server remotely via SSH
Throughout the seven-week project, the emphasis is placed not on advanced infrastructure design, but on building competence in operating system configuration, security hardening, network setup, and performance monitoring.

 
-----------------------------------------------------------------------------------------------------------------------------------------
1. **System Architecture Diagram:**


<img width="532" height="216" alt="Screenshot 2025-12-11 170100" src="https://github.com/user-attachments/assets/a8772457-5594-449b-b841-8d02aa00912a" />



-----------------------------------------------------------------------------------------------------------------------------------------





Comparing your chosen server distribution with alternatives:

For this project, I selected Ubuntu Server 24.04 LTS as my server operating system.
To justify this choice, I compared it directly with Ubuntu Desktop 24.04 LTS, an alternative that I could also have installed on the server VM.

Both systems come from the same family, but they are optimised for completely different purposes.
Ubuntu Desktop is designed for interactive GUI usage, while Ubuntu Server is optimised for headless (no GUI), command-line administration, and server workloads.
##
Ubuntu Server 24.04 LTS — 
Pros

•	No desktop environment → extremely lightweight

•	Lower RAM/CPU usage

•	More secure (fewer services running)

•	Optimised for SSH remote administration

•	Follows server-grade LTS stability

•	Ideal for learning CLI skills (module requirement)

Use Cases

•	Web servers

•	Database servers

•	Cloud VMs

•	Headless machines

•	Learning Linux CLI & server administration

-----------------------------------------------------------------------------------------------------------------------------------------
**Workstation configuration decision:**

Ubuntu Desktop 24.04 LTS — 
Strengths

Full graphical interface (GNOME)

Easy for beginners to navigate

Preinstalled desktop applications (browser, office apps, etc.)

Better for local development and GUI-based tools

Typical Use Cases

Personal computers

Student laptops

Workstations

GUI-based applications

•	Cloud VMs

•	Headless machines

-----------------------------------------------------------------------------------------------------------------------------------------
**Network configuration**

Adapter 1 (Nat) internet access - 


<img width="940" height="581" alt="image" src="https://github.com/user-attachments/assets/bdf0b9f1-856b-4879-96f0-4910c8481245" />

##
Adapter 2 (Host-Only) ssh - 

<img width="779" height="480" alt="image" src="https://github.com/user-attachments/assets/b69f8add-ae89-46e7-81bf-617383470d2e" />


##
**server network output**

uname is a system information command.
It tells you what kernel, architecture, and system type your Ubuntu Server is running: 

<img width="662" height="71" alt="Screenshot 2025-12-11 193541" src="https://github.com/user-attachments/assets/2a6b2da2-2b3d-4c16-afe3-d38bf8aaeada" />

##
free is a memory reporting command.
It shows how much RAM your system has, how much is used, and how much is free:

<img width="658" height="87" alt="Screenshot 2025-12-11 193602" src="https://github.com/user-attachments/assets/edec6122-780f-4bb1-aa9f-6da7c3342767" />

##
df -h shows how much disk space your system has:

<img width="660" height="115" alt="Screenshot 2025-12-11 193719" src="https://github.com/user-attachments/assets/2fc513e2-97ff-4295-aca9-f2306b987497" />

##

ip addr (or full command: ip address show) displays all network interfaces on your system and their IP addresses:

<img width="581" height="250" alt="image" src="https://github.com/user-attachments/assets/2a18c83a-5966-4067-b24e-3687e598c245" />


##
lsb_release -a shows what Linux distribution you are running:


<img width="363" height="32" alt="Screenshot 2025-12-11 193955" src="https://github.com/user-attachments/assets/045e21c4-bb4a-4dae-adac-b157dcfd4e53" />

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
