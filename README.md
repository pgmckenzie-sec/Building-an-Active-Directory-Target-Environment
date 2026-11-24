# Building-an-Active-Directory-Target-Environment
# Phase 1: Building an Active Directory Target Environment

## Project Overview

This phase focused on transforming a basic Active Directory deployment into a realistic enterprise environment designed for ethical hacking, threat detection, and SOC analysis. The lab was built to simulate common corporate infrastructure and provide a safe environment for practicing Active Directory enumeration, privilege escalation, SIEM monitoring, and incident response.

---

## Lab Architecture

### Network Layout

| Host | Role | IP Address |
|--------|--------|------------|
| DC01 | Windows Server 2019 Domain Controller | 192.168.56.10 |
| Kali Linux | Attack Platform | 192.168.56.40 |
| Wazuh Server | SIEM & Security Monitoring | 192.168.56.50 |
| WIN10-USER1 | Domain Workstation | 192.168.56.20 |

---

## Active Directory Configuration

### Organizational Units (OUs)

```text
Company
├── IT
├── HR
├── Finance
└── Management
```

### Domain Users

Created multiple user accounts to simulate a corporate environment:

```text
jsmith
sjones
mbrown
alee
rking
```

### Security Groups

```text
IT Team
HR Team
Finance Team
HelpDesk
Remote Users
```

---

## Shared Resources

The following SMB shares were configured on the Domain Controller:

```text
\\DC01\HR
\\DC01\Finance
\\DC01\IT
```

Sample files included:

```text
Employee_Salaries.xlsx
Payroll2025.xlsx
PasswordPolicy.docx
ITInventory.xlsx
```

These shares were used for enumeration and access control testing.

---

## Security Monitoring

### Wazuh Integration

Configured Wazuh agents and centralized monitoring to collect:

#### Authentication Events

```text
4624 - Successful Logon
4625 - Failed Logon
4648 - Explicit Credential Logon
4672 - Privileged Logon
```

#### User & Group Changes

```text
4720 - User Created
4728 - Added to Security Group
4732 - Added to Local Group
```

#### Kerberos Events

```text
4768 - TGT Request
4769 - Service Ticket Request
4771 - Kerberos Authentication Failure
```

#### PowerShell Monitoring

```text
4103 - Module Logging
4104 - Script Block Logging
```

---

## Objectives

- Deploy and manage Active Directory
- Create realistic enterprise user structure
- Configure shared resources and permissions
- Simulate corporate network activity
- Generate security logs for SIEM analysis
- Prepare environment for future attack simulations
- Practice blue-team monitoring and detection engineering

---

## Skills Demonstrated

- Active Directory Administration
- Windows Server 2022
- User & Group Management
- SMB Share Configuration
- Network Administration
- Wazuh SIEM Deployment
- Security Monitoring
- Threat Detection
- Log Analysis
- SOC Operations

---

## Next Phase

Phase 2 will focus on Active Directory enumeration using:

- Nmap
- SMB Enumeration
- LDAP Enumeration
- BloodHound
- Wazuh Alert Analysis

Goal: Establish a complete attacker reconnaissance workflow while validating defensive detections within the SIEM environment.
