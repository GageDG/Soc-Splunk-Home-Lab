# Windows 11 Endpoint Setup

## Overview

This virtual machine simulates a corporate user workstation within the SOC lab environment and is configured with realistic data to replicate real-world enterprise activity.

Hostname: HR-WKS01  
Operating System: Windows 11  
Role: Endpoint generating security logs

---

## System Configuration

CPU: 2 cores  
RAM: 4 GB  
Disk: 64 GB  

Network: Same network as Splunk SIEM server <**local network**>

---

## User Accounts

Primary user account:

Username: j.smith

This account represents a simulated HY employee and includes information associated with their workstation.

---

## Security Monitoring Tools

The following tools will be installed:

• Sysmon – advanced system monitoring
• Splunk Universal Forwarder – log forwarding

These tools allow security events to be forwarded to the Splunk SIEM server.

---

## Logging Sources

The endpoint will generate logs from:

• Windows Security Logs
• Sysmon process monitoring
• PowerShell activity

These logs will be ingested by Splunk for threat detection and analysis.
