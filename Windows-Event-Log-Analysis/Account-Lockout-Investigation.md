# Account Lockout Investigation

## Overview

This section demonstrates how Windows account lockouts can be investigated using Windows Security Event Logs collected in Splunk Enterprise.

Multiple failed authentication attempts were generated to trigger the configured account lockout policy, allowing the resulting security events to be analysed.

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
| 4625 | Failed logon |
| 4740 | User account locked out |

---

# Demonstration

## 1. Failed Authentication Attempts

Multiple failed logon attempts were generated using an incorrect password.

### SPL Query

```spl
index=* EventCode=4625
```

### Splunk Verification

![Failed Logon Event](screenshots/failed-logon-event-4625.png)

---

## 2. Account Lockout

After the configured lockout threshold was reached, Windows generated Event ID 4740.

### SPL Query

```spl
index=* EventCode=4740
```

### Splunk Verification

![Event ID 4740](screenshots/event-4740-account-lockout.png)

---

## 3. Windows Account Lockout

The Windows client confirmed that the user account had been locked.

![Account Lockout](screenshots/account-lockout-screen.png)

---

## 4. Unlocking the Account

The account was unlocked using Active Directory Users and Computers.

![Unlock Account](screenshots/reset-password-dialog.png)

---

## Findings

The investigation confirmed that repeated failed authentication attempts generated Event ID 4625 before the configured account lockout policy triggered Event ID 4740. Splunk successfully identified the affected user account, source computer, and administrator actions used to restore access.
