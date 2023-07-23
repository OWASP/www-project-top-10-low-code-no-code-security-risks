---

layout: col-sidebar
title: "LCNC-SEC-04: Authentication and Secure Communication Failures"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 2 | 3 | 2 | 2 |

## The Gist

Low-code/no-code development typically interacts with business-critical data via connections set up by business users, which can often result in insecure communications.

## Business User Description

Many applications need to access data and/or move data to fulfill their design.  When the connection to access or move the data is created, “improper” settings can lead to the data being intercepted, blocked, or users having over-privileged access to data, services and more.

## Description

Low-code/no-code development typically connects to business-critical data across on-premise, Saas, PaaS, and cloud platforms. 
Applications use built-in connectors, which allow for easy connections to various services. 
Connections offer a variety of security configurations, including communication protocols, authentication flows, and types of credentials used. 
In many cases, business users set up connections that often result in deviations from best practices and corporate data security policies.

## Example Attack Scenarios

### Scenario #1

A developer creates an application that uses an FTP connection but doesn’t check the box that turns on encryption. 
Users of that app have no way to know that their data is being transferred unencrypted since the communication between the app and its users is encrypted.

### Scenario #2

A developer uses administrator credentials to create a database connection. 
They build an application that uses that connection to show data to its users. Even though they intended to allow read-only operations through the app, users can use the over-privileged connection to write or delete records from the database.

## Example Attack & Misuse Scenarios - Business Users

### Scenario #1

An application is created to accept payments from users through a website, which sends credit card details to a credit card processor for processing. When sending the data to the credit card processor, the data is not encrypted.  

A malicious user is intercepting the web traffic, and since the data is not encrypted, they can read all of the data, including the credit card information.


## How to Prevent

- In production environments, limit the creation of connections to dedicated personnel
- Monitor platforms for connections that do not comply with best practices
- Educate business users on the risks of insecure communication and the need to involve security teams when setting them up

## References

- [The CISO View: Protecting Privileged Access in RPA](https://www.cyberark.com/resources/blog/ciso-view-insights-securely-scaling-rpa-initiatives)
