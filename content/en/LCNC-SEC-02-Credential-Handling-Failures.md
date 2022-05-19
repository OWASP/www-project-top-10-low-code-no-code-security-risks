# LCNC-SEC-02: Credential Handling Failures

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 3 | 3 | 3 |

## Description

Service connections are first class citizens in most low-code/no-code platforms, which means they can be shared between applications, with other users or become stale.

App Impersonation

Since low-code/no-code application are often internal business applications, users tend to trust them blindly. 
Attackers can take advantage of this fact to take over accounts and move laterally in an organization by staging seemingly-benign applications to gain access on behalf of users.


## Impact

TBD

## How to Prevent

TBD

## Example Attack Scenarios

Shared connections enable PrivEsc
Shared connection lead to account takeover (e.g. "forgot password")
Default settings encourage users to share their credentials with everyone

App Impersonation

Users trust low code apps by default

### Scenario #1

TBD

### Scenario #2

TBD

## References

TBD