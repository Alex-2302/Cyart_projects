# Adversary Emulation Lab

## Overview
This lab demonstrates adversary emulation using MITRE Caldera to simulate APT29-style attack techniques. The exercise focuses on phishing simulation, command and control activity, persistence mechanisms, and Blue Team detection using Wazuh SIEM.

The objective of the lab is to understand attacker tactics, techniques, and procedures (TTPs) while validating detection and monitoring capabilities from a defensive perspective.

---

# Objectives

- Simulate adversary behavior using MITRE Caldera
- Emulate APT29 attack techniques
- Test Blue Team visibility and monitoring
- Analyze attack telemetry in Wazuh
- Map activities to the MITRE ATT&CK framework

---

# Tools Used

| Tool | Purpose |
|------|----------|
| MITRE Caldera | Adversary emulation and attack orchestration |
| Evilginx2 | Credential phishing simulation |
| Wazuh | SIEM monitoring and log analysis |
| Kali Linux | Attacker operating system |
| MITRE ATT&CK | TTP mapping framework |

---

# Lab Environment

| Component | Description |
|-----------|-------------|
| Attacker Machine | Kali Linux |
| C2 Framework | MITRE Caldera |
| Monitoring Platform | Wazuh |
| Target System | Windows endpoint with Wazuh agent |

---

# MITRE ATT&CK Mapping

| Phase | TTP | Tool Used | Notes |
|------|------|------------|-------|
| Phishing | T1566.001 | Evilginx2 | Credential harvesting |
| Initial Access | T1078 | Caldera | Valid account simulation |
| Command and Control | T1071 | Caldera | C2 communication |
| Persistence | T1053 | Caldera | Scheduled task persistence |
| Execution | T1059 | Caldera | Command execution |
| Detection & Monitoring | T1119 | Wazuh | Security event monitoring |

---

# Procedure

## 1. Caldera Initialization
- Started the MITRE Caldera server
- Verified framework accessibility
- Configured operational settings

---

## 2. Agent Deployment
- Configured Caldera agent deployment
- Established communication with the C2 server
- Verified successful callback

---

## 3. Ability Configuration
- Reviewed and configured adversary abilities
- Selected ATT&CK-mapped techniques

---

## 4. Operation Creation
- Created a new adversary operation
- Configured attack execution parameters

---

## 5. Adversary Profile Selection
- Selected adversary emulation profile
- Prepared operation execution


---

## 6. Operation Monitoring
- Monitored active operation progress
- Verified agent communication

---

## 7. Caldera Terminal Execution
- Observed successful framework execution
- Validated operation status

---

## 8. Dashboard Overview
- Reviewed Caldera operational dashboard
- Observed attack statistics

---

## 9. Active Agent Verification
- Confirmed connected agents
- Verified operational readiness

---

## 10. Operation Scheduling
- Configured attack timing
- Adjusted execution settings

---

## 11. Adversary Operation Execution
- Launched attack simulation
- Executed ATT&CK techniques
---

## 12. Operation Results
- Reviewed successful execution results
- Validated technique execution

---

## 13. Attack Log Analysis
- Analyzed detailed execution logs
- Reviewed ATT&CK technique traces

---

## 14. Wazuh Dashboard Monitoring
- Monitored security telemetry
- Observed endpoint event collection

---

## 15. Wazuh Event Analysis
- Investigated attack-generated events
- Analyzed security alerts

---

## 16. Detection Correlation
- Correlated attack activities with alerts
- Verified Blue Team visibility

---

## 17. Security Event Visualization
- Reviewed attack telemetry dashboards
- Observed categorized alerts

---

## 18. Blue Team Investigation
- Investigated attack indicators
- Validated detection coverage

### Screenshot
`task3.18.png`

---

# Blue Team Detection Summary

Wazuh successfully detected multiple adversary activities generated through Caldera operations, including command execution, persistence attempts, and suspicious process behavior. Security dashboards and event logs provided visibility into attack stages, enabling Blue Team correlation, monitoring, and investigation of simulated APT29 tactics mapped to MITRE ATT&CK techniques.

---

# Findings

- MITRE Caldera effectively simulated adversary behavior
- ATT&CK-mapped techniques generated realistic telemetry
- Wazuh provided centralized visibility into attack activity
- Persistence and execution actions were detectable
- Blue Team monitoring validated detection capabilities

---

# Conclusion

The adversary emulation lab successfully demonstrated how offensive security tools such as MITRE Caldera and Evilginx2 can simulate realistic attack scenarios for defensive validation. Wazuh enabled effective monitoring and analysis of attack telemetry, improving understanding of attacker behavior and Blue Team detection strategies.

---

# References

- MITRE ATT&CK Framework
- MITRE Caldera Documentation
- Wazuh Documentation
- Evilginx2 Documentation
