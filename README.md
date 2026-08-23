# Week 3 – Advanced Cybersecurity Practical Assessment

## Overview

This project documents my Week 3 cybersecurity practical assessment covering:

- Network Discovery
- Traffic Analysis
- Vulnerability Assessment
- Security Hardening
- Nmap Scanning
- Wireshark Packet Analysis

All activities were performed in an authorized and isolated virtual lab environment.

## Lab Environment

| Component | Details |
|---|---|
| Hypervisor | VMware 17 |
| Analyst Machine | Kali Linux |
| Kali IP | 192.168.94.133 |
| Target VM 1 | Metasploitable |
| Metasploitable IP | 192.168.94.134 |
| Target VM 2 | Ubuntu Server |
| Ubuntu IP | 192.168.94.135 |
| Network | Host-only / Internal |
| Subnet | 192.168.94.0/24 |

## Tools Used

- **Nmap** – Host discovery, port scanning, service/version detection and security assessment
- **Wireshark** – Packet capture and network traffic analysis
- **VMware** – Virtual lab environment
- **draw.io / diagrams.net** – Network topology diagram
- **GitHub** – Project documentation and version control

## Nmap Scanning

Example commands used in the authorized lab:

```bash
nmap -sn 192.168.94.134
nmap 192.168.94.134
nmap -sV 192.168.94.134
nmap -O 192.168.94.134
nmap -sS 192.168.94.134
nmap -sU --top-ports 20 192.168.94.134
```

## Key Findings

The assessment identified the following exposed legacy services:

| Port | Service | Risk |
|---|---|---|
| 21/TCP | FTP | High |
| 23/TCP | Telnet | Critical |
| 512/TCP | EXEC | Critical |
| 513/TCP | rlogin | Critical |
| 514/TCP | RSH | Critical |

## Wireshark Analysis

Wireshark was used to capture and analyze:

- DNS
- TCP
- UDP
- ICMP
- ARP

Useful display filters included:

```text
tcp.flags.syn == 1
tcp.flags.reset == 1
dns.flags.response == 0
```

Nmap and Wireshark were also used together to observe how SYN scans appear at the packet level.

## Security Hardening

The following improvements were performed:

1. Disabled FTP on port 21.
2. Disabled Telnet on port 23.
3. Disabled legacy EXEC service on port 512.
4. Disabled rlogin service on port 513.
5. Disabled RSH-related service on port 514.

The changes were verified using Nmap after hardening.

## Before and After

| Service | Before | After |
|---|---|---|
| FTP – 21 | Open | Closed |
| Telnet – 23 | Open | Closed |
| EXEC – 512 | Open | Disabled |
| rlogin – 513 | Open | Disabled |
| RSH – 514 | Open | Disabled |

## Screenshots

Add your screenshots to the `screenshots` folder and update the filenames below.

### Network Diagram
![Network Diagram](screenshots/network-diagram.png)

### Nmap Before Hardening
![Nmap Before Hardening](screenshots/nmap-before.png)

### Wireshark Packet Capture
![Wireshark Analysis](screenshots/wireshark.png)

### Nmap After Hardening
![Nmap After Hardening](screenshots/nmap-after.png)

## Learning Outcomes

Through this practical, I learned:

- How to discover hosts using Nmap.
- How to identify open ports and services.
- How to perform service and version detection.
- How to capture and analyze packets using Wireshark.
- How network scanning appears in packet captures.
- How to identify insecure legacy services.
- How to perform basic vulnerability assessment.
- How to harden an authorized lab system.
- How to verify security improvements after hardening.

## Ethical & Legal Notice

All scanning, packet capture, vulnerability assessment and hardening activities were performed only against authorized systems in an isolated cybersecurity lab.

Do not scan or test systems without proper authorization.

## Author

**Khushveer Dhiman**  
Cybersecurity Intern  
**Program / Organization:** DG INTERN  
**Week:** 3 – Advanced Cybersecurity Practical Assessment  
**Submission Date:** 24 August 2026
