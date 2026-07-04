# User Account Management

## Overview

This section demonstrates how common Active Directory user account management tasks generate Windows Security Events that can be monitored and investigated using Splunk Enterprise.

The investigation covers user account creation, account disablement, password resets, and account enablement.

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
| 4720 | User account created |
| 4722 | User account enabled |
| 4724 | Password reset |
| 4725 | User account disabled |

---

# Demonstration

## 1. User Account Created

A new Active Directory user account (**Test01**) was created.

### Active Directory

![Create User](screenshots/create-user-ad.png)

### SPL Query

```spl
index=* EventCode=4720
```

### Splunk Verification

![Event ID 4720](screenshots/event-4720-user-created.png)

---

## 2. User Account Disabled

The user account was disabled in Active Directory.

### Active Directory

![Disabled Account](screenshots/disabled-account-popup.png)

### SPL Query

```spl
index=* EventCode=4725
```

### Splunk Verification

![Event ID 4725](screenshots/event-4725-user-disabled.png)

---

## 3. Password Reset

The user's password was reset using Active Directory Users and Computers.

### Active Directory

![Reset Password](screenshots/reset-password-dialog.png)

### SPL Query

```spl
index=* EventCode=4724
```

### Splunk Verification

![Event ID 4724](screenshots/event-4724-password-reset.png)

---

## 4. User Account Enabled

The account was enabled, allowing the user to authenticate successfully.

### SPL Query

```spl
index=* EventCode=4722
```

### Splunk Verification

![Event ID 4722](screenshots/event-4722-user-enabled.png)

---

## Findings

The investigation confirmed that Windows Security Events accurately recorded each administrative action. Splunk successfully identified the event IDs, affected user account, and administrator responsible for the changes.
