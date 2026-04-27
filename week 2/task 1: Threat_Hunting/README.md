# Threat Hunting Lab using Elastic Security & Sysmon

## Overview
This project demonstrates threat hunting using open-source tools. Windows logs were collected, ingested into Elastic Security, and analyzed to detect suspicious activity.

---

## Objective
- Ingest logs into Elastic Security  
- Perform threat hunting  
- Detect PowerShell activity  
- Create a Sigma rule  

---

## Tools Used
- Elastic Security  
- Sysmon  
- Winlogbeat / Elastic Agent  
- Sigma Rules  

---

## Setup
- Installed Sysmon on a Windows VM  
- Configured log shipping to Elastic  
- Verified logs in Kibana Discover  

---

## Threat Hunting
- Executed PowerShell command in the VM  
- Queried logs using KQL  

---

## Sigma Rule
Created a rule to detect PowerShell execution using `-Command`.

```yaml
title: Suspicious PowerShell Activity
logsource:
  category: process_creation
  product: windows
detection:
  selection:
    Image|endswith: '\powershell.exe'
    CommandLine|contains: '-Command'
  condition: selection
```
---

## Challenges
Missing command_line field
Query timeouts
Field mapping issues

---

##Solutions
Used message field instead
Reduced time range
Optimized queries

---

## Importance

This project demonstrates:

Real-world threat hunting
Detection techniques
Log analysis skills

---

## Sample Queries 

process.name : "powershell.exe"
message : "*Write-Host*"
process.name : "powershell.exe" AND message : "*Write-Host*"

---

## Results Table

| Timestamp           | Process         | Command Line        | Notes                  |
|--------------------|-----------------|--------------------|------------------------|
| 2026-04-24 18:21:35 | powershell.exe  | Write-Host Test    | Suspicious execution   |
| 2026-04-24 18:13:53 | whoami.exe      | whoami             | User enumeration       |
| 2026-04-24 18:10:12 | powershell.exe  | Write-Host Test    | Repeated execution     |

---

## Conclusion

Successfully ingested logs, detected suspicious activity, and implemented Sigma-based detection.
