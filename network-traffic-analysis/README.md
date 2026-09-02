# Network Traffic Analysis

## 🔎 Project Overview

This project simulates a basic network traffic analysis performed by a cybersecurity analyst.

The objective is to review network connection data, identify suspicious activity, analyze communication patterns, and recommend appropriate security actions.

This project demonstrates fundamental network security and security monitoring skills.

## 🎯 Analysis Objectives

* Analyze network connections.
* Identify source and destination IP addresses.
* Identify network protocols and ports.
* Detect unusual communication patterns.
* Identify potential Indicators of Compromise (IOCs).
* Assess security risks.
* Recommend appropriate response actions.

## 🌐 Simulated Network Traffic

The following traffic was collected from a simulated network environment.

| Time     | Source IP      | Destination IP   | Protocol | Port | Activity            |
| -------- | -------------- | ---------------- | -------- | ---- | ------------------- |
| 10:14:02 | `192.168.1.25` | `8.8.8.8`        | DNS      | 53   | DNS Query           |
| 10:14:15 | `192.168.1.25` | `142.250.72.14`  | HTTPS    | 443  | Web Connection      |
| 10:15:33 | `192.168.1.25` | `185.220.101.45` | TCP      | 4444 | Outbound Connection |
| 10:15:41 | `192.168.1.25` | `185.220.101.45` | TCP      | 4444 | Outbound Connection |
| 10:16:02 | `192.168.1.25` | `185.220.101.45` | TCP      | 4444 | Outbound Connection |
| 10:17:19 | `192.168.1.25` | `8.8.8.8`        | DNS      | 53   | DNS Query           |
| 10:18:44 | `192.168.1.25` | `142.250.72.14`  | HTTPS    | 443  | Web Connection      |

## 🔍 Initial Analysis

Most of the traffic appears consistent with normal network activity.

For example:

* DNS traffic is using port `53`.
* HTTPS traffic is using port `443`.
* Connections to public infrastructure may be normal depending on the application being used.

However, repeated outbound TCP connections to `185.220.101.45` on port `4444` require further investigation.

## 🚩 Suspicious Activity

### Destination IP

`185.220.101.45`

### Destination Port

`4444`

### Protocol

TCP

### Activity

Multiple outbound connections were observed within a short period.

### Analyst Assessment

Repeated outbound connections to an unusual external IP address and port may indicate suspicious software, unauthorized remote access, command-and-control communication, or another application requiring investigation.

The traffic alone does not confirm malicious activity.

Additional endpoint, DNS, firewall, and process information should be collected before determining whether the connection is malicious.

## 🧠 Network Concepts Demonstrated

### DNS

**Port:** `53`

DNS is used to translate domain names into IP addresses.

### HTTPS

**Port:** `443`

HTTPS provides encrypted communication between a client and a web server.

### TCP

TCP is a connection-oriented transport protocol that provides reliable delivery of network traffic.

### IP Address

An IP address identifies a device or destination on a network.

### Network Port

A port identifies a specific service or application endpoint on a device.

## 🚨 Potential Indicator of Compromise

| IOC Type           | Indicator                           | Reason                                       |
| ------------------ | ----------------------------------- | -------------------------------------------- |
| Destination IP     | `185.220.101.45`                    | Repeated outbound connections                |
| Destination Port   | `4444`                              | Unusual service port requiring investigation |
| Protocol           | TCP                                 | Repeated external connections                |
| Connection Pattern | Multiple connections within minutes | Potential suspicious communication           |

## 🛡️ Recommended Investigation

A security analyst should:

1. Identify the process responsible for the outbound connection.
2. Review endpoint security logs.
3. Review firewall logs.
4. Review DNS queries from the affected workstation.
5. Determine whether the destination IP is known or trusted.
6. Check whether other systems communicated with the same destination.
7. Investigate the workstation for suspicious software.
8. Search for additional Indicators of Compromise.
9. Isolate the endpoint if malicious activity is confirmed or strongly suspected.
10. Document all findings and response actions.

## 📊 Risk Assessment

**Severity:** Medium to High

The observed network traffic requires further investigation because repeated outbound connections to an unusual external destination may indicate unauthorized communication.

The severity should be increased if additional evidence confirms malicious software, command-and-control activity, or unauthorized remote access.

## 📝 Analyst Conclusion

The simulated network traffic analysis identified a potentially suspicious communication pattern involving repeated outbound TCP connections to `185.220.101.45` on port `4444`.

Although the traffic does not independently confirm malicious activity, the connection pattern warrants additional investigation.

A cybersecurity analyst should correlate network traffic with endpoint, DNS, firewall, and authentication data before determining the full scope and impact.

**Investigation Status:** Open

**Analyst:** Marisa F. Almeida
