---

layout: col-sidebar
title: "LCNC-SEC-07: Vulnerable and Untrusted Components"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 2 | 2 | 2 | 2 |

To accelerate building a solution, many LCNC platforms have the equivalent of an “app store” where a developer can use pre-made parts of a solution created by third parties. These pre-made components can come with any of the risks below, as well as being created with malicious intent. 

## The Gist

Low-code/no-code development relies heavily on ready-made components out of marketplaces, the web, or custom connectors built by developers. 
These components are often unmanaged, lack visibility, and expose organizations to supply chain-based risks.

## Description

In many cases, entire applications are built by vendors leveraging pre-built components, data connectors, widgets, and sub-services. 
Third-party components and applications are often a target for attackers who wish to compromise a large number of customers.

Moreover, low-code/no-code development often enables extensibility through custom code. 
These pieces of code are embedded into the application and, in some cases, are not held up to the same level of security vigilance as with other profesionally developed applications.

## Example Attack Scenarios

### Scenario #1

Developers across an organization use a vulnerable component from the marketplace. 
Every app that uses the component is exposed to exploitation. Admins can find it difficult to locate apps affected by the vulnerable component.

### Scenario #2

A developer creates a custom connector that allows developers to connect to an internal business API. 
The custom connector passes the authentication token on the URL, exposing the authentication secrets to app users.

## Example Attack & Misuse Scenarios - Business Users

### Scenario #1

A user is building an application that connects to their human resources systems to update salary information. The user finds a third party created “connector” to add to their HR system that greatly simplifies their task. The connector was created without properly securing the transmission ([LCNC-SEC-04-Authentication-and-Secure-Communication-Failures](content/2022/en/LCNC-SEC-04-Authentication-and-Secure-Communication-Failures.md)), allowing a malicious user to view the data in-transit. The malicious user is able to use this to obtain and publicly publish the salaries of all employees.  

### Scenario #2

A user builds a tablet based application to allow sales to be processed at a conference. They find a component that processes credit card data and decides to add it to their solution. The component was maliciously designed to send the credit card data to its creator. As a result, all of the conference users who purchased products had their credit card data stolen. 

### Scenario #3

A new application has been created using a third party component for login.  The third party component comes with default credentials of admin/admin, which is publicly documented. The developer is unaware of this default setting and does not change it. A malicious user is able to access the application using these default settings, leading to unauthorized access to the application.

## How to Prevent

- Remove unused dependencies, unnecessary features, components, and files
- Continuously inventory versions of applications and components used by those applications and scan that inventory for deprecated or vulnerable components
- Limit use to pre-approved marketplace components
- Monitor for components that are unmaintained or do not create security patches for older versions

## References

- [No-Code Malware - Windows 11 at Your Service, DEF CON 2022](https://www.youtube.com/watch?v=e8PEIOa6W9M)
- [CVE-2021-44228: Incident Report for Mendix Technology B.V.](https://status.mendix.com/incidents/8j5043my610c)
- [A06:2021 – Vulnerable and Outdated Components, OWASP Top 10](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)
