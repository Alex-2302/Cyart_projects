# OSINT and Reconnaissance Lab

## Overview
This project demonstrates the use of Open Source Intelligence (OSINT) tools to gather information about a target domain. The lab focuses on subdomain enumeration, infrastructure mapping, and exposed service discovery using passive reconnaissance techniques.

---

## Objectives
- Enumerate subdomains of a target domain
- Identify associated IP addresses
- Visualize relationships between entities
- Discover exposed services using search engines

---

## Tools Used

- **Recon-ng** – Automated reconnaissance framework  
- **Maltego** – Link analysis and visualization tool  
- **Shodan** – Search engine for internet-connected devices  
- **Kali Linux** – Penetration testing environment  

---

## Methodology

---

## 1. Subdomain Enumeration (Recon-ng)

### Module used:

```
recon/domains-hosts/hackertarget
```

---

### Commands:

```bash
modules load recon/domains-hosts/hackertarget
options set SOURCE tesla.com
run
show hosts
```

---

### Output:

Subdomains
IP addresses

---

## 2. Service Discovery (Shodan)

### Query used:

```
apache country:US
```

---

### Purpose:

Identify publicly exposed Apache servers
Analyze open ports and services

---

### Ethical Considerations

Only perform passive reconnaissance
Do not scan or exploit targets
Use publicly available data only
Respect legal and ethical boundaries

---

## Conclusion

This lab demonstrates how OSINT tools can be used to gather valuable information about a target without direct interaction. Combining Recon-ng, Maltego, and Shodan provides a comprehensive view of a target’s digital footprint and potential exposure

---
