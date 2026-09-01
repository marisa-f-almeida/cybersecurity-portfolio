# Incident Timeline

## Incident Timeline Overview

This timeline documents the sequence of events identified during the simulated security incident.

| Time     | User     | Source IP        | Event                 |
| -------- | -------- | ---------------- | --------------------- |
| 22:14:03 | `jsmith` | `192.168.1.25`   | Successful Login      |
| 22:15:11 | `admin`  | `185.220.101.45` | Failed Login          |
| 22:15:14 | `admin`  | `185.220.101.45` | Failed Login          |
| 22:15:17 | `admin`  | `185.220.101.45` | Failed Login          |
| 22:15:20 | `admin`  | `185.220.101.45` | Failed Login          |
| 22:15:23 | `admin`  | `185.220.101.45` | Failed Login          |
| 22:15:31 | `admin`  | `185.220.101.45` | Successful Login      |
| 22:16:02 | `admin`  | `185.220.101.45` | Privilege Escalation  |
| 22:17:45 | `admin`  | `185.220.101.45` | Sensitive File Access |

## Key Observations

* Five failed login attempts occurred within a short period.
* All five failed attempts originated from the same external IP address.
* A successful login occurred shortly after the failed attempts.
* Privilege escalation was detected after the successful login.
* Sensitive file access occurred shortly afterward.
* The sequence of events requires further investigation.

## Analyst Assessment

The timeline shows a suspicious sequence of authentication and post-authentication activity.

The combination of repeated failed logins, a successful login, privilege escalation, and sensitive file access may indicate an attempted or successful compromise of the administrative account.

Further investigation is required to determine whether the activity was authorized and to identify the full scope of the incident.
