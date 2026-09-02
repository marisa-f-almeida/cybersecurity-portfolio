# SIEM Security Monitoring

## 🔎 Project Overview

This project simulates a Security Information and Event Management (SIEM) investigation.

The objective is to analyze security events, identify suspicious patterns, correlate multiple alerts, and recommend appropriate incident response actions.

This project demonstrates fundamental Security Operations Center (SOC) skills.

## 🎯 Investigation Objectives

* Analyze security logs.
* Identify suspicious authentication activity.
* Correlate multiple security events.
* Identify potential Indicators of Compromise (IOCs).
* Assess alert severity.
* Recommend incident response actions.
* Document investigation findings.

## 🖥️ Simulated Environment

The simulated environment contains:

| Asset            | Type           | Purpose              |
| ---------------- | -------------- | -------------------- |
| `WORKSTATION-01` | Windows 11     | Employee workstation |
| `FILE-SRV-01`    | Windows Server | File server          |
| `WEB-SRV-01`     | Windows Server | Web server           |
| `SIEM-01`        | SIEM Platform  | Security monitoring  |

## 📊 Security Events

The SIEM generated the following simulated events:

| Time     | Host             | User     | Source IP        | Event                 |
| -------- | ---------------- | -------- | ---------------- | --------------------- |
| 09:42:11 | `WORKSTATION-01` | `jsmith` | `192.168.1.25`   | Successful Login      |
| 09:43:02 | `FILE-SRV-01`    | `admin`  | `185.220.101.45` | Failed Login          |
| 09:43:05 | `FILE-SRV-01`    | `admin`  | `185.220.101.45` | Failed Login          |
| 09:43:08 | `FILE-SRV-01`    | `admin`  | `185.220.101.45` | Failed Login          |
| 09:43:11 | `FILE-SRV-01`    | `admin`  | `185.220.101.45` | Failed Login          |
| 09:43:14 | `FILE-SRV-01`    | `admin`  | `185.220.101.45` | Failed Login          |
| 09:43:21 | `FILE-SRV-01`    | `admin`  | `185.220.101.45` | Successful Login      |
| 09:44:03 | `FILE-SRV-01`    | `admin`  | `185.220.101.45` | Privilege Escalation  |
| 09:45:17 | `FILE-SRV-01`    | `admin`  | `185.220.101.45` | Sensitive File Access |

## 🚨 Alert Detection

The SIEM generated an alert based on the following pattern:

**Multiple failed logins → Successful login → Privilege escalation → Sensitive file access**

This sequence represents a potentially high-risk security event.

## 🧠 Event Correlation

Individually, a failed login may not indicate malicious activity.

However, multiple failed authentication attempts followed by a successful login from the same external IP address are more suspicious.

The subsequent privilege escalation and sensitive file access increase the potential impact.

Correlating these events allows the analyst to identify a suspicious sequence that may not be obvious when reviewing individual events.

## 🚩 Potential Indicators of Compromise

| IOC Type               | Indicator                          | Reason                                                |
| ---------------------- | ---------------------------------- | ----------------------------------------------------- |
| Source IP              | `185.220.101.45`                   | Repeated authentication activity                      |
| Account                | `admin`                            | Multiple failed attempts followed by successful login |
| Authentication Pattern | 5 failed logins → successful login | Potential credential attack                           |
| Privilege Activity     | Privilege escalation               | Elevated access detected                              |
| File Activity          | Sensitive file access              | Potential unauthorized access                         |

## 📈 Alert Severity

**Severity:** High

The alert should be treated as high priority because multiple suspicious events occurred in sequence.

However, the available logs alone do not prove that the account was compromised.

Additional evidence should be collected before confirming malicious activity.

## 🛡️ Analyst Investigation

The analyst should:

1. Review authentication logs.
2. Verify whether the `admin` login was authorized.
3. Investigate the source IP address.
4. Review endpoint security alerts.
5. Investigate the privilege escalation event.
6. Review sensitive file access logs.
7. Search the SIEM for additional activity from the same IP.
8. Search for activity involving the `admin` account on other systems.
9. Check for suspicious processes or applications.
10. Determine whether other systems were affected.

## 🚨 Recommended Response

If the investigation confirms unauthorized activity:

1. Disable or restrict the affected account.
2. Reset the account credentials.
3. Revoke active sessions or authentication tokens when appropriate.
4. Isolate affected systems if necessary.
5. Block confirmed malicious network indicators.
6. Preserve relevant logs and evidence.
7. Investigate additional affected systems.
8. Document containment and remediation actions.
9. Continue monitoring for related activity.

## 🧩 MITRE ATT&CK Considerations

The observed behavior may warrant investigation for techniques related to:

* **Brute Force**
* **Valid Accounts**
* **Privilege Escalation**
* **Data from Local System**

These are investigation hypotheses rather than confirmed techniques until additional evidence is collected.

## 📝 Analyst Conclusion

The simulated SIEM investigation identified a suspicious sequence involving repeated authentication failures, a successful administrative login, privilege escalation, and sensitive file access.

Correlation of these events increased the confidence that the activity required investigation.

The incident should be treated as a **High Severity** alert while additional evidence is collected.

**Alert Status:** Open

**Severity:** High

**Investigation:** Ongoing

**Analyst:** Marisa F. Almeida
