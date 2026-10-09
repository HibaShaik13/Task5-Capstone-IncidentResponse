# Task5-Capstone-IncidentResponse
# Task 5 — Capstone Project & Incident Response

**Intern:** Shaik Hiba Tharunnum | **Offer Letter ID:** APSPL2645050  
**Domain:** Cybersecurity & Ethical Hacking | **Organization:** ApexPlanet Software Pvt. Ltd.

## Capstone Focus
Web Application Penetration Test — DVWA (Damn Vulnerable Web Application) on
Metasploitable2, consolidating findings from Tasks 2–4 into one formal engagement,
plus a simulated incident-response exercise.

## Objective
Produce a professional, consolidated penetration-testing report covering the full
engagement lifecycle (Recon → Scanning → Exploitation → Post-Exploitation →
Reporting), and demonstrate basic incident detection and response.

## What Was Done
- **Project Plan:** Defined objectives, scope, tools, and timeline; built a lab
  architecture diagram.
- **Recon/Scanning:** Re-verified target reachability and service state with a fresh
  Nmap scan and DVWA availability check.
- **Consolidated Findings:** Pulled together 7 confirmed vulnerabilities across
  Tasks 2–4 — SQL Injection, Stored/Reflected XSS, CSRF, Local File Inclusion,
  the vsFTPd remote root exploit, weak SSH credentials, and missing security headers
  — into one prioritized findings table.
- **Incident Response Simulation:** Simulated a SYN flood attack with hping3,
  detected it live in Wireshark (93,000+ packets captured), and documented
  detection, containment (iptables), eradication, and a post-incident summary.
- **Mitigations:** Documented remediation recommendations for every finding.

## Tools Used
Nmap, Metasploit Framework, Meterpreter, Hydra, John the Ripper, Burp Suite,
Wireshark, hping3, iptables, DVWA, curl

## Files in This Folder
| File | Description |
|---|---|
| `README.md` | This file |
| `Task5_Capstone_IncidentResponse_Report.docx` | Full capstone report with diagram & screenshots |
| `findings-summary.md` | Consolidated vulnerability findings (raw notes) |
| `incident-response-log.md` | SYN flood detection/containment raw notes |
| `lab_diagram.png` | Lab network architecture diagram |

## Key Concepts Covered
- End-to-end penetration testing lifecycle across a multi-task engagement
- Consolidating findings into one professional report
- Web application vulnerabilities: SQLi, XSS, CSRF, LFI
- Remote exploitation and post-exploitation
- Credential attacks and offline hash cracking
- Incident detection via packet capture analysis
- Containment and post-incident reporting
- Risk prioritization and mitigation planning

## Lab Environment
- Attacker: Kali Linux — 192.168.56.101
- Target: Metasploitable2 — 192.168.56.102
- Network: VirtualBox host-only adapter (isolated lab network)

## Internship Summary
This capstone marks the completion of all 5 tasks of the ApexPlanet Cybersecurity &
Ethical Hacking internship: Foundation Setup, Network Scanning, Web Application
Security, Exploitation & System Security, and this Capstone & Incident Response
project.
