# Windows Event Log Analysis

This project demonstrates the collection, analysis, and investigation of Windows Security Event Logs within a home lab environment using Splunk Enterprise. It focuses on common security events encountered by SOC analysts, including authentication activity, user account management, account lockouts, group membership changes, and PowerShell logging.

---

## Topics Covered

- Authentication Events (Event IDs 4624 & 4625)
- User Account Management (4720, 4722, 4724, 4725)
- Account Lockout Investigation (4740)
- Group Membership Changes (4732, 4733)
- PowerShell Operational Logging
- Security Event Analysis using SPL

---

## Environment

- Splunk Enterprise 10.4.0
- Splunk Universal Forwarder
- Windows Server 2022 (Domain Controller)
- Windows 10 Enterprise (Domain Joined)
- Active Directory Domain Services
- Oracle VirtualBox
