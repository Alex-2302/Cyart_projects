# Living-Off-the-Land Lab

## Overview
This project demonstrates Living-Off-the-Land (LotL) attack techniques using legitimate Windows administrative tools. The lab focuses on fileless execution, credential harvesting simulation, and security monitoring using Wazuh.

---

# Objectives
- Perform fileless attack execution using PowerShell.
- Simulate credential harvesting activities.
- Use native Windows administrative tools such as WMI.
- Monitor and analyze attack activities using Wazuh.
- Understand how defenders detect Living-Off-the-Land techniques.

---

# Tools Used
- PowerShell
- WMI
- Mimikatz
- Wazuh
- Kali Linux

---

# Lab Environment

| Component | Description |
|---|---|
| Attacker Machine | Kali Linux |
| Target Machine | Windows Environment |
| Monitoring Platform | Wazuh SIEM |
| Attack Category | Living-Off-the-Land (LotL) |

---

# Project Workflow

## 1. PowerShell Fileless Execution
PowerShell commands were executed directly in memory to simulate a fileless attack scenario. This technique minimizes disk artifacts and is commonly used by attackers to evade traditional antivirus solutions.

---

## 2. Credential Interaction and Native Tool Abuse
Native Windows tools and credential-related operations were performed using PowerShell and Mimikatz to simulate adversarial behavior.

---

## 3. Wazuh Monitoring Initialization
Wazuh monitoring services were initialized to collect security telemetry and monitor endpoint activities generated during the attack simulation.

---

## 4. Wazuh Dashboard Validation
The Wazuh dashboard was used to verify agent connectivity and observe generated security alerts.

---

## 5. Security Event Analysis
Wazuh successfully detected suspicious PowerShell execution and related attack activities during the simulation.

---

## 6. Detailed Alert Inspection
Detailed alert logs were analyzed to review event correlation and detection visibility.

---

# Attack Activity Log

| Attack ID | Tool | Action | Notes |
|---|---|---|---|
| LID001 | PowerShell | Fileless execution | Bypassed traditional AV detection |
| LID002 | Mimikatz | Credential interaction | Simulated credential harvesting |
| LID003 | WMI | System interaction | Native administrative execution |
| LID004 | Wazuh | Alert monitoring | Detected suspicious activities |

---

# Credential Harvesting Summary
Credential harvesting activities were simulated using PowerShell, WMI, and Mimikatz. Native administrative tools were abused to minimize forensic artifacts while interacting with the target system. Wazuh successfully detected suspicious PowerShell execution and generated security alerts associated with credential-related activities.

---

# Conclusion
This lab demonstrated how attackers can abuse legitimate Windows tools for malicious operations without relying on traditional malware binaries. The project highlighted the importance of behavioral monitoring, endpoint visibility, and SIEM-based detection mechanisms for identifying Living-Off-the-Land attack techniques.
