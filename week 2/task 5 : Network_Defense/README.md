# Suricata Network Defense Project

## Project Overview
This project demonstrates the setup and use of **Suricata** as an Intrusion Detection and Prevention System (IDS/IPS).  
The objective was to detect and block malicious traffic and map alerts to **MITRE ATT&CK techniques**.

---

## Tools Used
- Suricata (IDS/IPS)  
- Kali Linux (Defender Machine)  
- Secondary VM (Attacker/Test Machine)  
- MITRE ATT&CK Framework  

---

## Setup Instructions
1. Install Suricata on Kali Linux  
2. Configure `suricata.yaml` (set `HOME_NET` and rule-files)  
3. Create custom rule in `local.rules`  
4. Run Suricata in IPS mode using **NFQUEUE**  
5. Ensure both VMs are on the same network  

---

## Rule Used

```rules
drop ip 192.168.56.102 any -> any any (msg:"Block Malicious IP"; sid:1000001; rev:1;)
```
---

## Output
- Traffic from the specified malicious IP was successfully blocked
- Alerts were generated in Suricata logs

---

## MITRE ATT&CK Mapping

| Alert Activity      | Tactic               | Technique | Description                  |
|--------------------|----------------------|----------|------------------------------|
| Suspicious Traffic | Command and Control  | T1071    | Outbound communication       |
| Traffic Blocking   | Defense Evasion      | T1562    | Blocking detection attempts  |

---

## Conclusion

Suricata effectively detected and blocked malicious traffic, demonstrating practical network defense capabilities using open-source tools.

