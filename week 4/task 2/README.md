# Cloud Attack Lab – IAM Privilege Escalation Using CloudGoat

## Overview

This project demonstrates an AWS IAM privilege escalation scenario using the CloudGoat vulnerable cloud environment. The assessment focused on identifying insecure IAM permissions, enumerating cloud resources, exploiting EC2 instance-profile attachment permissions, and validating privilege escalation paths.

The lab was performed in a controlled environment using Kali Linux, Pacu, AWS CLI, Terraform, and CloudGoat.

---

# Objectives

* Enumerate AWS IAM and EC2 resources
* Analyze IAM policies and roles
* Identify privilege escalation opportunities
* Abuse EC2 instance profile permissions
* Demonstrate cloud privilege escalation techniques
* Clean up deployed infrastructure securely

---

# Tools Used

| Tool       | Purpose                                   |
| ---------- | ----------------------------------------- |
| CloudGoat  | Vulnerable AWS cloud lab environment      |
| Pacu       | AWS exploitation framework                |
| AWS CLI    | AWS resource interaction and enumeration  |
| Terraform  | Infrastructure deployment and destruction |
| Kali Linux | Attacker machine                          |

---

# Lab Scenario

The CloudGoat scenario used in this project was:

```bash
iam_privesc_by_attachment
```

This scenario demonstrates how a low-privileged IAM user can escalate privileges by abusing EC2 instance-profile attachment permissions.

---

# Attack Workflow

## 1. Environment Initialization

* CloudGoat scenario deployed
* AWS credentials configured
* Pacu initialized

---

## 2. IAM Enumeration

The following enumeration activities were performed:

* IAM role discovery
* IAM policy analysis
* EC2 permission validation
* AccessDenied reconnaissance
* Identification of dangerous permissions

Example permissions discovered:

```json
iam:PassRole
ec2:RunInstances
ec2:AssociateIamInstanceProfile
```
---

## 3. IAM Role Analysis

Two important IAM roles were identified:

### Meek Role

A restricted role with deny-all permissions.

### Mighty Role

An over-permissive role with wildcard administrative access:

```json
"Action": "*",
"Resource": "*"
```

This role became the privilege escalation target.
---

## 4. AWS IAM Configuration Review

The IAM dashboard and policies were reviewed to identify insecure configurations and attached permissions.

---

## 5. EC2 Abuse and Instance Profile Enumeration

The attacker used EC2 permissions to:

* Launch EC2 instances
* Attach IAM instance profiles
* Enumerate attached profiles
* Validate role associations

AWS CLI commands used:

```bash
aws ec2 run-instances
aws iam list-roles
aws iam list-instance-profiles
aws ec2 describe-instances
```

---

## 6. Privilege Escalation Validation

The assessment validated that:

* EC2 instance profile abuse could be performed
* IAM role attachment permissions were dangerous
* Misconfigured IAM policies enabled privilege escalation paths

A failed attachment attempt also demonstrated AWS quota enforcement mechanisms.
---

## 7. Cleanup Operations

Terraform destroy operations were executed to safely remove:

* IAM users
* IAM policies
* EC2 instances
* IAM roles
* Networking resources

---

# Key Findings

* Overly permissive IAM roles create severe privilege escalation risks
* `iam:PassRole` combined with EC2 permissions is dangerous
* EC2 instance-profile abuse is a valid cloud attack path
* Infrastructure-as-Code deployments should be reviewed carefully
* Principle of Least Privilege was not enforced properly

---

# Security Recommendations

## Implement Least Privilege

Avoid wildcard permissions such as:

```json
"Action": "*"
```

---

## Restrict `iam:PassRole`

Limit which roles users can pass to EC2 instances.

---

## Monitor EC2 Instance Profile Changes

Enable logging and monitoring for:

* Instance profile attachment
* IAM policy changes
* Role assumptions

---

## Review Infrastructure-as-Code

Audit Terraform and CloudFormation deployments for insecure IAM configurations.

---

# Conclusion

The CloudGoat IAM privilege escalation scenario successfully demonstrated how insecure IAM permissions and EC2 instance-profile associations can be abused to escalate privileges within AWS environments.

The assessment highlighted the importance of:

* strict IAM policy management
* least privilege enforcement
* infrastructure security reviews
* continuous cloud monitoring

---


