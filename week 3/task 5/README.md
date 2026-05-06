# Social Engineering Lab

## Overview

This project demonstrates social engineering techniques using OSINT tools and phishing simulation in a controlled lab environment. The exercise includes intelligence gathering, relationship mapping, and credential harvesting to understand how attackers exploit human behavior.

---

## Objective

* Perform OSINT-based intelligence gathering
* Map relationships using visualization tools
* Simulate phishing attacks
* Demonstrate a vishing (voice phishing) scenario

---

## Tools Used

* **PhoneInfoga** – Phone number intelligence gathering
* **Maltego** – OSINT relationship mapping
* **Social-Engineer Toolkit (SET)** – Phishing simulation
* **Python HTTP Server** – Local hosting (fallback testing)

---

## 1. Intel Gathering (PhoneInfoga)

Command used:

```bash
phoneinfoga scan -n +91XXXXXXXXXX
```

### Result

* No significant public data found
* Indicates **limited OSINT exposure**

---

## 2. Relationship Mapping (Maltego)

### Steps:

* Added phone number entity
* Ran transforms
* Observed results

### Findings:

* Number is **not disposable**
* **No risk detected**

👉 Suggests the number is likely legitimate

---

## 3. Phishing Simulation (SET)

### Method:

* Used **Credential Harvester (Web Templates)**
* Hosted phishing page locally

### Result:

* Test credentials successfully captured

Example:

```text
[*] WE GOT A HIT!
USERNAME: alex
PASSWORD: Password123
```

---

## 4. Vishing Scenario

### Scenario:

An attacker impersonates IT support and convinces the victim to visit a login page.

### Flow:

1. Attacker calls victim
2. Claims security issue
3. Sends phishing link
4. Victim enters credentials
5. Credentials captured

---

## Results

* ✔ Credential harvesting successful
* ✔ OSINT data limited but valid
* ✔ Maltego mapping completed

---

## Log Table

| Target ID | Data Source | Information             | Notes               |
| --------- | ----------- | ----------------------- | ------------------- |
| TID001    | PhoneInfoga | No public data          | Privacy preserved   |
| TID001    | Maltego     | Not disposable, no risk | Legitimate number   |
| TID001    | SET         | Credentials captured    | Successful phishing |

---

## 50-Word Summary

A simulated social engineering attack was conducted using OSINT tools and phishing techniques. A phishing page was deployed and user interaction was observed through credential capture. The exercise demonstrated how attackers exploit trust, gather intelligence, and obtain sensitive information through deceptive methods.

---

## Screenshots (To Include)

* PhoneInfoga scan output
* Maltego graph
* SET credential capture
* Phishing page in browser

---

## Conclusion

This lab demonstrates how social engineering attacks can effectively bypass technical defenses by targeting human behavior. Even with limited OSINT data, attackers can combine phishing and vishing techniques to obtain sensitive information.

---
