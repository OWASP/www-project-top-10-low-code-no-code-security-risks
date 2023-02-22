---

layout: col-sidebar
title: "LCNC-SEC-01: Account Impersonation"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## The Gist

No-code/Low-code applications can be embedded with a developer account which is used implicitly by any application user. 
This creates a direct path towards Privilege Escalation, allows an attacker to hide behind another user's identity, and circumvents traditional security controls.

## Description

Identities are embedded within the application, and multiple users can use that application.
This creates a direct path to privilege escalation, where application users can gain access levels they should not typically have.

No-code/low-code applications can take advantage of embedded user accounts rather than having their own application identity.
Embedded identities can belong to the application creator, or they could be a common identity shared by teams, such as database credentials. They could also be service account or shared identities.

The lack of application identity makes hides the application's existence from monitoring systems outside the no-code/low-code platform.
As an outside viewer, any user that uses the application is impersonating the application's creator, and there is no way to distinguish between the application and its creator.
The problem becomes even more acute when applications use different identities to operate on various platforms.
In such a case, one user could be used to store files on a file-sharing SaaS and another user to retrieve on-premise data.

## Example Attack Scenarios

### Scenario #1

A developer creates a simple application to view records from a database.
They use their identity to log into the database, creating a connection embedded within the application.
Every action users perform in the application ends up querying the database with the developer's identity.
A malicious user takes advantage of this and uses the application to view, modify or delete records they should not have access to.
Database logs indicate that all queries were made by a single user, the app developer.

### Scenario #2

A developer creates a business application that allows corporate employees to fill out forms with their information.
To store form responses, the developer uses their personal email account.
Users have no way of knowing that the app is storing their data on the developer's personal account.

### Scenario #3

A developer creates a business application and shares it with an admin.
The developer configures the app to use its user's identity.
Aside from its stated purpose, the app also uses its user's identity to elevate the privileges of the developer.
Once the admin uses the app, they inadvertently elevate the developer's privileges. 

## How to Prevent

- Adhere to the principle of least privilege when provisioning connections to databases/services/SaaS.
- Ensure applications use dedicated service or application accounts rather than user accounts.
- Ensure applications use a single consistent identity across all their connections, rather than a different identity for each. Use a dedicated service or application account for those connections.
- Ensure a proper audit trail is maintained to identify the actor behind actions performed through the shared connection, whether those connections are shared by virtue of users using the application or by granting users access to that connection directly.

## References

- [Low Code High Risk - Enterprise Domination via Low Code Abuse, DEF CON 2022](https://www.youtube.com/watch?v=D3A62Rzozq4)
- [Watch Out for User Impersonation in Low-Code/No-Code Apps](https://www.darkreading.com/edge-articles/watch-out-for-user-impersonation-in-low-code-no-code-apps)
- [Do low-code / no-code platforms pose a security risk?](https://sdtimes.com/lowcode/do-low-code-no-code-platforms-pose-a-security-risk/)
- [Credential Sharing as a Service: The Hidden Risk of Low-Code/No-Code](https://www.darkreading.com/dr-tech/credential-sharing-as-a-service-hidden-risk-of-low-code-no-code)
