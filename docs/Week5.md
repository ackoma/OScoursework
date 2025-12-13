**Advanced Security & Monitoring Infrastructure**

--------------------------------------------------------------------------------------------------------------

The objective of this task is to enhance the security posture of the Ubuntu Server by implementing advanced security controls and introducing monitoring capabilities. Building on the foundational security implemented in Week 4, this phase focused on access control enforcement, automated security maintenance, intrusion detection, and verification through scripting and remote monitoring.

By the end we want to see that the server had transitioned from a securely configured system to a self-maintaining platform. Advanced security controls were implemented, validated, and documented, meeting all Phase 5 requirements and establishing a strong foundation for future performance analysis and optimization.

##

AppArmor as its default mandatory access control (MAC) framework -


<img width="899" height="256" alt="image" src="https://github.com/user-attachments/assets/f8d1accd-af88-42e4-a681-16bf878f17ac" />


To assess enforcement, the following command was executed:


<img width="476" height="604" alt="Screenshot 2025-12-13 121018" src="https://github.com/user-attachments/assets/d9f5a0a5-c58c-4e40-9993-01451fe399cd" />


##

Document access control reporting (This proves you can track and report AppArmor activity):


<img width="809" height="139" alt="Screenshot 2025-12-13 121152" src="https://github.com/user-attachments/assets/4e9ef60c-fc48-4f82-8306-657c1ee005f3" />

Thats the deliverable all done 

##

Enable automatic security updates: 

<img width="1251" height="328" alt="Screenshot 2025-12-13 121813" src="https://github.com/user-attachments/assets/3cde93b9-f951-43b9-8da8-bd8425cfbd9f" />

##

<img width="822" height="628" alt="Screenshot 2025-12-13 121934" src="https://github.com/user-attachments/assets/b7e4e3cd-ed72-4415-9910-965f5d06b8a5" />

##

checking the 2nd deliverable -


<img width="818" height="257" alt="Screenshot 2025-12-13 122128" src="https://github.com/user-attachments/assets/44fec806-2896-4c20-b9fd-027d558b5eec" /> 

##

Fail2ban - Fail2Ban is an intrusion‑prevention tool designed to protect servers from brute‑force attacks by automatically banning suspicious IP addresses:



<img width="817" height="361" alt="Screenshot 2025-12-13 124838" src="https://github.com/user-attachments/assets/277ff82e-7993-40dc-b737-08a550009e27" />

##

configuration file (jail.local) was created to use the SSH jail with strict retry limits. The configuration limits login attempts and imposed temporary bans on repeated failures.

command using - 

fail2ban-client status
fail2ban-client status sshd :



<img width="499" height="107" alt="Screenshot 2025-12-13 125404" src="https://github.com/user-attachments/assets/45e4e9c6-4371-4bb8-bf80-d5f6ca4a53e1" />

##


<img width="544" height="178" alt="Screenshot 2025-12-13 125439" src="https://github.com/user-attachments/assets/fec46cff-f119-4cc8-9787-f3fc76b1b217" />

the final outcome shows the server now actively detects and mitigates unauthorized login attempts, providing dynamic protection against brute-force attacks.

##

Security Baseline Verification Script: 


<img width="458" height="526" alt="Screenshot 2025-12-13 131126" src="https://github.com/user-attachments/assets/63f4671c-6887-4d21-8709-304479f7534e" />


4th deliverable :


<img width="559" height="445" alt="image" src="https://github.com/user-attachments/assets/dfbf62b2-52d7-4d26-b174-b84b56429556" />


This approach ensures repeatability and allows future audits to confirm that security controls remain intact after updates or configuration changes.

Outcome:
Security configuration is now verifiable through automation, reducing reliance on manual checks.
4th complete.

##
