# LCNC-SEC-01: Identity Misuse

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## The Gist

No-code/Low-code applications can be embedded with user identities which are used implicitly by any application user. 
This creates a direct path towards Privilege Escalation, allows an attacker to hide behind another user's identity, and circumvents traditional security controls.

## Description

No-code/low-code applications can take advantage of existing user identity rather than having their own application identity.
Embedded identities can be that of the application creator, or a common identity shared by teams such as credentials to a database.

The lack of application identity results an application being transparent to any enforcing or monitoring systems outside the no-code/low-code platform.
As an outside viewer, any user that uses the application is impersonating the application creator.
There is no way to distinguish the application and its creator.
The problem becomes even more acute when applications use multiple identities to operate on multiple different platforms.
One user could be used to store files on a file sharing SaaS, another to retrieve on-prem data.

Furthermore, identities are embedded within the application, and that application can be used by multiple users.
This creates a direct path to privilege escalation, where application users can gain access they should not have.

## Example Attack Scenarios

Ideas to explore (TBD):
- Application is embedded with maker credentials, which is implicitly used by any app user
- Application uses a mixture of business / personal / vendor identities
- App Impersonation: Users trust low code apps by default

### Scenario #1

TBD

### Scenario #2

TBD

## How to Prevent

- Adhere to the Principal of Least Privilege when provisioning connections to external services.
- Ensure applications use dedicated service account rather than user accounts.
- Ensure applications use a single consistent identity across all of their connections, rather than a different identity for each connection. 

## References

TBD