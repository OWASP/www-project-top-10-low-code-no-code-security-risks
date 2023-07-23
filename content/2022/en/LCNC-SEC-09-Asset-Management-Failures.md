---

layout: col-sidebar
title: "LCNC-SEC-09: Asset Management Failures"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 2 |

## The Gist

The purpose of low-code/no-code development is that it makes it easy for anyone to create applications withrelatively low maintenance costs. 
This also unfortunately makesthem prone to abandonment while the apps still remain active. 
Furthermore, internal applications can gain popularity rapidly without addressing business continuity concerns as they scale in usage.

## Business User Description

Keeping a clear inventory of applications in an organization is critical to maintaining a healthy ecosystem. Since LCNC applications can be developed rapidly and with ease, keeping track of what applications exist, how to maintain them, and who “owns” them becomes challenging.  

## Description

The ease of creating new applications, their relatively low maintenance costs, and the fact that they are often managed by SaaS services are all contributing factors. 
This means that the number of active applications in an organization tends to grow rapidly and that popular business applications can often find themselves without an owner.

Furthermore, the viral nature of useful internal business applications within large organizations can result in applications developed by a single business user and being relied on by many users throughout the organization. 
Low-code/no-code development can lack business continuity measures expected from important business applications, for example, having multiple owners, being monitored by IT, or offering an SLA.

## Example Attack Scenarios

### Scenario #1

A developer creates an application that becomes popular as an internal tool. 
The developer leaves the organization or moves to another role. 
Due to an API change, the application breaks, disrupting business. 
IT is not aware of the app and cannot help fix it and maintain productivity.

### Scenario #2

A developer browses through the platform marketplace and explores application templates. 
Each click creates an app with an external-facing URL. 
The user forgets about these apps, even though they might expose business data. 
This scenario is multiplied by the number of developers, resulting in an ever-growing number of stale apps.

## Example Attack & Misuse Scenarios - Business Users

### Scenario #1

A developer builds an automated process to load data from a network location into the financial system to complete order processing. A manager is alerted the process isn't running. The developer is now working for another company and has left no documentation. What should have been a quick fix takes weeks, and results in many thousands of overtime to manually process the transactions. 

### Scenario #2

The security team notices that an account is being used to store multiple records simultaneously by a single user. This pattern indicates one of the vulnerabilities ([LCNC-SEC-01-Account-Impersonation](content/2022/en/LCNC-SEC-01-Account-Impersonation.md)) may have occurred. The security team wants to identify the application and implement a change to record the individual user's actions to their credentials. Due to poor inventory management, IT is unable to identify what application is causing this and therefore unable to enforce an appropriate change. 

### Scenario #3

The Security team is planning a Vulnerability test of all applications.   Due to poor inventory management, several LCNC developed applications are missed during this test. These applications have vulnerabilities that later led to a data breach. This breach should have been prevented if the security team were able to test the application. 


## How to Prevent

- Maintain a comprehensive inventory that lists applications, components, and users
- Remove or disable unused dependencies, unnecessary features, components, files, and documentation

## References

- [3 Ways No-Code Developers Can Shoot Themselves in the Foot](https://www.darkreading.com/dr-tech/3-ways-no-code-developers-can-shoot-themselves-in-the-foot)
- [Why So Many Security Experts Are Concerned About Low-Code/No-Code Apps](https://www.darkreading.com/dr-tech/why-so-many-security-experts-are-concerned-about-low-code-no-code-apps)
- [You Can't Opt Out of Citizen Development](https://www.darkreading.com/edge-articles/you-can-t-opt-out-of-citizen-development)
