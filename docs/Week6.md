 **Performance Evaluation and Analysis**

 ---------------------------------------------------------------------------

To begin for this task performance‑testing workflow,evidence folders were created on both the server and workstation to keep all collected data organized. On the server, directories for baseline measurements, load tests, optimization attempts, and logs are prepared, while the workstation receives folders for raw data, processed datasets, and charts. With the structure in place, baseline testing is performed on an idle system by gathering key system metrics such as the current time, uptime, memory usage, disk space, network configuration, and a snapshot of active processes

##

Baseline testing
commands used: 

##

date | tee ~/week6/baseline/time.txt

<img width="531" height="63" alt="image" src="https://github.com/user-attachments/assets/d4f73287-1d2a-46c2-9f6f-19c009139d19" />

##

uptime | tee ~/week6/baseline/uptime.txt


<img width="543" height="57" alt="image" src="https://github.com/user-attachments/assets/e65ce608-cbde-4a34-b69a-0c8cc3d7bd97" />

##

free -h | tee ~/week6/baseline/free.txt

<img width="746" height="100" alt="image" src="https://github.com/user-attachments/assets/51dbbca6-5575-4053-aa0b-a17cdfe05609" />

##

df -h | tee ~/week6/baseline/df.txt 

<img width="542" height="139" alt="image" src="https://github.com/user-attachments/assets/a0b5f5c5-9372-4e2e-bc60-957b712cf456" />

##


ip addr | tee ~/week6/baseline/ip_addr.txt

<img width="816" height="230" alt="image" src="https://github.com/user-attachments/assets/d98d840b-bf15-49e1-b17c-4f716457aa09" />

##

top -b -n1 | head -n 30 | tee ~/week6/baseline/top.txt


<img width="685" height="525" alt="Screenshot 2025-12-13 140515" src="https://github.com/user-attachments/assets/33581948-4e09-49a2-813a-5f1178fa9e53" />

------------------------------------------------------------------------
