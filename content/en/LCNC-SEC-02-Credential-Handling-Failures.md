# LCNC-SEC-02: Credential Handling Failures

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 3 | 3 | 3 |

## The Gist

Service connections are first class objects in most no-code/low-code platforms, which means they can be shared between applications, with other users or with entire organizations.

## Description

No-code/low-code applications are not built in silo.
Their impact is based on integration across the organization stack, through on-prem, SaaS, PaaS and cloud.
Most no-code/low-code platforms come built in with a large set of connectors, i.e. wrappers around APIs, which allow quick and easy connectivity.
Connectors coupled with user credentials form connections, which are first class objects in most no-code/low-code platforms.
This means that connections be shared between applications, with other users or with entire organizations.

To increase productivity and reduce time-to-deliver, many no-code/low-code platforms abuse OAuth authorization flows by querying and storing user refresh tokens, and reusing them at will.
This allows business users to quickly set up connections without thinking about secrets or permissions, but it means that connections are embedded with user identities that are difficult to monitor or revoke.
Even through OAuth refresh tokens are designed to be short-lived, they are most frequently valid for a few months or even years.
Hence, a connection created by a business user in under a minute could persist in the no-code/low-code platform for a large amount of time, and often get use by other users for different purpose than the original intention.

## Example Attack Scenarios

Ideas to explore (TBD):
- Shared connections enable PrivEsc
- Shared connection lead to account takeover (e.g. "forgot password")
- Default settings encourage users to share their credentials with everyone

### Scenario #1

A maker creates a connection to their corporate email account.
They inadvertently click the "share with everyone" option.
Every user the in organization, including contractors and vendors, gains access to their corporate email account.
A malicious user triggers a "forgot password" flow and uses the connection to follow through with the process and gain control over the account.

### Scenario #2

A maker creates a simple application to view records from a database.
The application has configured permissions to make sure each user can only view records related to them.
However, the application is set up in a way such that the underlying database connection is implicitly shared with its user.
An application user can use the database connection directly, gaining full access to all records.

## How to Prevent

- Disable or monitor for use of implicitly shared connections.
- Adhere to the Principal of Least Privilege when providing access to environments that can contained shared connections.
- Monitor no-code/low-code platforms for over-shared connections.
- Educate business users on the risks of connection sharing and its relation to credential sharing.

## References

- [Low-Code Platforms Are the New Holy Grail for Hackers](https://www.zenity.io/blog/why-are-low-code-platforms-becoming-the-new-holy-grail-of-cyberattackers/)