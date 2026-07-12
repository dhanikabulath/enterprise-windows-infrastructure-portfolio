# Project 09 - Windows Server Security Hardening

## Overview

This project focuses on strengthening the security posture of a Windows Server 2022 domain controller by implementing and validating common enterprise security configurations. Security settings were configured using Group Policy and verified through PowerShell and built-in Windows administration tools.

The project demonstrates practical experience in configuring account security, audit policies, Microsoft Defender, Windows Firewall, Remote Desktop security, SMB security, and Windows security monitoring.

---

# Objectives

- Configure Account Lockout Policy
- Configure Advanced Audit Policies
- Verify Microsoft Defender Antivirus
- Validate Windows Defender Firewall
- Review Remote Desktop security configuration
- Validate SMB server security settings
- Review local administrator configuration
- Monitor Windows Security Event Logs
- Verify installed security updates

---

# Environment

| Component | Configuration |
|-----------|---------------|
| Operating System | Windows Server 2022 Datacenter |
| Domain | corp.novatech.local |
| Server | DC01 |
| Management Tools | Group Policy Management, PowerShell |

---

# Lab 1 – Account Lockout Policy

Configured enterprise account lockout settings to reduce brute-force attack risks.

Configured:

- Account Lockout Threshold
- Lockout Duration
- Reset Lockout Counter

### Validation

```powershell
Get-ADDefaultDomainPasswordPolicy |
Select LockoutThreshold,
LockoutDuration,
LockoutObservationWindow
```

![Account Lockout](Screenshots/01_Account_Lockout_Policy.jpeg)

![Validation](Screenshots/02_Account_Lockout_Validation.jpeg)

---

# Lab 2 – Advanced Audit Policies

Configured auditing for:

- Credential Validation
- Logon Events
- User Account Management
- Authentication Policy Changes

Applied Group Policy:

```powershell
gpupdate /force
```

Validated:

```cmd
auditpol /get /category:*
```

![Credential Validation](Screenshots/03_Audit_Credential_Validation.jpeg)

![Audit Logon](Screenshots/04_Audit_Logon.jpeg)

![User Account Management](Screenshots/05_Audit_User_Account_Management.jpeg)

![Authentication Policy Change](Screenshots/06_Audit_Authentication_Policy_Change.jpeg)

![GPUpdate](Screenshots/07_GPUpdate_Force.jpeg)

![Audit Validation](Screenshots/08_AuditPol_Validation.jpeg)

---

# Lab 3 – Microsoft Defender

Verified Windows Defender Antivirus configuration.

```powershell
Get-MpComputerStatus
```

```powershell
Get-MpPreference
```

```powershell
Get-MpComputerStatus |
Select AntivirusSignatureVersion,
AntispywareSignatureVersion,
AntivirusEnabled,
RealTimeProtectionEnabled
```

![Defender Status](Screenshots/09_Defender_Status.jpeg)

![Defender Preferences](Screenshots/10_Defender_Preferences.jpeg)

![Defender Signatures](Screenshots/11_Defender_Signatures.jpeg)

---

# Lab 4 – Windows Defender Firewall

Validated Windows Firewall profiles and enabled rules.

```powershell
Get-NetFirewallProfile
```

```powershell
Get-NetFirewallRule |
Where-Object Enabled -eq True |
Select -First 20
```

![Firewall Profiles](Screenshots/12_Firewall_Profiles.jpeg)

![Firewall Rules](Screenshots/13_Firewall_Rules.jpeg)

---

# Lab 5 – Remote Desktop Security

Verified Remote Desktop configuration and firewall rules.

```powershell
Get-ItemProperty "HKLM:\System\CurrentControlSet\Control\Terminal Server" -Name fDenyTSConnections
```

```powershell
Get-NetFirewallRule -DisplayGroup "Remote Desktop"
```

![RDP Status](Screenshots/14_RDP_Status.jpeg)

![RDP Firewall](Screenshots/15_RDP_Firewall_Rules.jpeg)

---

# Lab 6 – SMB Security

Validated SMB server security configuration.

```powershell
Get-SmbServerConfiguration |
Select EnableSMB1Protocol,
EnableSMB2Protocol,
EncryptData,
RequireSecuritySignature
```

![SMB Security](Screenshots/16_SMB_Server_Configuration.jpeg)

---

# Lab 7 – Administrator Review

Reviewed administrator group membership.

```powershell
Get-LocalGroupMember Administrators
```

or

```cmd
net localgroup administrators
```

![Administrators](Screenshots/17_Local_Administrators.jpeg)

---

# Lab 8 – Security Event Monitoring

Reviewed recent security events.

```powershell
Get-WinEvent -LogName Security -MaxEvents 20
```

![Security Log](Screenshots/18_Security_Event_Log.jpeg)

---

# Lab 9 – Installed Security Updates

Validated installed Windows updates.

```powershell
Get-HotFix
```

![Installed Updates](Screenshots/19_Installed_Security_Updates.jpeg)

---

# Skills Demonstrated

- Windows Server Security
- Group Policy Security Configuration
- Windows Defender Administration
- Windows Firewall Administration
- Remote Desktop Security
- SMB Security
- Windows Event Log Analysis
- Security Monitoring
- PowerShell Administration
- Enterprise Security Validation

---

# Lessons Learned

This project demonstrates practical Windows Server security administration through the implementation and validation of enterprise security controls. Core security features including account protection, auditing, endpoint protection, firewall configuration, SMB security, and event monitoring were configured and verified using Microsoft administrative tools and PowerShell.

---

# Next Project

## Enterprise Network Analysis (Wireshark & Nmap)

The next repository focuses on enterprise network analysis, packet inspection, protocol analysis, and network discovery using Wireshark and Nmap.