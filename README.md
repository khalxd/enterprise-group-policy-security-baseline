# Enterprise Group Policy Security Baseline

![Windows Server](https://img.shields.io/badge/Windows%20Server-2022-0078D6?style=for-the-badge&logo=windows)
![Active Directory](https://img.shields.io/badge/Active%20Directory-Enabled-0078D4?style=for-the-badge)
![Group Policy](https://img.shields.io/badge/Group%20Policy-GPMC-blue?style=for-the-badge)
![Microsoft Defender](https://img.shields.io/badge/Microsoft-Defender-5E5E5E?style=for-the-badge)
![Windows Firewall](https://img.shields.io/badge/Windows-Firewall-red?style=for-the-badge)

## Overview

This project demonstrates the implementation of an enterprise Windows security baseline using Microsoft Active Directory Group Policy. The lab simulates a corporate Active Directory environment where security configurations are centrally managed and deployed to domain-joined Windows workstations.

Security settings were implemented, validated, and verified using enterprise administration tools including Group Policy Management, Windows Security, Windows Defender Firewall, Event Viewer, and Group Policy Result (`gpresult`).

---

# Enterprise Scenario

**Scenario**

As a Systems Administrator, your responsibility is to secure domain-joined Windows workstations by deploying standardized security policies through Active Directory Group Policy. Rather than configuring each workstation individually, security settings are centrally managed and automatically applied across the organization to improve consistency, security, and compliance.

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Domain | HOMELAB.LOCAL |
| Domain Controller | DC01 |
| Client Workstation | CLIENT01 |
| Operating System | Windows Server 2022 / Windows 11 |
| Directory Service | Active Directory Domain Services |
| Management Tool | Group Policy Management Console (GPMC) |

---

# Objectives

- Create enterprise security baseline GPOs
- Separate User Configuration and Computer Configuration policies
- Configure workstation security through Group Policy
- Configure Microsoft Defender Antivirus
- Configure Windows Defender Firewall
- Configure Interactive Logon Banner
- Disable AutoPlay and AutoRun
- Configure Advanced Audit Policies
- Validate Group Policy deployment

---

# Group Policy Design

## User Security Baseline

Applied to:

```
Employees OU
```

Configured:

- Screen saver timeout
- Password-protected screen saver

---

## Workstation Security Baseline

Applied to:

```
Workstations OU
```

Configured:

- AutoPlay & AutoRun Hardening
- Interactive Logon Banner
- Microsoft Defender Antivirus
- Windows Defender Firewall
- Remote Desktop Firewall Rules
- Advanced Audit Policies

---

# Security Controls Implemented

## User Security

- Screen saver timeout
- Password-protected screen saver

---

## Workstation Security

### AutoPlay & AutoRun Hardening

Configured:

- Turn off AutoPlay
- Disable AutoRun commands

**Purpose**

Prevent removable media from automatically executing malicious code.

---

### Interactive Logon Banner

Configured an enterprise legal notice displayed before user authentication.

**Purpose**

- Authorized access warning
- Security awareness
- Enterprise compliance

---

### Microsoft Defender Antivirus

Configured:

- Real-Time Protection
- Behavior Monitoring
- Script Scanning

**Purpose**

Provide centralized endpoint protection while preventing users from disabling critical security settings.

---

### Windows Defender Firewall

Configured:

- Domain Firewall Profile
- Remote Desktop Firewall Rules

**Purpose**

Protect workstations from unauthorized inbound connections while allowing approved enterprise services.

---

### Advanced Audit Policies

Configured:

- Audit Logon
- Audit Credential Validation

**Purpose**

Generate security logs for authentication events to support auditing, investigations, and compliance.

---

# Validation

The following tools were used to validate successful policy deployment:

- `gpupdate /force`
- `gpresult /r`
- Windows Security
- Windows Defender Firewall
- Event Viewer

Verification confirmed that all Group Policy Objects were successfully deployed and enforced on the client workstation.

---

# Skills Demonstrated

- Active Directory
- Group Policy Management
- Organizational Units (OUs)
- Windows Server Administration
- Microsoft Defender Antivirus
- Windows Defender Firewall
- Advanced Audit Policies
- Endpoint Security
- Windows Security Hardening
- Enterprise Administration
- Group Policy Troubleshooting
- Security Compliance

---

# Screenshots

## Group Policy Structure

### Workstations OU

![Workstations OU](screenshots/GPO-Link-Workstations.png)

### Employees OU

![Employees OU](screenshots/GPO-Link-Employees.png)

### User Security Baseline

![User Security Baseline](screenshots/GPO-Link-UserSecurityBaseline.png)

---

## User Security Policies

### Screen Saver Policy

![Screen Saver Policy](screenshots/ScreenSaverPolicy.png)

### Screen Lock Verification

![Screen Locked](screenshots/ScreenLocked.png)

---

## Computer Security Policies

### AutoPlay Hardening

![AutoPlay Policy](screenshots/AutoPlayPolicy.png)

### Interactive Logon Banner

![Interactive Logon Banner](screenshots/InteractiveLogonBanner.png)

### Interactive Logon Banner Verification

![Interactive Logon Banner Verification](screenshots/InteractiveLogonBanner-Verification.png)

---

## Microsoft Defender Antivirus

### Real-Time Protection

![Real-Time Protection](screenshots/Defender-RealTimeProtection.png)

### Behavior Monitoring

![Behavior Monitoring](screenshots/Defender-BehaviorMonitoring.png)

### Script Scanning

![Script Scanning](screenshots/Defender-ScriptScanning.png)

### Managed by Organization

![Windows Security](screenshots/WindowsSecurity-ManagedByOrganization.png)

---

## Windows Defender Firewall

### Domain Profile

![Firewall Domain Profile](screenshots/Firewall-DomainProfile.png)

### Managed by Group Policy

![Firewall Managed by Group Policy](screenshots/Firewall-ManagedByGroupPolicy.png)

### Remote Desktop Rule

![Remote Desktop Rule](screenshots/Firewall-RDPRule.png)

### Remote Desktop Rules

![Remote Desktop Rules](screenshots/Firewall-RDPRules.png)

---

## Advanced Audit Policies

### Audit Logon

![Audit Logon](screenshots/AuditPolicy-Logon.png)

### Audit Credential Validation

![Audit Credential Validation](screenshots/AuditPolicy-CredentialValidation.png)

### Security Event Log

![Event Viewer Security Log](screenshots/EventViewer-SecurityLog.png)

---

## Group Policy Verification

### User Security Baseline

![User Security Baseline](screenshots/GPResult-UserBaseline.png)

### Workstation Security Baseline

![Workstation Security Baseline](screenshots/GPResult-WorkstationSecurityBaseline.png)

---

# Key Takeaways

This project demonstrates how enterprise organizations centrally manage Windows security through Active Directory Group Policy. By deploying standardized security baselines through Group Policy Objects (GPOs), administrators can enforce consistent security settings, reduce administrative overhead, and improve compliance across all managed workstations.

The project also demonstrates the importance of validating security configurations using enterprise administration tools to ensure successful policy deployment and enforcement.

---

# Technologies Used

- Windows Server 2022
- Windows 11
- Active Directory Domain Services (AD DS)
- Group Policy Management Console (GPMC)
- Microsoft Defender Antivirus
- Windows Defender Firewall
- Event Viewer
- gpupdate
- gpresult

---

# Future Improvements

- Configure BitLocker policies through Group Policy
- Implement Windows Update management
- Deploy password and account lockout policies
- Configure Software Restriction Policies
- Implement AppLocker application control
- Integrate with Microsoft Intune and Microsoft Entra ID
