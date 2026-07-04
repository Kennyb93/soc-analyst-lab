# Authentication Events

## Overview

This section demonstrates how Windows authentication events can be monitored using Windows Security Event Logs collected by Splunk Enterprise.

Both successful and failed authentication attempts were generated to demonstrate how authentication activity can be investigated using Windows Security Event IDs.

---

## Environment

- Splunk Enterprise 10.4.0
- Splunk Universal Forwarder
- Windows Server 2022 Domain Controller
- Windows 10 Enterprise (Domain Joined)
- Active Directory Domain Services
- Oracle VirtualBox

---

## Event IDs

| Event ID | Description |
|----------|-------------|
| 4624 | Successful logon |
| 4625 | Failed logon |

---

# Demonstration

## 1. Failed Authentication

An incorrect password was entered to generate a failed authentication event.

### SPL Query

```spl
index=* EventCode=4625
```

### Splunk Verification

![Failed Logon Event](screenshots/failed-logon-event-4625.png)

---

## 2. Successful Authentication

The correct credentials were entered to generate a successful authentication event.

### SPL Query

```spl
index=* EventCode=4624
```

### Splunk Verification

![Successful Logon Event](screenshots/successful-logon-event-4624.png)

---

## Findings

The investigation confirmed that Windows Security Events accurately recorded both successful and failed authentication attempts. Splunk successfully identified the username, logon type, authentication package, source workstation, and outcome of each authentication event.
