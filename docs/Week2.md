**Design a security baseline and performance testing methodology**

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

performance testing plan - 

This performance testing plan explains how I will monitor my Ubuntu Server remotely from my Ubuntu Desktop VM. The goal is to observe CPU, RAM, disk, and network performance using simple, accessible commands.

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Remote Monitoring: 

I will access the server by using the command ( ssh username@SERVER-IP
once i am connected, i will run the basic monitoring commands to collect the right performance data. i will repeat this each and every time before and after configuration changes to measure improvements.
##
Tesing Approach:

for cpu utilisation are will use the command top, the reason for this is to show which processes use the most cpu. this command also help with identifing system load.

will test this by taking a screenshot of top when system is inactive then run a simple workload for example intalling updates and test again.
 ##
Ram Usage:

i will view the memory usage using the command free -h; this command shows me all availabe RAMs help with decting memory pressure and give me a simple output

i run the test by running is before systems updates and run it again after running applications 
##

Disk Usage:

the df -h command will be used to show the disk space usage across mounted filesystems and help me with identifying low storage 
the test process wll me taking screeshots before intalling packages then i will install the software and repeat df -h to show any changes 
##
Network connectivity: 

Commands-

ip addr
ping -c 4 8.8.8.8

ping -c 4 UBUNTU-DESKTOP-IP


Why:

- Confirms correct server IP

- Confirms outbound connectivity


Testing:

- Perform pings before firewall configuration

- Perform again after enabling firewall rules
##
Running Processes:

Command-

ps aux


Why:

Lists all running processes

Helps verify background services such as SSH

Testing:

Capture output before and after securing services

-------------------------------------------------------------------------

**Security Configuration Checklist**
##
SSH Harding 

Protect remote access and prevent unauthorized login attempts

<img width="447" height="179" alt="image" src="https://github.com/user-attachments/assets/098007de-cda5-4044-b556-3545561baa6c" />

commands: 

sudo nano /etc/ssh/sshd_config

sudo systemctl restart ssh


##

Firewall Configuration

Limit network access to essential services only.

<img width="447" height="176" alt="image" src="https://github.com/user-attachments/assets/51657d64-6f05-414b-ad3b-44d903f66f47" />

##

Mandatory Access Control

Restrict applications to least privilege.

<img width="446" height="121" alt="image" src="https://github.com/user-attachments/assets/bdea1af2-fe2d-4ec7-bf87-cd1b5350b533" />

##

Automatic Updates

Keep the server protected against vulnerabilities


<img width="384" height="127" alt="image" src="https://github.com/user-attachments/assets/d0bc3e2f-98c7-4d9f-92c7-7b3f1baa7fdf" />

command: 

sudo apt install unattended-upgrades

sudo dpkg-reconfigure unattended-upgrades

systemctl status unattended-upgrades

##


User Privilege Management

Ensure only authorized users have administrative access


<img width="320" height="162" alt="image" src="https://github.com/user-attachments/assets/bb3539bd-365c-4a3b-86d5-da80895367ba" />


##

Network Security

Reduce attack surface by securing all network connections.

<img width="444" height="178" alt="image" src="https://github.com/user-attachments/assets/bd6c24a4-2a5f-465b-a4c0-be953d3fca2a" />


------------------------------------------------------------------------

**Threat Model**

##

Threat (1)

Attackers commonly scan the internet looking for SSH servers and try to break in using brute-force password attacks. Even if the server is not exposed publicly, weak passwords or default settings increase risk.

How the Attack Could Happen

Weak or reused passwords

SSH root login allowed

Firewall not enabled

SSH running on default port (22) makes detection easier

Impact

Full server compromise

Loss of confidential data

Installation of backdoors or malware

Mitigation Strategies

Disable root login in /etc/ssh/sshd_config

Enforce strong passwords

(Optional) Change SSH port to reduce scanning attempts

Enable UFW firewall with only SSH allowed

Use key-based authentication for stronger protection

##

Threat (2)

If the firewall is not set correctly, services may be open that should not be accessible. This increases attack surface and can expose internal services to unauthorized users.

How the Attack Could Happen

UFW disabled or misconfigured

Multiple open ports visible on the network

Unused services like FTP, SMB, or web servers left running

Impact

Remote exploitation of vulnerable services

Unauthorized access to internal files

DoS attacks if public services are exposed

Mitigation Strategies

Enable UFW and default deny incoming traffic

Allow only required ports (e.g., SSH)

Check open ports regularly using: command ( ss -tuln ).

##

threat (3)

If the server does not receive security updates, it becomes vulnerable to known exploits. Attackers often look for outdated SSH versions, kernel vulnerabilities, or unsafe packages.

How the Attack Could Happen

Disabled or incorrect update settings

Long periods without manual patching

New vulnerabilities published while server is unpatched

Impact

Remote code execution 

Privilege escalation

Loss of data integrity

Malware installation
