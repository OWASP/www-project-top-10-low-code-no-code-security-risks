# LCNC-SEC-10: Security Misconfiguration

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 3 | 3 | 3 |

## Description

Low-code/no-code platforms provide a wide range of features, some of which control the balance between security and support of specific use cases. 
Misconfigurations can often result in anonymous user access to sensitive data or operations, sensitive data leaking to logs, unprotected secrets and oversharing.

broken access control

Instances where public endpoints expose data / operations. 
For example app database exposed or flow trigger available for all.

## Impact

TBD

## How to Prevent

TBD

## Example Attack Scenarios

Turn on audit logs
RBAC
Power Platform requireUserConsent flag

broken access control

Automation trigger is available to anonymous users
Managed database is exposed to anonymous users (Power Platform data leak)

### Scenario #1

TBD

### Scenario #2

TBD

## References

TBD