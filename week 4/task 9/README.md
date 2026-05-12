# Capstone Project: Full Adversary Simulation

## Overview

This capstone project demonstrates a full adversary simulation conducted within a controlled lab environment. The engagement simulated multiple stages of a modern cyberattack, including cloud reconnaissance, payload delivery, command-and-control behavior, credential access attempts, defense evasion, and blue team monitoring.

The assessment was performed for educational and defensive security purposes only.

---

# Objectives

- Perform AWS cloud reconnaissance and IAM enumeration
- Simulate initial access using PowerShell payload delivery
- Demonstrate defense evasion techniques
- Generate telemetry detectable by blue team monitoring
- Simulate credential access behavior
- Document findings using PTES methodology
- Map activities to MITRE ATT&CK techniques

---

# Tools Used

| Tool | Purpose |
|---|---|
| Kali Linux | Attacker machine |
| Pacu | AWS exploitation and cloud enumeration |
| AWS CLI | Cloud service interaction |
| MITRE Caldera | Adversary emulation |
| Metasploit | Payload handling and C2 simulation |
| Mimikatz | Credential access simulation |
| Wazuh | Blue team monitoring and detection |
| PowerShell | Payload execution and defense evasion |

---

# Lab Environment

## Attacker Systems
- Kali Linux

## Victim Systems
- Windows 11 VM
- AWS Lab Environment

## Monitoring
- Wazuh SIEM/XDR

---

# Project Phases

## 1. Reconnaissance and Cloud Enumeration

Activities:
- IAM permission enumeration using Pacu
- AWS identity validation
- S3 enumeration attempts
- Cloud permission analysis

MITRE ATT&CK:
- T1580 — Cloud Infrastructure Discovery
- T1078 — Valid Accounts
- T1526 — Cloud Service Discovery

---

## 2. Initial Access and Payload Delivery

Activities:
- PowerShell payload hosting
- Payload execution using MITRE Caldera
- Remote script execution
- HTTP payload delivery

MITRE ATT&CK:
- T1059.001 — PowerShell
- T1105 — Ingress Tool Transfer
- T1204 — User Execution

---

## 3. Defense Evasion

Activities:
- PowerShell execution policy bypass
- Fileless payload execution
- Simulated AV evasion

MITRE ATT&CK:
- T1027 — Obfuscated Files or Information
- T1562 — Impair Defenses

---

## 4. Credential Access Simulation

Activities:
- Mimikatz execution
- Credential access attempts
- LSASS interaction simulation

MITRE ATT&CK:
- T1003 — OS Credential Dumping

---

## 5. Blue Team Analysis

Activities:
- Wazuh alert analysis
- PowerShell telemetry review
- Process creation monitoring
- Detection validation

---

# Key Findings

- Excessive AWS IAM permissions were identified
- PowerShell payload execution succeeded
- Execution policy bypass techniques were successful
- Wazuh detected multiple attack stages
- Credential access simulations generated telemetry

---

# Recommendations

- Implement least-privilege IAM policies
- Enable advanced PowerShell logging
- Improve endpoint monitoring
- Strengthen cloud activity monitoring
- Monitor suspicious process execution

---

# Ethical Notice

This project was conducted strictly within an isolated lab environment for educational and defensive security purposes only. No unauthorized systems or production environments were targeted.

---


