# LCNC-SEC-01: Identity Misuse

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

The lack of application identity results in sensitive data exposure to any monitoring systems outside the no-code/low-code platform.
As an outside viewer, any user that uses the application is impersonating the application's creator, and there is no way to distinguish between the application and its creator.
The problem becomes even more acute when applications use multiple identities to operate on multiple different platforms. In such a case, one user could be used to store files on a file sharing SaaS, and another user to retrieve on-premise data.

Furthermore, identities are embedded within the application, and that application can be used by multiple users. This creates a direct path to privilege escalation, where application users can gain access levels they should not normally have.

## Example Attack Scenarios

Coming soon

## How to Prevent

- Adhere to the principal of least privilege when provisioning connections to external services.
- Ensure applications use dedicated service accounts rather than user accounts.
- Ensure applications use a single consistent identity across all of their connections, rather than a different identity for each connection. 

## References

- [Why So Many Security Experts Are Concerned About Low-Code/No-Code Apps](https://www.darkreading.com/dr-tech/why-so-many-security-experts-are-concerned-about-low-code-no-code-apps)