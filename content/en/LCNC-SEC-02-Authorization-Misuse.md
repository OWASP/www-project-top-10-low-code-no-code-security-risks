# LCNC-SEC-02: Authorization Misuse

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 3 | 3 | 3 |

## The Gist

Service connections are first-class objects in most no-code/low-code platforms. This means connections between applications, other users, or entire organizations. Applications can also be shared with users who should not have access to their underlying data.

## Description

No-code/low-code applications aren't built in silos. Their impact is based on integrations across the organization's stack through on-premise, SaaS, PaaS, and cloud platforms.
Most no-code/low-code platforms come built-in with a large set of connectors, i.e., wrappers around APIs, which allow quick and easy connectivity.
Connectors and user credentials form connections, which are first-class objects in most no-code/low-code platforms.
This means that connections can be shared among applications, with other users, or with entire organizations.

Many no-code/low-code platforms abuse OAuth authorization flows by querying and storing user refresh tokens and re-using them at will to increase productivity and reduce time-to-deliver.
This allows business users to quickly set up connections without thinking about secrets or permissions; at the same time, connections are embedded with user identities that are difficult to monitor or revoke.
Even though OAuth refresh tokens are designed to be short-lived, they are most frequently valid for a few months or even years. 
Hence, a connection created by a business user in under a minute could persist in the no-code/low-code platform for an extended period and often get used by other users for different purposes than the original intention.

## Example Attack Scenarios

### Scenario #1

A maker creates a connection to their corporate email account.
They inadvertently click the "share with everyone" option.
Every user in the organization, including contractors and vendors, gains access to their corporate email account.
A malicious user triggers a "forgot password" flow and uses the connection to follow through with the process and gain control over the account.

### Scenario #2

A maker creates a simple application to view records from a database.
The application is configured to ensure each user can only view related records.
However, the application is configured in such a way that the underlying database connection is implicitly shared with its user.
An application user can use the database connection directly, gaining full access to all records.

### Scenario #3

Admin connects an application to their source code management system (i.e., BitBucket) using a service account.
The provisioned service account has unrestricted access to all repositories to enable seamless integration.
Any internal user can abuse this connection to access restricted repositories they usually don't have access to.


## How to Prevent

- Disable or monitor the use of implicitly shared connections.
- Adhere to the principle of least privilege when providing access to environments that can contain shared connections.
- Monitor no-code/low-code platforms for over-shared connections.
- Educate business users on the risks of connection sharing and its relation to credential sharing.

## References

- [Low-Code Platforms Are the New Holy Grail for Hackers](https://www.zenity.io/blog/why-are-low-code-platforms-becoming-the-new-holy-grail-of-cyberattackers/)
