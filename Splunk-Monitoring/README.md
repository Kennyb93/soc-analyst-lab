# Splunk Monitoring

This section documents the deployment and use of Splunk Enterprise for log collection, monitoring, and investigation within a home lab environment.

## Topics Covered

- Windows Event Log ingestion
- Linux log collection
- Splunk Universal Forwarder configuration
- SPL searches and queries
- Security event analysis

## Environment

- Splunk Enterprise
- Splunk Universal Forwarder
- Windows 10
- Windows Server 2022
- Ubuntu Linux

## Windows Endpoint Security Monitoring Dashboard

Built a Splunk dashboard to provide centralized visibility into Windows endpoint activity using Sysmon telemetry.

The dashboard provides visibility into:

- Total security events and process activity
- Network connections and destination IP addresses
- Process activity over time
- Most frequently executed processes
- DNS queries
- Network connections by process
- Recent file creation activity
- Windows Registry modifications

The dashboard uses Sysmon events forwarded from a Windows endpoint to Splunk Enterprise using the Splunk Universal Forwarder.

### Dashboard

![Windows Endpoint Security Monitoring Dashboard](screenshots/windows-endpoint-security-dashboard.png)

## Activities

### Log Collection
- Configured Windows Event Log forwarding
- Collected Linux authentication and system logs
- Verified successful data ingestion into Splunk

### Monitoring and Analysis
- Investigated authentication events
- Reviewed Windows Security Logs
- Analyzed Linux authentication activity
- Performed event searches using SPL

### Splunk Administration
- Installed and configured Splunk Enterprise
- Configured data inputs
- Managed indexes and searches
- Connected Universal Forwarders

## Goals

Develop practical experience with SIEM technologies, log analysis, security monitoring, and incident investigation while building skills relevant to a SOC Analyst role.
