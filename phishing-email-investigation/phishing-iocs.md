# Phishing Indicators of Compromise (IOCs)

## 🔎 Purpose

This document identifies and categorizes potential Indicators of Compromise (IOCs) discovered during the simulated phishing email investigation.

IOCs are pieces of information that can help security analysts identify, investigate, and correlate suspicious activity.

## 🚩 Identified IOCs

| IOC Type           | Indicator                              | Description                               | Risk   |
| ------------------ | -------------------------------------- | ----------------------------------------- | ------ |
| Suspicious Domain  | `micros0ft-support.com`                | Look-alike domain impersonating Microsoft | High   |
| Suspicious URL     | `https://micros0ft-support.com/verify` | Potential credential harvesting page      | High   |
| Sender Address     | `security-alert@micros0ft-support.com` | Sender uses the suspicious domain         | High   |
| Target Account     | `employee@example.com`                 | Intended recipient of the phishing email  | Medium |
| Phishing Technique | Urgent account suspension message      | Creates pressure for immediate action     | High   |

## 🧠 IOC Analysis

### Suspicious Domain

**Indicator:**

`micros0ft-support.com`

The domain uses a look-alike spelling designed to resemble a legitimate Microsoft-related domain.

The replacement of the letter **o** with the number **0** is a common technique used in phishing and impersonation attacks.

### Suspicious URL

**Indicator:**

`https://micros0ft-support.com/verify`

The URL is considered suspicious because it directs the user to a domain that does not appear to be an official Microsoft domain.

The URL should not be accessed directly during an investigation.

### Suspicious Sender

**Indicator:**

`security-alert@micros0ft-support.com`

The sender address uses the same suspicious domain and attempts to create the appearance of a legitimate security notification.

## 🛡️ Recommended Detection Actions

A security analyst could use these IOCs to:

1. Search email security logs for the suspicious sender.
2. Search DNS or proxy logs for connections to the suspicious domain.
3. Search endpoint logs for access to the suspicious URL.
4. Determine whether additional users received the same email.
5. Identify users who clicked the suspicious link.
6. Check whether credentials were submitted.
7. Block the suspicious domain if confirmed malicious.
8. Document additional IOCs discovered during the investigation.

## 🚨 Incident Response Considerations

If a user interacted with the phishing email, the security team should determine:

* Whether the link was opened.
* Whether credentials were entered.
* Whether MFA was triggered.
* Whether suspicious authentication activity occurred afterward.
* Whether additional systems or accounts were accessed.

If credentials were compromised, appropriate remediation may include password reset, session/token revocation, and additional account monitoring.

## 📝 Analyst Conclusion

The investigation identified multiple potential Indicators of Compromise associated with the simulated phishing email.

The suspicious domain, URL, sender address, and social engineering techniques should be used to support further investigation and detection activities.

These indicators should be considered **potential IOCs** until additional evidence confirms malicious activity.

**Investigation Status:** Open

**Severity:** High
