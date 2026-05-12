# Advanced Evasion Lab

## Objective
The objective of this lab was to perform advanced evasion techniques used in offensive security operations. The tasks included generating obfuscated payloads using `msfvenom` and `Veil`, and bypassing network monitoring controls by routing command-and-control (C2) traffic through the Tor network using `proxychains`.

---

# Tools Used

- msfvenom
- Veil Framework
- Metasploit Framework
- proxychains
- Tor
- Kali Linux
- Windows Virtual Machine

---

# Lab Activities

## 1. Payload Obfuscation

### Goal
Generate and obfuscate a Meterpreter payload capable of bypassing basic antivirus detection.

### Steps Performed

1. Verified the lab environment and tool installation.
2. Generated a Meterpreter reverse TCP payload using `msfvenom`.
3. Configured payload parameters including:
   - LHOST
   - LPORT
   - Payload format
4. Applied encoding techniques to reduce static signature detection.
5. Exported the payload for further obfuscation.
6. Launched the Veil framework.
7. Selected the appropriate payload generation module.
8. Configured Veil payload settings.
9. Compiled the obfuscated payload executable.
10. Verified successful payload generation.
11. Configured a Metasploit multi/handler listener.
12. Started the listener for incoming sessions.

---

## 2. Network Evasion

### Goal
Route C2 traffic through Tor using `proxychains` to anonymize communication.

### Steps Performed

1. Configured `proxychains.conf`.
2. Started the Tor service.
3. Verified proxy functionality.
4. Confirmed external IP address masking.
5. Routed network traffic through Tor.
6. Tested anonymized connectivity.
7. Executed the obfuscated payload.
8. Verified successful Meterpreter session establishment.

---

# Payload Obfuscation Log

| Payload ID | Type | AV Detection | Notes |
|------------|------|--------------|-------|
| PID001 | Meterpreter | Bypassed | Obfuscated payload generated using msfvenom and Veil |

---

# Network Evasion Summary

Proxychains and Tor were configured to anonymize outbound command-and-control traffic. The setup successfully routed communications through multiple proxy layers, masking the attacker IP address. Testing confirmed stable connectivity and successful Meterpreter session establishment while bypassing direct network visibility controls and reducing exposure during network monitoring operations.

---

# Observations

- Payload obfuscation reduced direct antivirus signature detection.
- Veil provided effective payload wrapping capabilities.
- Tor successfully anonymized outbound network traffic.
- proxychains correctly redirected communication through proxy routes.
- Meterpreter sessions remained stable during testing.

---

# Conclusion

The Advanced Evasion Lab successfully demonstrated practical offensive security techniques involving payload obfuscation and network evasion. Obfuscated payloads were generated using `msfvenom` and `Veil`, while `proxychains` and `Tor` effectively anonymized command-and-control communications. The lab validated the effectiveness of evasion techniques commonly used during red team operations.

---
