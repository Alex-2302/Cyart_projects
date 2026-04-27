# Incident Response Report – Phishing Attack Simulation

---

## Project Overview
This project documents a **simulated phishing incident** using a structured **incident response approach (SANS model)**.  
The objective was to detect, analyze, contain, and recover from a phishing attack while documenting the entire process.

---

## Objectives
- Simulate a phishing attack scenario  
- Analyze attacker behavior  
- Document incident response lifecycle  
- Provide mitigation and recommendations  

---

## Tools Used
- Email Client (Phishing Simulation)  
- Windows VM  
- Log Analysis Tools / SIEM  
- Basic DFIR Methodology  

---

## Executive Summary
A phishing email was delivered to a user, tricking them into executing a malicious link.  
The activity was detected through unusual process behavior and suspicious network connections.

Key Outcomes:
- Attack was identified early  
- System was contained before lateral movement  
- No major data loss occurred  

---

## Incident Timeline

| Time                | Event Description                          |
|---------------------|-------------------------------------------|
| 10:00 AM            | Phishing email received                   |
| 10:05 AM            | User clicked malicious link               |
| 10:06 AM            | Suspicious process initiated              |
| 10:08 AM            | Detection alert triggered                 |
| 10:10 AM            | System isolated (containment)             |
| 10:20 AM            | Malicious process terminated              |
| 10:30 AM            | System restored and monitored             |

---

## Incident Analysis
- Initial Access: Phishing email  
- Execution: Malicious script executed  
- Indicators Observed:
  - Suspicious PowerShell activity  
  - Unknown outbound connections  
  - Unusual process behavior  

---

## Containment Actions
- Isolated affected machine from network  
- Blocked malicious IP/domain  
- Disabled compromised user account  

---

## Eradication
- Removed malicious files/scripts  
- Cleared temporary files  
- Verified no persistence mechanisms  

---

## Recovery
- Restored system to normal state  
- Re-enabled user access with new credentials  
- Monitored system for recurring activity  

---

## Mitigation & Recommendations
- Enable email filtering and anti-phishing tools  
- Conduct user awareness training  
- Implement multi-factor authentication (MFA)  
- Enable endpoint detection and logging  
- Regular patching and updates  

---

## Key Learnings
- Early detection is critical in phishing attacks  
- User awareness plays a major role  
- Logging and monitoring improve response speed  
- Structured response reduces impact  

---

## Conclusion
The simulated phishing attack was successfully detected and mitigated.  
This project demonstrates a complete **incident response lifecycle**, highlighting the importance of preparation, detection, and rapid containment.
