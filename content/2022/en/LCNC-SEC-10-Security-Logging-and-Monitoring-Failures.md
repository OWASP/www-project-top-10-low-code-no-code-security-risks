---

layout: col-sidebar
title: "LCNC-SEC-10: Security Logging and Monitoring Failures"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 2 | 2 | 3 | 2 |

## The Gist

Low-code/no-code applications often lack a comprehensive audit trail, produce insufficient or non-existent logs, or overshare access to sensitive logs.

## Business User Description

When an application runs, it’s critical to know what ran and the actions it or a user took (also known as an audit trail). This is often done using logging of specific actions. In case of a breach or malicious activity, the audit log is key to understanding what happened and how to recover. This risk occurs when running systems log too much or too little information, which needs to be balanced with cost and quality of information.

## Description

Low-code/no-code applications often rely on vendors to generate logs and monitoring data.
In many cases, logs are either insufficient or not being collected, which impedes security investigations and can lead to a failed audit stemming from compliance requirements.

Furthermore, individual resources often lack a comprehensive audit trail, preventing change management processes and inquiries.
Finding out who introduced a change becomes an intractable challenge.

## Example Attack Scenarios

### Scenario #1

Application logs are turned off.
When a breach attempt occurs, security teams are unable to determine who accessed the app and what they tried to do. 

### Scenario #2

A business-critical application stops functioning following a change.
Since multiple changes have occurred, each resulting in an application update, it is challenging to find which developer introduced the particular change that caused the issue.
Developers have to review each application version manually to locate the problematic version.
Since each application "save" translates to an update, the number of updates would make a manual process prohibitively expensive and time-consuming.
On some platforms, developers can only review the application's current version, so they won't be able to find or revert to a stable version.

## Example Attack & Misuse Scenarios - Business Users

### Scenario #1

A developer builds an automated process to load data into a financial system to complete order processing. The process handles around one thousand transactions per week with a 97% success rate. The 3% that fail are processed manually off of a daily Failed Transaction email.  

The Failed Transaction email fails to get sent for a few days before its absence is noticed. Due to poor logging there is no easy way to find the failed records. Instead 100% of all transactions have to be investigated to find the failures, resulting in a significantly larger task. 

### Scenario #2

An application to process credit card payments at a conference is created.   As part of its creation, a detailed log file is created to track the transactions and stored on a shared network drive. The logging includes records of the credit card details. A user browsing the network drive discovers this file and is able to obtain all of the credit card data. 

## How to Prevent

- Leverage platform built-in capabilities to collect user access and platform audit logs
- Where applicable, instrument applications with logging mechanisms to provide extra visibility
- Ensure logs are not contaminated with sensitive data by configuring the platform to avoid logging raw application data

## References

- [No-Code Malware - Windows 11 at Your Service, DEF CON 2022](https://www.youtube.com/watch?v=e8PEIOa6W9M)
- [Full Operational Shutdown—another cybercrime case from the Microsoft Detection and Response Team](https://www.microsoft.com/en-us/security/blog/2020/04/02/full-operational-shutdown-another-cybercrime-case-microsoft-detection-and-response-team/)
- [A08:2021 – Software and Data Integrity Failures, OWASP Top 10](https://owasp.org/Top10/A08_2021-Software_and_Data_Integrity_Failures/)
