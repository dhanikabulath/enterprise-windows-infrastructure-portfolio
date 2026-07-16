# Project 08 - Enterprise Windows Server Troubleshooting

## Overview

This project demonstrates a structured approach to troubleshooting common enterprise Windows Server issues. It covers DNS resolution, DHCP services, Active Directory verification, Event Viewer analysis, disk health, system performance monitoring, and Windows Update verification. These are common administrative tasks performed by IT Support Engineers and System Administrators in enterprise environments.

---

# Objectives

- Troubleshoot DNS resolution issues
- Verify DNS records
- Validate DHCP service health
- Inspect DHCP scopes and leases
- Verify Active Directory services
- Analyze Windows Event Logs
- Monitor disk health
- Identify resource-intensive processes
- Verify Windows Update status

---

# Environment

| Component | Configuration |
|-----------|---------------|
| Server | Windows Server 2022 |
| Client | Windows 11 Pro |
| Domain | enterprise.local |
| Tools | Server Manager, DNS Manager, DHCP Manager, Event Viewer, PowerShell |

---

# Project Structure

```text
08-Enterprise-Troubleshooting
│
├── README.MD
└── Screenshots
```

---

# Scenario

A user reports multiple infrastructure issues including:

- Unable to access the file server by hostname
- Network connectivity problems
- Authentication delays
- Slow server performance

The objective is to systematically diagnose each component of the Windows Server infrastructure.

---

# Lab 1 – DNS Resolution Failure

Verified that the client could not resolve the File Server hostname.

### Screenshot

![DNS Resolution Failed](Screenshots/01_DNS_Resolution_Failed.png)

---

# Lab 2 – Create File Server DNS Record

Created the required DNS A record for the File Server.

### Screenshot

![Create Fileserver DNS Record](Screenshots/02_Create_Fileserver_DNS_Record.png)

---

# Lab 3 – DNS Resolution Success

Verified successful DNS name resolution after creating the DNS record.

### Screenshot

![DNS Resolution Success](Screenshots/03_DNS_Resolution_Success.png)

---

# Lab 4 – DHCP Service Verification

Confirmed that the DHCP Server service was running successfully.

### Screenshot

![DHCP Service Status](Screenshots/05_DHCP_Service_Status.png)

---

# Lab 5 – DHCP Scope Verification

Verified configured DHCP scopes and address pools.

### Screenshot

![DHCP Scopes](Screenshots/06_DHCP_Scopes.png)

---

# Lab 6 – DHCP Lease Verification

Reviewed active DHCP leases assigned to client devices.

### Screenshot

![DHCP Leases](Screenshots/07_DHCP_Leases.png)

---

# Lab 7 – DHCP Statistics

Verified DHCP utilization and lease statistics.

### Screenshot

![DHCP Statistics](Screenshots/08_DHCP_Statistics.png)

---

# Lab 8 – Active Directory Services

Verified that essential Active Directory services were running correctly.

### Screenshot

![Active Directory Services](Screenshots/09_AD_Services.png)

---

# Lab 9 – Event Viewer Analysis

Reviewed Windows System logs for errors and warnings.

### Screenshot

![System Error Events](Screenshots/10_System_Error_Events.png)

---

# Lab 10 – Security Event Log

Reviewed security-related events recorded by Windows.

### Screenshot

![Security Event Log](Screenshots/11_Security_Event_Log.png)

---

# Lab 11 – Disk Health

Verified storage health and disk status.

### Screenshot

![Disk Health](Screenshots/12_Disk_Health.png)

---

# Lab 12 – Performance Monitoring

Identified the processes consuming the highest system resources.

### Screenshot

![Top Processes](Screenshots/13_Top_Processes.png)

---

# Lab 13 – Windows Update Verification

Verified installed Windows updates and system patch status.

### Screenshot

![Installed Updates](Screenshots/14_Installed_Updates.png)

---

# Skills Demonstrated

- DNS Troubleshooting
- DNS Record Management
- DHCP Administration
- DHCP Lease Management
- Active Directory Troubleshooting
- Windows Event Viewer Analysis
- Windows Server Diagnostics
- Performance Monitoring
- Disk Health Verification
- Windows Update Management
- Enterprise Troubleshooting Methodology

---

# Lessons Learned

This project demonstrates a systematic troubleshooting methodology for diagnosing and resolving common Windows Server infrastructure issues. It emphasizes validating core enterprise services such as DNS, DHCP, Active Directory, storage, and system performance using built-in Microsoft administration tools.

---

# Next Project

## Project 09 – Windows Server Security Hardening

The next project focuses on implementing enterprise security best practices including account policies, auditing, Microsoft Defender configuration, Windows Firewall management, Remote Desktop security, SMB hardening, and Windows Update security.
