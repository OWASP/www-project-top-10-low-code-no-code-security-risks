# LCNC-SEC-03: Data Leakage and Unexpected Consequences

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## The Gist

No-code/low-code applications often sync data or trigger operations across multiple systems, which creates a path for data to find its way outside the organizational boundary. This means that operations in one system can have unexpected consequences in another.

## Description

No-code/low-code applications are often used to sync data between multiple systems or trigger operations on one system as a result of a change in another.
As data movers, no-code/low-code applications can easily cause data leakage by moving data outside the organizational boundary, to another organization or to a personal account.
As operation triggers, no-code/low-code applications can result in unexpected consequences by implicitly coupling an operation within one system, with a change on another.
Furthermore, multiple applications can be connected to and triggered by a single data source, resulting in chained data movement or operation triggers, which are difficult to predict or fully map.

## Example Attack Scenarios

Ideas to explore (TBD):
- Email forwarding
- Shadow vendors - data moving outside the org boundary
- Several hidden automations chain together two seemingly unrelated systems

### Scenario #1

TBD

### Scenario #2

TBD

## How to Prevent

- Limit platform connectors to an approved services list.
- Limit creation of custom connectors to dedicated personnel.
- Monitor platforms for data flow outside the organizational boundary, including multi-hop paths.

## References

- [Low-Code Security and Business Email Compromise via Email Auto-Forwarding](https://www.zenity.io/blog/low-code-security-and-business-email-compromise-via-email-auto-forwarding/)
- [Hackers Abuse Low-Code Platforms And Turn Them Against Their Owners](https://www.zenity.io/blog/hackers-abuse-low-code-platforms-and-turn-them-against-their-owners/)