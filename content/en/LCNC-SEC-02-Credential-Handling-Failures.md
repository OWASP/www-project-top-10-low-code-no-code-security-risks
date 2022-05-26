# LCNC-SEC-02: Credential Handling Failures

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 3 | 3 | 3 |

## The Gist

Service connections are first class objects in most no-code/low-code platforms. This means they can be shared between applications, with other users or with entire organizations.

## Description

No-code/low-code applications are not built in silos. Their impact is based on integrations across the organization's stack, through on-premise, SaaS, PaaS and cloud platforms.
Most no-code/low-code platforms come built in with a large set of connectors, i.e. wrappers around APIs, which allow quick and easy connectivity.
Connectors coupled with user credentials form connections, which are first class objects in most no-code/low-code platforms.
This means that connections can be shared among applications, with other users or with entire organizations.

To increase productivity and reduce time-to-deliver, many no-code/low-code platforms abuse OAuth authorization flows by querying and storing user refresh tokens, and re-using them at will.
This allows business users to quickly set up connections without thinking about secrets or permissions, at the same time, connections are embedded with user identities that are difficult to monitor or revoke.
Even through OAuth refresh tokens are designed to be short-lived, they are most frequently valid for a few months or even years. Hence, a connection created by a business user in under a minute could persist in the no-code/low-code platform for a long period of time, and often get used by other users for different purposes than the original intention.

## Example Attack Scenarios

Ideas to explore (TBD):
- Shared connections enable PrivEsc
- Shared connection lead to account takeover (e.g. "forgot password")
- Default settings encourage users to share their credentials with everyone

### Scenario #1

TBD

### Scenario #2

TBD

## How to Prevent

- Disable or monitor the use of implicitly shared connections.
- Adhere to the principal of least privilege when providing access to environments that can contained shared connections.
- Monitor no-code/low-code platforms for over-shared connections.
- Educate business users on the risks of connection sharing and its relation to credential sharing.

## References

- [Low-Code Platforms Are the New Holy Grail for Hackers](https://www.zenity.io/blog/why-are-low-code-platforms-becoming-the-new-holy-grail-of-cyberattackers/)