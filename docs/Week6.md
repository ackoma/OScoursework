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

------------------------------------------------------------------------------------------------------------

Disk baeline

<img width="1291" height="610" alt="image" src="https://github.com/user-attachments/assets/fec49e6f-1c93-4246-90f7-b5de6b675ddd" />

------------------------------------------------------------------------------------------------------------

**Load testing per application + capture metrics**

##

For each test, you will capture:


CPU usage (top -b -n1 | head -n 20)


<img width="638" height="169" alt="Screenshot 2025-12-13 142304" src="https://github.com/user-attachments/assets/3dff28f1-19df-4124-9253-4b301c106b01" />

##

Memory usage (free -h)


<img width="658" height="99" alt="image" src="https://github.com/user-attachments/assets/e6c40928-dffc-4a77-8c47-81ddc1405c25" />

##

System latency(vmstat 1 5)


<img width="764" height="163" alt="image" src="https://github.com/user-attachments/assets/ded04b8c-b009-4b88-a390-76c3f30275a1" />


##


Disk I/O (iostat -xz 1 3)


<img width="1295" height="478" alt="image" src="https://github.com/user-attachments/assets/1eba9072-bf14-4511-84a1-cfd536725bd6" />

##
CPU:

For the CPU workload test, the server is stressed using stress‑ng to generate sustained processor activity and capture how the system behaves under load. The test begins by recording the current timestamp for documentation, followed by running a 60‑second CPU stress operation using two CPU workers, with all results saved into the Week 6 load directory.


<img width="651" height="339" alt="image" src="https://github.com/user-attachments/assets/6ca9c8f6-ebd5-4e6d-a499-5776fc32054d" />

##

RAM:

For the RAM workload test, the system’s memory performance is evaluated using stress‑ng to simulate heavy memory consumption. The process begins by recording a timestamp for documentation, followed by running a 60‑second memory‑intensive workload that allocates 80% of available RAM through a single virtual memory worker.

<img width="723" height="190" alt="image" src="https://github.com/user-attachments/assets/59fca839-1829-4bb8-8245-0213b2e2ff5d" />

##

Disk I/O:

For the Disk I/O workload, fio is used to evaluate both sequential throughput and random read/write performance under controlled conditions. The test begins by recording a timestamp, followed by running a 60‑second sequential write workload that writes a 1GB file using a 1MB block size, with all results saved for later analysis. A second test measures random I/O behaviour by performing mixed read/write operations on a 1GB file using 4KB blocks, four parallel jobs, and a 70% read bias—capturing realistic latency and IOPS characteristics.


<img width="830" height="622" alt="image" src="https://github.com/user-attachments/assets/dd3daf93-68b8-4684-b6fa-b7bda940e6c6" />


##
Network performance:

For the network performance tests, both throughput and latency are measured to assess how efficiently the server and workstation communicate under controlled conditions. Throughput testing is carried out using iperf3, with the server placed in listening mode while the workstation runs a 30‑second client test, saving the results for later analysis. After stopping the server process, its output can also be captured to provide a complete record of both ends of the connection.

-----------------------------------------------------------------------------
Create charts and graphs:

To visualise the performance data collected throughout Week 6, a Python script is created on the workstation to automatically generate charts from the completed CSV file. The script loads the dataset, cleans the values, and produces two key visualisations: one comparing throughput and request‑per‑second metrics across scenarios, and another illustrating latency‑related measurements such as RTT and time‑per‑request.





##

