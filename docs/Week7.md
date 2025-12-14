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


##

To verify the firewall settings, the sudo ufw status verbose command was run on the server. The results confirmed that the default policy blocks all incoming connections and that SSH access is only allowed from the workstation’s IP address. A screenshot was taken as evidence.


<img width="589" height="221" alt="image" src="https://github.com/user-attachments/assets/9fe0058e-8766-436a-b55c-adaa70014b23" />

##

SSH security was checked by reviewing the OpenSSH configuration. The audit showed that root login and password logins were turned off, and only key-based authentication was allowed.

<img width="438" height="114" alt="image" src="https://github.com/user-attachments/assets/800362e2-a8a8-4b7c-afc6-1377366b7909" />

##

Service Audit:


A service audit was carried out on the server by listing all active services using the systemctl command. Each running service was then reviewed and justified. Core services such as ssh (remote administration), ufw (firewall control), AppArmor (access control), fail2ban (intrusion prevention), and unattended‑upgrades (automatic updates) were confirmed as necessary for security and system management. If nginx was running, it was justified as being used for performance testing.


<img width="839" height="449" alt="image" src="https://github.com/user-attachments/assets/dab7f48d-83b5-4de3-b582-e6412c4121b9" />

##

System Configuration Review:

A system configuration check was carried out on the server by running commands such as uname -a, lsb_release -a, free -h, df -h, and ip addr. These commands were used to confirm the operating system version, check memory and storage usage, and verify the network settings. Screenshots of the outputs were taken as evidence.

##

<img width="1018" height="33" alt="image" src="https://github.com/user-attachments/assets/6ae3fe3d-664d-46a8-b61f-c519399aa9a1" />

##

<img width="671" height="62" alt="image" src="https://github.com/user-attachments/assets/5f69a746-4950-42c6-bd63-df4b1e1e3cdb" />

##

<img width="465" height="112" alt="image" src="https://github.com/user-attachments/assets/bccb1e1b-28d9-4e5b-9668-c176ee568805" />

##

<img width="828" height="294" alt="image" src="https://github.com/user-attachments/assets/bab2272b-e107-473e-8e95-c9ef31aaa3cc" />


##


