## Penetration Testing Project
Hands on Penetration testing walkthrough of vulnerable machine

## Overview
This project documents the exploitation of a vulnerable Linux machine as part of hands-on penetration testing practice.
The objective was to gain initial access and escalate privileges to root by identifying and exploiting misconfigurations and vulnerabilities.

## Target Information
- Target OS: Linux
- Difficulty: Beginner – Intermediate
- Attack Type: Web & Linux Privilege Escalation
- Environment: Local Lab

## Tools Used
- Nmap
- Gobuster 
- WPScan
- Linux Enumeration techniques 

## Phase 1: Reconnaissance & Enumeration

### Network Scanning
Performed a full TCP port scan to identify open services.

Command used:
nmap -sCV -p- 192.168.184.194 --min-rate 10000

Findings:
- HTTP service discovered
- Web application hosted on Apache

## Phase 2: Web Enumeration
Directory enumeration was performed to discover hidden paths and files.

Command used:
gobuster dir -u http://dc-2/ -w /usr/share/wordlists/dirb/common.txt
wpscan --url http://dc-2/ -e 

Key observations:
- Discovered restricted directories
- Identified login functionality
- WordPress user enumeration
- Found clues leading to valid credentials

## Phase 3: Initial Access
Using credentials identified during enumeration, access to the system was obtained.

Result:
- Shell access gained as a low-privileged user
- Access verified using the 'whoami' command

## Phase 4: Privilege Escalation
Local system enumeration was performed to identify privilege escalation vectors.

Techniques used:
- Sudo permission enumeration
- Misconfigured file and binary permissions
- User privilege analysis

Result:
- Successfully escalated privileges to root

## Final Result
- Root access achieved
- Complete attack lifecycle executed:
  - Reconnaissance
  - Enumeration
  - Exploitation
  - Privilege Escalation

## Lessons Learned
- Importance of proper enumeration
- Common Linux privilege escalation methods
- How misconfigurations lead to system compromise

## Disclaimer
This write-up is for educational purposes only.  
All testing was performed in a controlled lab environment.
How small misconfigurations lead to full compromise

⚠️ Disclaimer

This write-up is for educational purposes only.
The techniques demonstrated were performed in a controlled lab environment.
