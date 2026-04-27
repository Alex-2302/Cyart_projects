# Capstone Incident Response Project

---

## Project Overview
This project demonstrates a complete **incident response lifecycle**, including:
- Attack simulation  
- Detection  
- Containment  
- Reporting  

The attack was performed using **Metasploit** against a vulnerable **Metasploitable2** system, detected using **Wazuh (conceptually)**, and contained using firewall rules.

---

## Tools Used
- Metasploit (Attack Simulation)  
- Wazuh (Detection & Monitoring)  
- iptables (Containment)  
- Kali Linux & Metasploitable2 (Lab Environment)  

---

## Steps Performed
1. Configured lab environment (Kali + Metasploitable2)  
2. Executed VSFTPD backdoor exploit using Metasploit  
3. Verified access using Meterpreter session  
4. Monitored activity using Wazuh dashboard  
5. Created detection table with MITRE ATT&CK mapping  
6. Simulated containment using iptables firewall rules  
7. Documented findings and response actions  

---

## Attack Details

| Parameter     | Value                          |
|--------------|--------------------------------|
| Exploit Used | exploit/unix/ftp/vsftpd_234_backdoor |
| Target IP    | 192.168.56.104                 |
| Attacker IP  | 192.168.56.103                 |

---

## Detection Summary

| Timestamp           | Source IP        | Alert Description     | MITRE Technique |
|--------------------|------------------|----------------------|-----------------|
| 2026-04-25 11:00:00 | 192.168.56.103   | VSFTPD exploit       | T1190           |

---

## Containment
Due to tool compatibility issues, containment was implemented using **iptables firewall rules**:
sudo iptables -A INPUT -s 192.168.56.103 -j DROP

✔ Blocked attacker IP successfully  

---

## Output
- Attack successfully achieved unauthorized access  
- Detection analyzed using monitoring concepts  
- Containment restricted further attacker interaction  

---

## MITRE ATT&CK Mapping

| Technique ID | Technique Name                     | Description                          |
|--------------|-----------------------------------|--------------------------------------|
| T1190        | Exploit Public-Facing Application | Exploiting vulnerable FTP service    |

---

## Importance
This project demonstrates:
- Real-world attack simulation  
- Detection and monitoring concepts  
- Incident containment strategies  
- End-to-end incident response workflow  

---

## Conclusion
This capstone project highlights:
- Importance of vulnerability management  
- Need for continuous monitoring  
- Effectiveness of rapid incident response  

Demonstrates how multiple security tools work together in a **complete incident response lifecycle**
