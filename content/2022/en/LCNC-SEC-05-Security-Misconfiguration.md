---

layout: col-sidebar
title: "LCNC-SEC-05: Security Misconfiguration"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## The Gist

Misconfigurations can often result in security risks like anonymous access to sensitive data or operations, unprotected public endpoints and secrets, and oversharing.

## Business User Description

In building a solution, platforms provide a variety of features, each having an impact on security. They can range from how/where sensitive data is stored, encryption settings, and more. Users need to consider productivity vs risk when making the right choices to combine these features.

## Description

Low-code/no-code development platforms provide a wide range of features, some of which control the balance between security and support of specific use cases. 
However, misconfigurations can often result in anonymous user access to sensitive data or operations, unprotected public endpoints, secrets, and oversharing. 
Furthermore, many configurations are set on the application level rather than the tenant level, meaning they can be set by business users themselves, rather than administrators.

## Example Attack Scenarios

### Scenario #1

A developer creates an application that exposes an API endpoint and fails to configure that endpoint to deny anonymous access. 
Attackers scan the low-code/no-code platform’s subdomains, locate the app, and steal its underlying data.

### Scenario #2

A developer creates an automation that is triggered by a webhook, but fails to protect that webhook with a secret. 
Attackers identify the webhook and can now trigger the automation at will. 
The automation could be used to modify or delete data.

## Example Attack & Misuse Scenarios - Business Users

### Scenario #1

A new application is built that requires a password to be set by a user. The “rules” configured for this new application are less secure than the company's password policy. The less secure password makes it easier for a malicious user to guess the users password and access the system. 

### Scenario #2

An application is created that allows users to upload documents to a server. The upload process has not been configured to scan the document upon upload for security risks. A malicious user uses this process to upload a document containing malware that then locks all computers in the company unless a payment is made (ransomware).

## How to Prevent

- Read low-code/no-code platform vendor documentation and follow best practices guides
- Ensure configurations align with industry best practices
- Monitor configuration for drifts
- Implement a change management system for tenant-level configuration

## References

- [By Design: How Default Permissions on Microsoft Power Apps Exposed Millions](https://www.upguard.com/breaches/power-apps)
- [Microsoft Internal Security Best Practices: Secure Power Platform Development](https://www.youtube.com/watch?v=h9FrOEfc81s)
- [Power Platform Landing Zones Reference Implementation](https://github.com/microsoft/industry/blob/main/foundations/powerPlatform/referenceImplementation/readme.md#power-platform-landing-zones-reference-implementation)
