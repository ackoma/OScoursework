 **Initial System Configuration & Security Implementation**
 -------------------------------------------------------------------------------------------------------------

I configured secure SSH access to the server using key-based authentication. An Ed25519 SSH key pair was generated on my local workstation, and the public key was installed on the server for a non-root administrative user. I verified that SSH access worked successfully using the key without requiring a password. After confirming key-based login, I hardened the SSH configuration by disabling password-based authentication and preventing direct root login in the SSH daemon configuration file. The SSH service was then restarted, and connectivity was retested to ensure secure remote access was functioning as intended.
##
Steps by step to follow to complete task -

Deployed and accessed the server to perform initial system configuration and security hardening.

Created a non-root administrative user and assigned sudo privileges to enforce proper privilege management.

Generated an Ed25519 SSH key pair on the local workstation for secure authentication.

Installed the public SSH key on the server for the administrative user and verified successful key-based login.

Hardened SSH by disabling password-based authentication and preventing direct root login in the SSH daemon configuration.

Restarted the SSH service and confirmed continued access using key-based authentication.

Identified the workstation IP address to be used for restricted remote access.

Configured the server firewall to deny all incoming connections by default and allow SSH only from the authorized workstation IP.

Verified and documented the complete firewall ruleset to confirm correct enforcement.

Demonstrated secure remote administration by executing system management commands over an SSH session(screenshots):

##

PREPARATION (Before touching the server)
- Your workstation IP address :


<img width="644" height="372" alt="image" src="https://github.com/user-attachments/assets/efe0e54f-ca1b-45f6-8cbe-af8ce157c0a3" />


##

UFW version number
Confirms firewall utility is installed :

<img width="703" height="96" alt="image" src="https://github.com/user-attachments/assets/78485537-0003-4bac-91eb-854ed57302cb" />

##

Generate SSH key:

<img width="580" height="276" alt="Screenshot 2025-12-12 210706" src="https://github.com/user-attachments/assets/49c35d87-637f-4a62-b053-2fbb927768ef" />

##

Apply firewall rules (server): 

<img width="569" height="114" alt="Screenshot 2025-12-12 212157" src="https://github.com/user-attachments/assets/1efb00d2-fb87-4872-988a-f221e474765b" />


#

Apply firewall rules (server):

<img width="626" height="156" alt="Screenshot 2025-12-12 212519" src="https://github.com/user-attachments/assets/65e5d77b-c50e-4091-a29c-52aea7f72202" />


##

Create a Non-Root Administrative User:

<img width="624" height="509" alt="Screenshot 2025-12-12 214254" src="https://github.com/user-attachments/assets/383046fc-ec66-4398-91e5-0f7781576a7c" />


##

is used to grant administrative (sudo) privileges to the user adminuser:

<img width="686" height="67" alt="Screenshot 2025-12-12 214528" src="https://github.com/user-attachments/assets/3e596e46-3785-4e7d-a611-9ca4ac2b94b8" />

##

Confirms that the non-root administrative user exists
Demonstrates user management and privilege separation: 

<img width="701" height="78" alt="Screenshot 2025-12-12 214757" src="https://github.com/user-attachments/assets/5ce5a779-5cad-46e3-ac13-9e6237c5cae4" /> 


##

SSH Hardening + Config File Before/After Evidence: 

<img width="943" height="574" alt="Screenshot 2025-12-12 223631" src="https://github.com/user-attachments/assets/e563e5d9-2b33-4324-9345-9b7711f7e19b" />

##


