# Phishing Email Investigation

## 🔎 Project Overview

This project simulates the investigation of a suspicious phishing email.

The goal is to identify potential indicators of compromise (IOCs), evaluate the risk of the email, and recommend appropriate security response actions.

## 🎯 Objectives

* Identify signs of phishing.
* Analyze suspicious sender information.
* Identify suspicious URLs and domains.
* Document potential Indicators of Compromise (IOCs).
* Assess the severity and potential impact.
* Recommend appropriate security response actions.

## 📧 Simulated Phishing Email

**From:** Microsoft Security [security-alert@micros0ft-support.com](mailto:security-alert@micros0ft-support.com)

**To:** [employee@example.com](mailto:employee@example.com)

**Subject:** Urgent: Your Account Will Be Suspended

**Date:** September 1, 2026

### Email Message

> Your Microsoft account has been identified as having unusual activity.
>
> To prevent your account from being suspended, please verify your account immediately by clicking the link below.
>
> Verify Your Account:
> `https://micros0ft-support.com/verify`

## 🚩 Initial Findings

Several characteristics of the message appear suspicious:

1. The sender domain uses `micros0ft-support.com`, which resembles a legitimate Microsoft domain but contains a deceptive spelling.
2. The email creates urgency by threatening account suspension.
3. The message asks the recipient to click a link and verify account information.
4. The requested action could potentially be used to steal credentials.

## 🧪 Investigation

### Suspicious Domain

`micros0ft-support.com`

The domain appears suspicious because the word "Microsoft" has been altered by replacing the letter **o** with the number **0**.

This technique is commonly associated with look-alike or typosquatting domains.

### Suspicious URL

`https://micros0ft-support.com/verify`

The URL should not be accessed directly during an investigation.

Instead, analysts should use safe analysis methods and security tools to investigate the domain and URL.

## 🚨 Indicators of Compromise

| IOC Type          | Indicator                              | Reason                          |
| ----------------- | -------------------------------------- | ------------------------------- |
| Suspicious Domain | `micros0ft-support.com`                | Look-alike domain               |
| Suspicious URL    | `https://micros0ft-support.com/verify` | Potential credential harvesting |
| Sender Address    | `security-alert@micros0ft-support.com` | Uses suspicious domain          |

## ⚠️ Risk Assessment

**Severity:** High

The email presents characteristics commonly associated with phishing and potential credential theft.

The combination of a deceptive domain, urgent language, and a request to verify an account creates a significant security risk.

## 🛡️ Recommended Response

1. Do not click the suspicious link.
2. Do not provide credentials or personal information.
3. Report the email to the security team.
4. Block or investigate the suspicious domain.
5. Search security logs for connections to the suspicious domain.
6. Determine whether any users interacted with the email.
7. Reset credentials if a user submitted credentials.
8. Document the incident and any additional IOCs.

## 📝 Analyst Conclusion

The simulated email contains multiple indicators consistent with a phishing attempt.

The suspicious look-alike domain, urgent language, and credential verification request indicate a potential attempt to obtain user credentials.

The email should be treated as a **High Severity** security event until the investigation determines the full scope and impact.

**Investigation Status:** Open
