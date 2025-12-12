**Application Selection for Performance Testing**
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
The focus of Week 3 was to select appropriate benchmarking applications and develop a full performance testing methodology. This forms the foundation for practical testing in later weeks.

I evaluated different types of workloads (CPU, memory, disk I/O, network, and server-based) to ensure broad performance coverage.

The methodology outlines how performance testing will be conducted on the Ubuntu Server VM. The approach focuses on evaluating CPU, memory, disk I/O, network throughput, and server performance using selected benchmarking tools.

Testing will be performed in a controlled VirtualBox environment to ensure consistency and repeatability.

##
 
 Application Selection Matrix(before test): 

 

 <img width="1158" height="144" alt="Screenshot 2025-12-12 140253" src="https://github.com/user-attachments/assets/af1d6626-7639-4e60-a29a-abdd36b8ce96" />

##

Install the chosen tools on the Ubuntu Server

steps -

update first : 
sudo apt update && sudo apt upgrade -y

installs :
sudo apt install -y stress-ng fio iperf3 nginx


<img width="794" height="618" alt="image" src="https://github.com/user-attachments/assets/d626397f-a274-42d5-b690-70f92c056487" />

All is installed and updated !
##
Stress version : 

<img width="819" height="47" alt="image" src="https://github.com/user-attachments/assets/f9dc3387-b7f3-4941-80b0-049888337a5c" />

##

Fio version:

<img width="466" height="47" alt="image" 
 src="https://github.com/user-attachments/assets/10eb5074-be92-4be7-acef-60a8efc93e01" />

 ##

 Iperf3 version: 

 <img width="843" height="101" alt="image" src="https://github.com/user-attachments/assets/1d3a5564-b0bd-4b9c-ba1d-3581e3210159" />

 ##

 nginx version: 

 <img width="395" height="49" alt="image" src="https://github.com/user-attachments/assets/8cb3ecee-e677-40ec-9089-6a5a8c712d03" />

 ##

How the testing will be done 
this is each workload test has a step-by-step plan:

CPU Test: Run stress-ng for 60 seconds to saturate CPU cores

Memory Test: Allocate up to 80% RAM using stress-ng

Disk Test: Run fio sequential and random workloads

Network Test: Using iperf3 server/client setup

Server Test: Run ApacheBench against nginx hosting a static webpage



