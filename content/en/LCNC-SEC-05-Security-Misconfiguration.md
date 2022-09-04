# LCNC-SEC-05: Security Misconfiguration

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## The Gist

Misconfigurations can often result in anonymous access to sensitive data or operations, unprotected public endpoints, secrets, and oversharing.

## Description

No-code/low-code platforms provide a wide range of features, some of which control the balance between security and support of specific use cases. 
Misconfigurations can often result in anonymous user access to sensitive data or operations, unprotected public endpoints, secrets, and oversharing.
Furthermore, many configurations are set on the application level rather than the tenant level, meaning they can be set by business users rather than administrators.

## Example Attack Scenarios

### Scenario #1

A developer creates an application that exposes an API endpoint and fails to configure that endpoint to deny anonymous access.
Attackers scan the low-code/no-code platform's subdomains, locate the app and steal its underlying data.

### Scenario #2

A developer creates automation triggered by a webhook but fails to protect that webhook with a secret.
Attackers identify the webhook and can now trigger the automation at will.
The automation could be modifying or deleting data.

## How to Prevent

- Read vendor documentation and follow best practices guides.
- Ensure configurations align with industry best practices.
- Monitor configuration for drifts.
- Implement a change management system for tenant-level configuration.

## References

- [By Design: How Default Permissions on Microsoft Power Apps Exposed Millions](https://www.upguard.com/breaches/power-apps)
- [Microsoft Internal Security Best Practices: Secure Power Platform Development](https://www.youtube.com/watch?v=h9FrOEfc81s)
- [Power Platform Landing Zones Reference Implementation](https://github.com/microsoft/industry/blob/main/foundations/powerPlatform/referenceImplementation/readme.md#power-platform-landing-zones-reference-implementation)