# Post-Exploitation and Data Exfiltration Lab

## Overview
This lab demonstrates a full post-exploitation attack chain in a controlled environment, including credential dumping, password cracking, lateral movement, and data exfiltration.

## Tools Used
- Mimikatz – Credential extraction  
- Hashcat – Password cracking  
- Impacket – Remote execution and lateral movement  

## Steps Performed
1. Gained remote access using valid credentials  
2. Extracted NTLM hashes from the target system  
3. Cracked hashes using a dictionary attack  
4. Reused credentials for lateral movement  
5. Simulated data exfiltration using DNS queries  

## Key Findings
- Weak passwords can be easily cracked  
- NTLM hashes can be reused for authentication  
- Administrative tools can be abused for lateral movement  
- DNS traffic can be used for covert data exfiltration  

## Conclusion
The lab successfully demonstrates how attackers can move from initial access to data exfiltration. It highlights the importance of strong passwords, monitoring, and network security controls.

---


