# Security Monitoring

## Overview

This section documents the use of Splunk Enterprise to monitor and investigate security-related events collected from Windows and Linux systems. Using Splunk Processing Language (SPL), logs were searched and filtered to identify authentication activity, account management events, PowerShell activity, and Linux authentication logs.

---

## Objectives

- Monitor Windows and Linux security events
- Perform security investigations using SPL
- Identify authentication activity
- Monitor account management events
- Investigate PowerShell activity

---

## Environment

- Splunk Enterprise 10.4.0
- Windows 10 Enterprise
- Windows Server 2022
- Ubuntu Server
- Oracle VirtualBox

---

## Activities Performed

- Investigated Windows authentication events.
- Monitored account management activity.
- Searched PowerShell Operational logs.
- Reviewed Linux authentication events.
- Used SPL queries to filter and investigate security events.

---

## Sample Security Queries

### Failed Logon Attempts

```spl
index=* EventCode=4625
```

---

### Successful Logons

```spl
index=* EventCode=4624
```

---

### Account Lockouts

```spl
index=* EventCode=4740
```

---

### User Account Created

```spl
index=* EventCode=4720
```

---

### User Account Enabled

```spl
index=* EventCode=4722
```

---

### User Account Disabled

```spl
index=* EventCode=4725
```

---

### Group Membership Changes

```spl
index=* EventCode=4732
```

---

### PowerShell Activity

```spl
index=* source="WinEventLog:Microsoft-Windows-PowerShell/Operational"
```

---

### Linux Authentication Events

```spl
index=* source="/var/log/auth.log"
```

---

## Verification

Security monitoring was verified by confirming:

- Windows security events were searchable.
- Linux authentication events were searchable.
- Authentication activity could be filtered using SPL.
- Account management events could be investigated.
- PowerShell Operational logs were successfully collected and searched.

---

## Summary

Splunk Enterprise was successfully configured to monitor Windows and Linux security events within the home lab environment. SPL queries were used to investigate authentication activity, account management events, PowerShell logs, and Linux authentication events, demonstrating practical experience with security monitoring and event investigation.
