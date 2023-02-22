---

layout: col-sidebar
title: "LCNC-SEC-07: Vulnerable and Untrusted Components"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 2 | 2 | 2 | 2 |

## The Gist

No-code/low-code applications rely heavily on ready-made components out of the marketplace, the web, or custom connectors built by developers.
These components are often unmanaged, lack visibility, and expose applications to supply chain-based risks. 

## Description

No-code/low-code applications rely heavily on ready-made components from the marketplace or the web, including data connectors, widgets, and sub-services. 
In many cases, entire applications are built by vendors. 
Third-party components and applications are often a target for attackers who wish to compromise a large number of customers.

Moreover, no-code/low-code applications often enable extensibility through custom code. 
These pieces of code are embedded into the application and, in some cases, are not held up to the same level of security vigilance as with other pro-code applications. 

## Example Attack Scenarios

### Scenario #1

Developers across the organization use a vulnerable component from the marketplace.
Every app that uses the component is exposed to exploitation.
Admins can find it difficult to locate apps affected by the vulnerable component.

### Scenario #2

A developer creates a custom connector that allows developers to connect to an internal business API.
The custom connector passes the authentication token on the URL, exposing the authentication secrets to app users.

## How to Prevent

- Remove unused dependencies, unnecessary features, components, files, and documentation.
- Continuously inventory versions of applications and components used by those applications and scan that inventory for deprecated or vulnerable components.
- Limit use to pre-approved marketplace components.
- Monitor for components that are unmaintained or do not create security patches for older versions.

## References

- [No-Code Malware - Windows 11 at Your Service, DEF CON 2022](https://www.youtube.com/watch?v=e8PEIOa6W9M)
- [CVE-2021-44228: Incident Report for Mendix Technology B.V.](https://status.mendix.com/incidents/8j5043my610c)
- [A06:2021 – Vulnerable and Outdated Components, OWASP Top 10](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)