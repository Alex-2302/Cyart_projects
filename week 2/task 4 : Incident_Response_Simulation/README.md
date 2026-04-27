# Velociraptor DFIR Project

## Project Overview
This project demonstrates the setup and use of **Velociraptor** for Digital Forensics and Incident Response (DFIR).  
A **Kali Linux machine** was configured as the server, and a **Windows VM** was used as the client.

Goal: Collect system artifacts and analyze them for **Indicators of Compromise (IOCs)**.

---

## Tools Used
- Velociraptor (DFIR platform)  
- Kali Linux (Server)  
- Windows Virtual Machine (Client)  
- MITRE Caldera (Red team simulation)  

---

## Setup Instructions
1. Install and configure Velociraptor server on Kali Linux  
2. Generate client MSI using:
    Server.Utils.CreateMSI
3. Install Velociraptor agent on Windows VM  
4. Ensure both systems are on same network (Host-only)  
5. Start Velociraptor server and open GUI  
6. Verify client connection (green indicator in dashboard)  

---

## Data Collection

### Artifacts Collected
- `Windows.System.Pslist` → Process information  
- `Windows.Network.NetstatEnriched` → Network connections  

Results exported as **CSV files**

---

## Analysis Summary
- All processes were legitimate and digitally signed  
- Network connections were expected (internal traffic, browser activity)  
- No suspicious activity detected  
- No Indicators of Compromise (IOCs) found

---

## Conclusion
This project successfully demonstrates **DFIR capabilities using Velociraptor**.

System showed:
- No signs of compromise  
- Normal system behavior  
- Clean artifact results  
