# LCNC-SEC-01: Account Impersonation

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## The Gist

No-code/Low-code applications can be embedded with user identities which are used implicitly by any application user. 
This creates a direct path towards Privilege Escalation, allows an attacker to hide behind another user's identity, and circumvents traditional security controls.

## Description

No-code/low-code applications can take advantage of existing user identities rather than having their own application identity.
Embedded identities can belong to the application creator, or they could be a common identity shared by teams, such as database credentials.

The lack of application identity exposes sensitive data to monitoring systems outside the no-code/low-code platform.
As an outside viewer, any user that uses the application is impersonating the application's creator, and there is no way to distinguish between the application and its creator.
The problem becomes even more acute when applications use different identities to operate on various platforms. In such a case, one user could be used to store files on a file-sharing SaaS and another user to retrieve on-premise data.

Furthermore, identities are embedded within the application, and multiple users can use that application. This creates a direct path to privilege escalation, where application users can gain access levels they should not typically have.

## Example Attack Scenarios

### Scenario #1

A maker creates a simple application to view records from a database.
They use their identity to log into the database, creating a connection embedded within the application.
Every action users perform in the app ends up querying the database with the maker's identity.
A malicious user takes advantage of this and uses the application to view, modify or delete records they should not have access to.
Database logs indicate that all queries were made by a single user, the app maker.

### Scenario #2

A maker creates a business application that allows corporate employees to fill out forms with their information.
To store form responses, the creator uses their personal email account.
Users have no way of knowing that the app is storing their data on the maker's personal account.

### Scenario #3

A maker creates a business application and shares it with an admin.
The maker configures the app to use its user's identity.
Aside from its stated purpose, the app also uses its user's identity to elevate the privileges of the maker.
Once the admin uses the app, they inadvertently elevate the maker's privileges. 

## How to Prevent

- Adhere to the principle of least privilege when provisioning connections to external services.
- Ensure applications use dedicated service accounts rather than user accounts.
- Ensure applications use a single consistent identity across all their connections, rather than a different identity for each. 
- Ensure a proper audit trail is maintained to identify the actor behind actions performed through the shared connection.

## References

- [Why So Many Security Experts Are Concerned About Low-Code/No-Code Apps](https://www.darkreading.com/dr-tech/why-so-many-security-experts-are-concerned-about-low-code-no-code-apps)