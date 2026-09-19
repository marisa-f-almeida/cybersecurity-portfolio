# SOC Investigation Report: SOC146 – Phishing Mail Detected (Excel 4.0 Macros)

## Executive Summary
An alert was triggered for an incoming email carrying a compressed archive containing an Excel document weaponized with Excel 4.0 (XLM) macros. Investigation confirmed that the email was delivered to the user and the recipient executed the document, initiating network connections to an external Command and Control (C2) domain. Emergency remediation actions were completed to purge the message from the email system and isolate the infected host via EDR controls.

## Incident Details
- **Alert ID / Event ID:** SOC146 / 93
- **Severity:** Medium
- **Alert Rule:** Phishing Mail Detected - Excel 4.0 Macros
- **Target User:** lars@letsdefend.io
- **Target Host / IP:** LarsPRD / 172.16.17.57
- **Sender Address:** trenton@tritowncomputers.com
- **Source IP / SMTP IP:** 24.213.228.54
- **Verdict:** True Positive

## Indicators of Compromise (IoCs)
| Artifact Type | Value | Context |
| :--- | :--- | :--- |
| **Sender Email** | `trenton@tritowncomputers.com` | Phishing delivery address |
| **Source IP** | `24.213.228.54` | Originating mail server IP |
| **Attachment Name** | `research-1646684671.xls` | Weaponized Excel file |
| **C2 Domain / URL** | `nws.visionconsulting.ro` | Malicious Command & Control server |
| **Target Host IP** | `172.16.17.57` | Compromised internal workstation |

## Investigation & Response Steps
1. **Email Header & Body Analysis:** Identified an inbound phishing email disguised as "RE: Meeting Notes" containing an attached `.zip` file with a malicious Excel 4.0 macro spreadsheet.
2. **Threat Intelligence Correlation:** Queried the extracted attachment hashes on VirusTotal, confirming classification as a macro-based Trojan downloader.
3. **Log & Execution Verification:** Checked central network logs in Log Management to verify whether host `172.16.17.57` (LarsPRD) established connection with `nws.visionconsulting.ro`. Confirmed active network communication, confirming payload execution.
4. **Containment & Remediation:**
   - Purged the phishing email from the user's inbox using Email Security management.
   - Initiated network containment on workstation `LarsPRD` (`172.16.17.57`) via Endpoint Security to prevent lateral movement and C2 communications.
