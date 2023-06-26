---

layout: col-sidebar
title: "LCNC-SEC-03: Data Leakage and Unexpected Consequences"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## The Gist

Low-code/no-code development legitimately accesses data from underlying services but can also serve as a conduit to those backend systems for actions that were not anticipated or approved of. 
This includes unintended negative side effects such as data leakage beyond the application/security boundary, triggering create/read/update/delete operations on the data, and accidental/malicious data exfiltration.

## Description

Low-code/no-code development often accesses data or performs operations on underlying services. 
As data operators, low-code/no-code applications can easily cause data leakage by moving data outside its designated storage or even the organizational boundary.

In some cases, low-code/no-code development can be used to sync data between multiple systems or trigger operations on one system due to a change in another. 
As operation triggers, these resources can result in unexpected consequences by implicitly coupling an operation within one system with a change in another. 
Furthermore, multiple applications can be connected to and triggered by a single data source, resulting in chained data movement or operation triggers, which are difficult to predict or fully map.

## Example Attack Scenarios

### Scenario #1

A developer grants an application that was built using low-code/no-code access to a corporate database. 
The application is shared with other users, granting them implicit access to the database without going through an approval or access request process.

### Scenario #2

A developer configures an automation that triggers each time they receive an email in their corporate mailbox. 
The automation sends a new email to the developer’s personal email account, copying the recipients, subject, and body from the original email received in the corporate mailbox. 
Since data is copied to a separate mailbox rather than emails being forwarded from the corporate mailbox, the automation bypasses DLP controls.

### Scenario #3

A developer builds an automation that syncs changes between two SharePoint sites, so every new file on site A is copied to site B. 
A business user accidentally writes a sensitive document to site A, not knowing that it is replicated to site B. 
Even if the business user deletes the document from site A, the document is still available on site B.

## How to Prevent

- Limit connectors to an approved services list
- Limit creation of custom connectors to dedicated personnel
- Monitor platforms for data flow outside the organizational boundary, including multi-hop paths

## References

- [3 Ways No-Code Developers Can Shoot Themselves in the Foot](https://www.darkreading.com/dr-tech/3-ways-no-code-developers-can-shoot-themselves-in-the-foot)
- [Low-Code Security and Business Email Compromise via Email Auto-Forwarding](https://www.zenity.io/blog/low-code-security-and-business-email-compromise-via-email-auto-forwarding/)
- [Hackers Abuse Low-Code Platforms And Turn Them Against Their Owners](https://www.zenity.io/blog/hackers-abuse-low-code-platforms-and-turn-them-against-their-owners/)
- [Full Operational Shutdown—another cybercrime case from the Microsoft Detection and Response Team](https://www.microsoft.com/en-us/security/blog/2020/04/02/full-operational-shutdown-another-cybercrime-case-microsoft-detection-and-response-team/)
