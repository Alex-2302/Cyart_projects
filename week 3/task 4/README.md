# Lateral Movement & Persistence Lab

## Overview

This project demonstrates lateral movement and persistence techniques in a controlled lab environment. Using valid credentials, remote access to a Windows system was achieved, followed by establishing persistence through scheduled tasks.

---

## Objective

* Perform lateral movement using valid credentials
* Gain remote command execution on a target system
* Verify privilege escalation
* Establish persistence for continued access

---

## Tools Used

* **Kali Linux (Attacker Machine)**
* **Windows Virtual Machine (Target)**
* **Impacket (psexec.py)**

---

## Lab Environment

* Network: Host-only setup
* Attacker IP: Kali Linux
* Target IP: Windows VM

---

## 1. Lateral Movement Using PsExec

Valid administrative credentials were used to authenticate to the target system over SMB.

### Command:

```bash id="wztqrg"
impacket-psexec pentest:Password123@192.168.56.102
```

### Result:

* Remote service created
* Command execution achieved
* SYSTEM-level shell obtained

---

## 2. Verification of Access

Command used:

```bash id="1v2b9v"
whoami
```

### Output:

```text id="i4qg4k"
NT AUTHORITY\SYSTEM
```

* Confirms highest privilege level

---

## 3. Persistence Mechanism

A scheduled task was created to maintain access.

### Command:

```bash id="n4o7vw"
schtasks /create /sc minute /mo 1 /tn "Updater" /tr "cmd.exe /c calc.exe" /ru SYSTEM
```

### Purpose:

* Executes every minute
* Runs with SYSTEM privileges
* Ensures continued access

---

## Impact

* Persistent SYSTEM-level execution
* Ability to run commands repeatedly
* Maintains access after session termination

---

## Log Table

| Technique      | Tactic           | Description                      | Notes                      |
| -------------- | ---------------- | -------------------------------- | -------------------------- |
| PsExec         | Lateral Movement | Remote command execution via SMB | Requires admin credentials |
| Scheduled Task | Persistence      | Recurring execution of command   | Runs as SYSTEM             |

---

## Pivot Summary 

Valid credentials were used to authenticate to a Windows system via SMB. Using Impacket’s psexec, a remote service was created to execute commands, resulting in SYSTEM-level access. This demonstrated lateral movement through credential reuse and remote command execution across the network.

---

## Conclusion

This lab demonstrates how attackers can leverage valid credentials to move laterally within a network and maintain persistent access. It highlights the importance of credential security and monitoring administrative activity.

---


