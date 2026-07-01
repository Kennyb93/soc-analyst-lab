# SPL Queries

## Overview

This section documents a collection of Splunk Processing Language (SPL) queries used throughout the lab to validate log ingestion, identify data sources, and search collected events.

---

## Objectives

- Validate data ingestion
- Identify hosts and event sources
- Verify sourcetypes
- Perform basic event searches

---

## Environment

- Splunk Enterprise 10.4.0
- Windows 10 Enterprise
- Ubuntu Server
- Oracle VirtualBox

---

# Query Reference

## Count Events by Host

Displays the number of indexed events for each host.

```spl
index=*
| stats count by host
```

---

## Count Events by Source

Displays all event sources currently indexed in Splunk.

```spl
index=*
| stats count by source
```

---

## Count Events by Sourcetype

Displays the sourcetypes assigned to collected events.

```spl
index=*
| stats count by sourcetype
```

---

## Search Windows Events

Returns Windows Event Logs from the Windows 10 Enterprise host.

```spl
index=* host=DESKTOP-0Q5STJ5
```

---

## Search Linux Authentication Logs

Returns authentication events collected from the Ubuntu server.

```spl
index=* source="/var/log/auth.log"
```

---

## Search Linux System Logs

Returns system events collected from the Ubuntu server.

```spl
index=* source="/var/log/syslog"
```

---

## Search Windows Security Events

Returns Windows Security Event Logs.

```spl
index=* source="WinEventLog:Security"
```

---

## Search Windows System Events

Returns Windows System Event Logs.

```spl
index=* source="WinEventLog:System"
```

---

## Search Windows Application Events

Returns Windows Application Event Logs.

```spl
index=* source="WinEventLog:Application"
```

---

# Summary

These SPL queries were used throughout the home lab to verify successful log ingestion, validate data sources, and perform basic event searches before conducting security investigations.
