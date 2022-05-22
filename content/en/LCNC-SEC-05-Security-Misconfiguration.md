# LCNC-SEC-05: Security Misconfiguration

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## The Gist

Misconfigurations can often result in anonymous user access to sensitive data or operations, unprotected public endpoints, unprotected secrets and oversharing.

## Description

No-code/low-code platforms provide a wide range of features, some of which control the balance between security and support of specific use cases. 
Misconfigurations can often result in anonymous user access to sensitive data or operations, unprotected public endpoints, unprotected secrets and oversharing.
Furthermore, many configurations are set on the application-level rather than the tenant-level, which means that they can be set by business users rather than admins.

## Example Attack Scenarios

Ideas to explore (TBD):
- Turn on audit logs
- RBAC
- Power Platform requireUserConsent flag
- broken access control
  - Automation trigger is available to anonymous users
  - Managed database is exposed to anonymous users (Power Platform data leak)

### Scenario #1

TBD

### Scenario #2

TBD

## How to Prevent

- Read vendor documentation and best practice.
- Ensure configurations align with industry best practice.
- Monitor configuration for drifts.
- Implement a change management system for tenant-level configuration.

## References

- [By Design: How Default Permissions on Microsoft Power Apps Exposed Millions](https://www.upguard.com/breaches/power-apps)
- [Microsoft Internal Security Best Practices: Secure Power Platform Development](https://www.youtube.com/watch?v=h9FrOEfc81s)
- [Power Platform Landing Zones Reference Implementation](https://github.com/microsoft/industry/blob/main/foundations/powerPlatform/referenceImplementation/readme.md#power-platform-landing-zones-reference-implementation)