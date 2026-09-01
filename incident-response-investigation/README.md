# 🔐 Incident Response Investigation

## Project Overview

This project is a hands-on cybersecurity investigation based on a simulated security incident.

The goal is to analyze authentication activity, identify suspicious behavior, document Indicators of Compromise (IOCs), assess the potential severity of the incident, and recommend appropriate response actions.

## Objectives

* Analyze authentication logs
* Identify suspicious login activity
* Identify Indicators of Compromise (IOCs)
* Investigate potential account compromise
* Assess the severity of the incident
* Recommend containment and remediation actions
* Document the investigation process

## Scenario

A security monitoring system detected unusual authentication activity involving the `admin` account.

Multiple failed login attempts were followed by a successful authentication from the same external IP address.

Additional activity was observed after the successful login, including privilege escalation and access to a sensitive file.

## Initial Evidence

| Event                 | Details          |
| --------------------- | ---------------- |
| Target Account        | `admin`          |
| Source IP             | `185.220.101.45` |
| Failed Login Attempts | 5                |
| Successful Login      | Yes              |
| Privilege Escalation  | Detected         |
| Sensitive File Access | Detected         |

## Initial Assessment

The activity is considered suspicious because multiple failed authentication attempts were followed by a successful login and subsequent privileged activity.

The pattern may indicate a potential account compromise or credential-based attack.

Further investigation is required before confirming the root cause.

## Tools and Technologies

* Authentication Logs
* Windows Event Logs
* Linux
* SIEM Concepts
* MITRE ATT&CK
* Incident Response Framework

## Skills Demonstrated

* Log Analysis
* Incident Response
* Threat Detection
* IOC Identification
* Security Monitoring
* Risk Assessment
* Technical Documentation

## Project Status

**In Progress**

The investigation will be expanded with a detailed incident timeline, MITRE ATT&CK mapping, severity assessment, and recommended response actions.
