# LCNC-SEC-07: Vulnerable, Unmanaged and Untrusted Components

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| TBD | TBD | TBD | TBD |

## The Gist

No-code/low-code applications heavily rely on ready-made components out of the marketplace, the web or custom connectors built by developers.
These component are often unmanaged, lack visibility and expose applications to supply chain-based risks. 

## Description

No-code/low-code applications heavily rely on ready-made components out of the marketplace or the web, including data connectors, widgets and sub-services. 
In many cases, entire applications are built by vendors. 
Third-party components and applications are often a target for attackers who wish to compromise a large number of customers.

Moreover, no-code/low-code applications often enable extendability through custom code. 
These pieces of code are embedded into the application, and in some cases are not held up to the same level of security vigilance as with other pro-code applications. 

## Impact

TBD

## Example Attack Scenarios

Ideas to explore (TBD):
- Log4J through marketplace components
- Custom connectors or custom code
- Using Open Source components with no review

### Scenario #1

TBD

### Scenario #2

TBD

## How to Prevent

- Remove unused dependencies, unnecessary features, components, files, and documentation.
- Continuously inventory versions of applications and components used by those applications, and scan that inventory for deprecated or vulnerable components.
- Limit use to pre-approved marketplace components.
- Monitor for components that are unmaintained or do not create security patches for older versions.

## References

- [CVE-2021-44228: Incident Report for Mendix Technology B.V.](https://status.mendix.com/incidents/8j5043my610c)
- [A06:2021 – Vulnerable and Outdated Components, OWASP Top 10](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)