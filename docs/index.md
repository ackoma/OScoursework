# Linux Server Administration, Security & Performance Analysis

## Module Overview
This repository documents a seven-week practical project focused on Linux server administration using a dual-system architecture.  
The project emphasises **command-line proficiency**, **security hardening**, **performance testing**, and **system analysis** rather than cloud or enterprise infrastructure design.

### System Architecture
- **Server:** Ubuntu Server (headless, administered via SSH)
- **Workstation:** Ubuntu Desktop / Host OS (remote administration & monitoring)
- **Virtualisation:** Oracle VirtualBox
- **Access Method:** Secure Shell (SSH)

---



### ▶️ [Week 1 – System Planning & Architecture](https://github.com/ackoma/OScoursework/blob/main/docs/Week1.md)
- System architecture diagram
- Distribution selection justification
- Workstation selection rationale
- VirtualBox network configuration
- CLI system specification evidence

---

### [Week 2 – Baseline Security & System Hardening](./Week-02-Baseline-Security)
- SSH configuration fundamentals
- Firewall concepts and planning
- User privilege analysis
- Initial threat awareness

---

### [Week 3 – Application Selection & Performance Planning](./Week-03-Performance-Planning)
- Application selection matrix
- Workload classification (CPU, RAM, I/O, Network)
- Performance testing methodology
- Baseline measurement planning

---
### [Week 4 – Initial Security Implementation](./Week-04-Security-Implementation)
- SSH key-based authentication
- Firewall configuration (restricted SSH access)
- User and privilege management
- Configuration file comparisons (before/after)
- Remote administration evidence

---

### [Week 5 – Advanced Security & Monitoring Infrastructure](./Week-05-Advanced-Security-Monitoring)
- AppArmor mandatory access control
- Automatic security updates
- Intrusion detection using fail2ban
- Security baseline verification script
- Remote monitoring script

---

### [Week 6 – Performance Evaluation & Optimisation](./Week-06-Performance-Evaluation)
- Baseline vs load testing
- CPU, memory, disk, network analysis
- Latency and service response measurement
- Bottleneck identification
- Optimisation testing with quantitative improvements
- Performance charts and data tables

---

### [Week 7 – Final Analysis & Reflection](./Week-07-Final-Analysis)
- Comparative performance analysis
- Security posture evaluation
- Lessons learned and critical reflection
- Final architecture evolution
- Project conclusion

---

## Tools & Technologies Used
- **Operating System:** Ubuntu Server & Ubuntu Desktop
- **Security:** OpenSSH, UFW, AppArmor, fail2ban
- **Performance Tools:** stress-ng, fio, iperf3, ApacheBench
- **Monitoring:** top, vmstat, iostat, custom scripts
- **Scripting:** Bash
- **Visualisation:** Python (matplotlib)

---

## Key Learning Outcomes
- Secure Linux server administration via CLI
- Defence-in-depth security implementation
- Performance testing and bottleneck analysis
- Automation of security verification and monitoring
- Professional documentation and evidence collection

---
## Author
**Name:** _Your Name Here_  
**Module:** _Module Code / Name_  
**Institution:** _University / College Name_  


