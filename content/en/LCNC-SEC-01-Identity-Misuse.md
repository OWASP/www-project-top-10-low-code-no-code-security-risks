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

A maker creates a simple application to view records from a database.
They use their own identity to log into the database, which creates a connection embedded within the application.
Every action performed by users in the app ends up querying the database with the maker's identity.
A malicious user takes advantage of this, and uses the application to view, modify or delete records they should not have access to.
Database logs indicate that all querying were made by a single user, the app maker.

### Scenario #2

A maker creates a business application that allows corporate employees to fill out forms with their information.
To store form responses, the user uses their own personal Gmail account.
Users have no way of knowing that the app is storing their data on the maker's personal account. 

## How to Prevent

- Adhere to the Principal of Least Privilege when provisioning connections to external services.
- Ensure applications use dedicated service account rather than user accounts.
- Ensure applications use a single consistent identity across all of their connections, rather than a different identity for each connection. 

## References

- [Why So Many Security Experts Are Concerned About Low-Code/No-Code Apps](https://www.darkreading.com/dr-tech/why-so-many-security-experts-are-concerned-about-low-code-no-code-apps)