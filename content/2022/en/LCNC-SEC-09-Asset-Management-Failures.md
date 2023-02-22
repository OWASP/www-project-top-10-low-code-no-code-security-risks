---

layout: col-sidebar
title: "LCNC-SEC-09: Asset Management Failures"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 2 |

## The Gist

No-code/low-code applications are easy to create and have relatively low maintenance costs, making them prone to abandonment while remaining active.
Furthermore, internal applications can gain popularity rapidly without addressing business continuity concerns.

## Description

No-code/low-code applications are prone to abandonment while remaining active.
The ease of creating new applications, their relatively low maintenance costs, and the fact that they are often managed by SaaS services are all contributing factors. 
This means that the number of active applications in an organization tends to grow rapidly and that popular business applications can often find themselves without an owner.

Furthermore, the viral nature of useful internal business applications within large organizations can result in applications developed by a single business user and being relied on by many users throughout the organization.
No-code/low-code applications can lack business continuity measures expected from important business applications, for example, having multiple owners, being monitored by IT, or offering an SLA.

## Example Attack Scenarios

### Scenario #1

A developer creates an application that becomes popular as an internal tool.
The developer leaves the organization or moves to another role.
Due to an API change, the application breaks, disrupting business.
IT is not aware of the app and cannot help fix it.

### Scenario #2

A developer browses through the platform marketplace and explores app templates.
Each click creates an app with an external-facing URL.
The user forgets about these apps, even though they might expose business data.
This scenario is multiplied by the number of developers, resulting in an ever-growing number of stale apps.

## How to Prevent

- Maintain a comprehensive inventory that lists applications, components, and users.
- Remove or disable unused dependencies, unnecessary features, components, files, and documentation.

## References

- [Why So Many Security Experts Are Concerned About Low-Code/No-Code Apps](https://www.darkreading.com/dr-tech/why-so-many-security-experts-are-concerned-about-low-code-no-code-apps)