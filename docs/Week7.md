**Security Audit and System Evaluation**

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="313" height="180" alt="image" src="https://github.com/user-attachments/assets/f6a48955-cf05-432c-9a09-d1b2581d2d9b" />





Server: Ubuntu Server

Workstation: Ubuntu Desktop

Access: SSH (key-based)

Security stack: OpenSSH, UFW, AppArmor, fail2ban, unattended-upgrades

##
Infrastructure Security Assessment


A complete security check was carried out on the Ubuntu Server to review how it is set up, how exposed it is, and whether it follows recommended security practices. The check looked at strengthening the system, controlling who can access it, reducing network risks, and turning off unnecessary services.

Lynis Security Audit Results: 

before -

<img width="651" height="121" alt="image" src="https://github.com/user-attachments/assets/59694e4c-23e9-448b-9019-a26f518b67bd" />

after- 

<img width="672" height="139" alt="image" src="https://github.com/user-attachments/assets/ccea06af-82b7-4033-8c15-35df05d08f4a" />

Although the Lynis hardening score didn’t change, the fixes still lowered several configuration risks and resolved multiple recommendations. This shows that some security improvements don’t always show up in automated scores.

##

Network Security Assessment with nmap: 


The server didn’t reply to ping (ICMP) checks, so nmap first thought it was offline. This is normal when a firewall is locked down. Using the -Pn option let nmap scan the ports and services successfully.

##

To check access control on the server, the AppArmor status was reviewed using the sudo aa-status command. The output confirmed that the necessary security profiles were loaded and that AppArmor was running in enforced mode, meaning the system was actively applying its protection rules.


<img width="662" height="188" alt="image" src="https://github.com/user-attachments/assets/44b93b6a-c9d8-4aad-ba50-c24acfd03e2f" />


