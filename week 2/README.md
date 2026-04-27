# Week 2 – Advanced Threat Analysis & Practical Security Operations

## Overview
This repository contains my **Week 2 cybersecurity learning and practical implementation**, covering:

- Advanced Threat Analysis  
- Security Frameworks (NIST CSF, ISO 27001)  
- Incident Response  
- Risk Management  
- Hands-on labs (Threat Hunting, Malware Analysis, SIEM, Network Defense, etc.)  

The goal is to bridge **theoretical knowledge with real-world security operations**.

---
# Theoretical Knowledge

## 1. Advanced Threat Analysis

### Threat Modeling (STRIDE)
Used STRIDE methodology:
- Spoofing  
- Tampering  
- Repudiation  
- Information Disclosure  
- Denial of Service  
- Elevation of Privilege  

Applied to a **web application authentication system** to identify risks like credential spoofing.

---

### MITRE ATT&CK Framework
- Studied tactics & techniques like:
  - Initial Access  
  - Execution  

Examples:
- Phishing → **T1566**  
- PowerShell → **T1059**

---

### Advanced Attack Vectors
- APTs (Advanced Persistent Threats)  
- Supply Chain Attacks  
- Zero-Day Exploits  

Case Study: SolarWinds Attack (2020)

---

## 2. Security Frameworks

### NIST Cybersecurity Framework (CSF)
Functions:
- Identify  
- Protect  
- Detect  
- Respond  
- Recover  

Used to map ransomware response lifecycle.

---

### ISO/IEC 27001
- Studied controls like:
  - Logging & Monitoring  
  - Backup Management  

Applied backup control to mitigate ransomware.

---

## 3. Incident Response Fundamentals
Lifecycle:
- Preparation  
- Detection  
- Containment  
- Eradication  
- Recovery  

Studied SANS methodology and SOC workflows.

---

## 4. Risk Management
- Quantitative vs Qualitative Risk  
- Business Impact Analysis (BIA)  

Calculated:
- **ALE (Annualized Loss Expectancy)**

---

# Practical Implementation

## 1. Threat Hunting

### Tools
- Elastic Security  
- Security Onion  
- Sigma Rules  

### Tasks
- Created Sigma rule for PowerShell detection  
- Queried Event ID 4688  

Output documented in report

---

## 2. Malware Analysis

### Tools
- REMnux  
- Hybrid Analysis  

### Tasks
- Static analysis using `strings`  
- Dynamic analysis comparison  

---

## 3. Vulnerability Management

### Tools
- OpenVAS  
- DefectDojo  

### Tasks
- Scanned Metasploitable2  
- Prioritized vulnerabilities  
- Proposed remediation  

---

## 4. Incident Response Simulation

### Tools
- Velociraptor  
- MITRE Caldera  

### Tasks
- Simulated phishing attack  
- Collected artifacts  
- Identified IOCs  

---

## 5. Network Defense

### Tools
- Suricata  
- Elastic SIEM  
- CrowdSec  

### Tasks
- Created detection rules  
- Mapped alerts to MITRE ATT&CK  

---

## 6. Risk Assessment

### Task
Calculated:
ALE = SLE × ARO
ALE = 10,000 × 0.2 = 2,000


✔ Built a **5x5 Risk Matrix**

---

## 7. Incident Response Report
- Created report using SANS format:
  - Executive Summary  
  - Timeline  
  - Mitigation Steps  

Added workflow diagram

---

## 8. Capstone Project

### Tools
- Metasploit  
- Wazuh  
- CrowdSec  

### Workflow
1. Attack Simulation (VSFTPD exploit)  
2. Detection via Wazuh  
3. Containment using CrowdSec  
4. Reporting  

Full incident lifecycle executed

---

# Key Learnings

- Applied **threat modeling in real scenarios**  
- Mapped attacks to **MITRE ATT&CK**  
- Built **SIEM detection & threat hunting queries**  
- Performed **malware and vulnerability analysis**  
- Understood **end-to-end incident response lifecycle**  

---
