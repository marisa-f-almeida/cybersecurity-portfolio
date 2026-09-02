# Phishing Email Analysis

## 🔎 Analysis Overview

This document provides a structured analysis of a simulated phishing email.

The objective is to identify suspicious characteristics, evaluate potential risks, and document the investigation from a cybersecurity analyst perspective.

## 📧 Email Information

| Field     | Details                                  |
| --------- | ---------------------------------------- |
| Sender    | `security-alert@micros0ft-support.com`   |
| Recipient | `employee@example.com`                   |
| Subject   | `Urgent: Your Account Will Be Suspended` |
| Date      | September 1, 2026                        |
| Severity  | High                                     |

## 🚩 Phishing Indicators

### 1. Look-Alike Domain

The sender uses:

`micros0ft-support.com`

The domain resembles the legitimate Microsoft brand but replaces the letter **o** with the number **0**.

This is a common social engineering technique used to make a malicious domain appear legitimate.

### 2. Urgency and Fear

The email states that the user's account will be suspended unless immediate action is taken.

Creating urgency or fear can pressure users into making unsafe decisions without verifying the message.

### 3. Suspicious Link

The email contains the following URL:

`https://micros0ft-support.com/verify`

The link should not be opened directly during an investigation.

Security analysts should use safe analysis techniques to investigate suspicious URLs and domains.

### 4. Credential Theft Risk

The email asks the recipient to verify their account.

This could potentially lead to a fake login page designed to collect usernames and passwords.

## 🧪 Analyst Assessment

The email contains multiple characteristics consistent with a phishing attempt:

* Deceptive sender domain
* Look-alike domain spelling
* Urgent language
* Suspicious URL
* Request for account verification
* Potential credential harvesting

Based on these indicators, the email should be treated as a **High Severity** security event.

## 🛡️ Recommended Security Actions

1. Do not click the suspicious link.
2. Do not enter credentials or personal information.
3. Report the email to the security team.
4. Investigate the sender domain and URL using approved security tools.
5. Search security logs for connections to the suspicious domain.
6. Determine whether other users received the same email.
7. Check whether any users clicked the link or submitted credentials.
8. Reset credentials immediately if credentials were submitted.
9. Document all findings and additional Indicators of Compromise (IOCs).

## 📝 Conclusion

The simulated email demonstrates several common phishing techniques, including impersonation, domain spoofing, urgency, and potential credential harvesting.

The combination of these indicators makes the email highly suspicious and requires further investigation.

**Investigation Status:** Open

**Severity:** High

**Analyst:** Marisa F. Almeida
