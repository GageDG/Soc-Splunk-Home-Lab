# Splunk SIEM Server Setup

## Overview

This system hosts the Splunk SIEM used to collect and analyze logs from endpoints within the SOC lab environment.

Hostname: SOC-SIEM01  
Operating System: Ubuntu Server  
Role: Security Information and Event Management (SIEM)

---

## System Configuration

CPU: 2 cores  
RAM: 4 GB  
Disk: 40 GB  

Network: Internal NAT network

---

## Splunk Installation

Splunk Enterprise was installed on Ubuntu using the official .deb package.

Installation command:

sudo dpkg -i splunk*.deb

After installation, Splunk was started with:

sudo /opt/splunk/bin/splunk start

The Splunk web interface runs on port 8000.

Access URL:

http://192.168.184.128:8000/

---

## Boot Persistence

Splunk was configured to start automatically when the server boots.

Command used:

sudo /opt/splunk/bin/splunk enable boot-start -user splunk

This ensures the SIEM service remains operational after system reboots.

Average expected Splunk system reboot time is <**5:45**>

---

## Purpose in the Lab

The Splunk server performs the following functions:

• Centralized log collection  
• Security event monitoring  
• Threat detection  
• Incident investigation

Logs will be forwarded from Kali Linux and Window endpoints using the Splunk Universal Forwarder.
