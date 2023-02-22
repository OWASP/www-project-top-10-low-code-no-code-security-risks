---

layout: col-sidebar
title: "LCNC-SEC-04: Authentication and Secure Communication Failures"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 2 | 3 | 2 | 2 |

## The Gist

No-code/low-code applications typically connect to business-critical data via connections set up by business users, which can often result in insecure communication.

## Description

No-code/low-code applications typically connect to business-critical data across on-premise, Saas, PaaS, and cloud platforms.
Applications use built-in connectors, which allow easy connections to various services. Connections offer a variety of security configurations, including communication protocols, authentication flows, and types of credentials used. In many cases, business users set up connections, which can often result in deviation from best practices and corporate data security policies.


## Example Attack Scenarios

### Scenario #1

A developer creates an app that uses an FTP connection and doesn't check the box that turns on encryption.
Users of the app have no way to know that their data is being transferred unencrypted since the communication between the app and its users is encrypted.

### Scenario #2

A developer uses admin credentials to create a database connection.
They build an application that uses that connection to show data to its users.
Even though they intended to allow read-only operations through the app, users can use the over-privileged connection to write or delete records from the database.

## How to Prevent

- In production environments, limit the creation of connections to dedicated personnel.
- Monitor platforms for connections that do not comply with best practices.
- Educate business users on the risks of insecure communication and the need to involve security teams when setting them up.

## References

- [The CISO View: Protecting Privileged Access in RPA](https://www.cyberark.com/resources/blog/ciso-view-insights-securely-scaling-rpa-initiatives)