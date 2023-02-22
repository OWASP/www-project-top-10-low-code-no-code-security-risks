---

layout: col-sidebar
title: "LCNC-SEC-10: Security Logging and Monitoring Failures"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 2 | 2 | 3 | 2 |

## The Gist

No-code/low-code applications often lack a comprehensive audit trail, produce none or insufficient logs, or overshare access to sensitive logs.

## Description

No-code/low-code applications often rely on vendors to generate logs and monitoring data.
In many cases, logs are either insufficient or not being collected, impeding security investigations and failing to satisfy compliance requirements.

Furthermore, applications often lack a comprehensive audit trail, preventing change management processes and inquiries.
Finding out who introduced a change becomes an intractable challenge.

## Example Attack Scenarios

### Scenario #1

App logs are turned off.
When a breach attempt occurs, security teams are unable to determine who accessed the app and what did they try to do. 

### Scenario #2

A business-critical application stops functioning following a change.
Since multiple changes have occurred, each resulting in an application update, it is challenging to find which developer has introduced the particular change that caused the issue.
Developers would have to review each application version manually to locate the problematic version.
Since every application "save" translates to an update, the number of updates would make a manual process prohibitively expensive.
On some platforms, developers can only review the application's current version, so they won't be able to find or revert to a stable version.

## How to Prevent

- Leverage platform built-in capabilities to collect user access and platform audit logs.
- Where applicable, instrument applications with logging mechanisms to provide extra visibility.
- Ensure logs are not contaminated with sensitive data by configuring the platform to avoid logging raw application data.

## References

- [Full Operational Shutdown—another cybercrime case from the Microsoft Detection and Response Team](https://www.microsoft.com/en-us/security/blog/2020/04/02/full-operational-shutdown-another-cybercrime-case-microsoft-detection-and-response-team/)
- [A08:2021 – Software and Data Integrity Failures, OWASP Top 10](https://owasp.org/Top10/A08_2021-Software_and_Data_Integrity_Failures/)