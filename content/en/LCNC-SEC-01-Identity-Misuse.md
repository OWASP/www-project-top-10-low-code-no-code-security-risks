# LCNC-SEC-01: Identity Misuse

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| TBD | TBD | TBD | TBD |

## Description

Low-code/no-code applications can be embedded with user identities which are used implicitly by any application user. 
This creates a direct path towards Privilege Escalation, and also allows an attacker to hide behind another user's identity.

App Impersonation

Since low-code/no-code application are often internal business applications, users tend to trust them blindly. 
Attackers can take advantage of this fact to take over accounts and move laterally in an organization by staging seemingly-benign applications to gain access on behalf of users.

## Impact

TBD

## How to Prevent

TBD

## Example Attack Scenarios

Application is embedded with maker credentials, which is implicitly used by any app user
Application uses a mixture of business / personal / vendor identities

App Impersonation

Users trust low code apps by default

### Scenario #1

TBD

### Scenario #2

TBD

## References

TBD