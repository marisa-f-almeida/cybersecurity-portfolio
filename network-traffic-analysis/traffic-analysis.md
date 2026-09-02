# Network Traffic Analysis Findings

## 🔎 Analysis Summary

This document provides a detailed analysis of the simulated network traffic collected from a workstation.

The goal is to identify normal and potentially suspicious network activity and determine which events require additional investigation.

## 🖥️ Affected Host

**Source IP:** `192.168.1.25`

The workstation generated multiple network connections during the observed period.

## 📊 Traffic Analysis

### Normal Activity

The following connections appear consistent with common network activity:

**DNS — Port 53**

DNS queries were observed to `8.8.8.8`.

DNS is commonly used to resolve domain names to IP addresses.

**HTTPS — Port 443**

HTTPS connections were observed to `142.250.72.14`.

HTTPS is commonly used for encrypted web communication.

These events should still be correlated with endpoint and DNS logs when performing a complete investigation.

---

## 🚩 Suspicious Activity

### Repeated TCP Connections

Multiple outbound TCP connections were observed:

| Time     | Source         | Destination      | Port   |
| -------- | -------------- | ---------------- | ------ |
| 10:15:33 | `192.168.1.25` | `185.220.101.45` | `4444` |
| 10:15:41 | `192.168.1.25` | `185.220.101.45` | `4444` |
| 10:16:02 | `192.168.1.25` | `185.220.101.45` | `4444` |

The repeated connections occurred within approximately one minute.

## 🧠 Analyst Assessment

The repeated outbound connections to the same external IP address and port are unusual enough to warrant investigation.

Potential explanations include:

* Legitimate software communication
* Remote administration software
* Unauthorized software
* Malware
* Command-and-control communication

The available network data is not sufficient to confirm malicious activity.

Additional evidence should be collected before classifying the connection as malicious.

## 🔍 Investigation Questions

A security analyst should answer the following questions:

1. What process created the connection?
2. Which application is using port `4444`?
3. Is the destination IP address authorized?
4. Have other workstations contacted the same IP?
5. Was the connection initiated by a user or automatically by software?
6. Are there related DNS requests?
7. Are there suspicious files or processes on the workstation?
8. Are there related authentication events?
9. Does endpoint security software report any alerts?
10. Does firewall telemetry show additional communication?

## 🚨 Potential IOC

**Destination IP:**

`185.220.101.45`

**Destination Port:**

`4444`

**Protocol:**

TCP

**Source Host:**

`192.168.1.25`

**Observed Pattern:**

Repeated outbound connections within a short period.

## 🛡️ Recommended Response

If additional evidence confirms malicious activity, recommended actions may include:

1. Isolate the affected workstation from the network.
2. Preserve relevant logs and evidence.
3. Identify and contain the responsible process or malware.
4. Investigate other systems for the same IOC.
5. Block the malicious destination if confirmed.
6. Reset compromised credentials if necessary.
7. Remove malicious software.
8. Patch affected systems.
9. Monitor for additional suspicious activity.
10. Document the investigation and remediation.

## 📈 Risk Evaluation

**Initial Severity:** Medium

The network activity is suspicious but not sufficient by itself to confirm compromise.

**Escalation Criteria:**

The severity should be increased if investigators discover:

* Confirmed malware
* Known command-and-control communication
* Unauthorized remote access
* Credential compromise
* Data exfiltration
* Additional compromised systems

## 📝 Final Assessment

The simulated investigation identified repeated outbound TCP connections from workstation `192.168.1.25` to external IP address `185.220.101.45` on port `4444`.

The activity should be investigated further and correlated with endpoint, DNS, firewall, and authentication data.

This analysis demonstrates the importance of **network monitoring, IOC identification, evidence correlation, and risk-based incident response**.

**Investigation Status:** Open

**Initial Severity:** Medium

**Analyst:** Marisa F. Almeida
