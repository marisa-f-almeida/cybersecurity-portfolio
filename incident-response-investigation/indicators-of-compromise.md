# Indicators of Compromise (IOCs)

## 1. Overview

Indicators of Compromise (IOCs) are pieces of evidence that may indicate suspicious or malicious activity.

During this simulated incident, several indicators were identified for further investigation.

## 2. Identified IOCs

| Indicator              | Value                                          | Why It Is Suspicious                                                                   |
| ---------------------- | ---------------------------------------------- | -------------------------------------------------------------------------------------- |
| Source IP Address      | `185.220.101.45`                               | Repeated authentication attempts originated from this external IP address.             |
| Target Account         | `admin`                                        | The account experienced multiple failed login attempts followed by a successful login. |
| Authentication Pattern | 5 failed logins followed by a successful login | This pattern may indicate a credential-based attack or account compromise.             |
| Privilege Escalation   | Detected                                       | Elevated privileges were obtained after the successful login.                          |
| Sensitive File Access  | Detected                                       | A sensitive file was accessed after privilege escalation.                              |

## 3. Recommended Investigation

The following actions should be performed to investigate these IOCs:

1. Review authentication logs associated with the source IP address.
2. Determine whether the `admin` account activity was authorized.
3. Review endpoint logs for suspicious processes or commands.
4. Investigate the privilege escalation event.
5. Review logs related to the sensitive file access.
6. Search for additional activity associated with `185.220.101.45`.
7. Document any additional indicators discovered during the investigation.

## 4. Analyst Assessment

The identified indicators show a suspicious sequence of authentication and post-authentication activity.

The source IP address, repeated failed logins, successful authentication, privilege escalation, and sensitive file access should be investigated together to determine whether the administrative account was compromised.

These indicators are considered **potential IOCs** until additional evidence confirms malicious activity.

## 5. Status

**Investigation Status:** Open

**Severity:** High

**Next Step:** Continue investigation and determine the full scope and impact of the incident.
