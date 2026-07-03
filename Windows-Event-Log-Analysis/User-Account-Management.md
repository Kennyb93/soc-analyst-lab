# User Account Management

## Overview

This section demonstrates the monitoring and investigation of user account management events within an Active Directory environment. Windows Security Event Logs were collected using the Splunk Universal Forwarder and analysed in Splunk Enterprise to verify common administrative actions such as user creation, account enablement, password resets, and account disablement.

---

## Objectives

- Monitor Active Directory user account management events.
- Identify Windows Security Event IDs related to account administration.
- Verify user management activity using Splunk Enterprise.
- Correlate administrative actions with Windows Security Event Logs.

---

## Environment

- Splunk Enterprise 10.4.0
- Splunk Universal Forwarder
- Windows Server 2022 Domain Controller
- Windows 10 Enterprise (Domain Joined)
- Active Directory Domain Services
- Oracle VirtualBox

---

## Event IDs Investigated

| Event ID | Description |
|----------|-------------|
| 4720 | User account created |
| 4722 | User account enabled |
| 4724 | Password reset attempted |
| 4725 | User account disabled |

---

## Activities Performed

- Created a new Active Directory user account.
- Enabled the user account.
- Reset the user's password.
- Disabled the user account.
- Verified each administrative action using Windows Security Event Logs collected in Splunk.

---

## Verification

The investigation confirmed that:

- User account creation generated Event ID 4720.
- Enabling the account generated Event ID 4722.
- Password reset activity generated Event ID 4724.
- Disabling the account generated Event ID 4725.
- All events contained the administrator account responsible for performing the action.

---

# Screenshots

## 1. User Account Created

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

### SPL Query

```spl
index=* EventCode=4722
```

### Splunk Verification

![Event ID 4722](screenshots/event-4722-user-enabled.png)
