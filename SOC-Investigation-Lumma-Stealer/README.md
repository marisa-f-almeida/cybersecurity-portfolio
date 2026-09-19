# SOC Investigation Report: SOC338 – Lumma Stealer via Click Fix Phishing

## Executive Summary
An email alert was triggered indicating a suspicious inbound email offering a fake "Windows 11 Pro Upgrade". Investigation confirmed the email contained a phishing payload utilizing the "Click Fix" tactic to trick the user into executing a malicious script. The target host accessed the payload and executed the script. Remediative actions were taken immediately to purge the email and isolate the affected host.

## Incident Details
- **Alert ID / Event ID:** SOC338 / 316
- **Severity:** Critical
- **Alert Rule:** Lumma Stealer - DLL Side-Loading via Click Fix Phishing
- **Target User:** dylan@letsdefend.io
- **Sender Address:** update@windows-update.site
- **Source IP:** 132.232.40.201
- **Verdict:** True Positive

## Indicators of Compromise (IoCs)
| Artifact Type | Value | Context |
| :--- | :--- | :--- |
| **Sender Domain** | `windows-update.site` | Spoofed update domain |
| **Source IP** | `132.232.40.201` | Mail delivery origin |
| **Attack Vector** | Click Fix / Script Execution | Social engineering payload |
| **Threat Family** | Lumma Stealer | Information stealer malware |

## Investigation & Response Steps
1. **Email Triage:** Verified the message contained deceptive phrasing and a malicious domain (`windows-update.site`) disguised as an official update notice.
2. **Log Analysis:** Checked log management to confirm the email was delivered to `dylan@letsdefend.io` and the user clicked the malicious link.
3. **Execution Verification:** Analyzed host network logs and confirmed execution of the Click Fix script payload on Dylan's endpoint.
4. **Containment & Remediation:**
   - Purged the phishing message from the target inbox via Email Security tools.
   - Isolated Dylan's endpoint from the network via EDR controls to prevent C2 communication or data exfiltration.
