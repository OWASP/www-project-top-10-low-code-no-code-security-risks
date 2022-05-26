# LCNC-SEC-06: Injection Handling Failures

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 2 | 2 | 2 | 2 |

## The Gist

No-code/low-code applications ingest user provided data in multiple ways, including direct input or retrieving user provided content from various services. Such data can contain malicious payloads that may introduce risk to the application.

## Description

No-code/low-code applications ingest user porivded data in multiple ways, including direct input or retrieving user provided content from various services.
Since applications often query data dynamically based on user input, they are exposed to a significant risk of injection-based attacks.
Moreover, since applications can use user provided content in various ways including querying a database, parsing a document and so forth, protection from injection-based attacks must take into account the specific application and its use of user data. 

## Example Attack Scenarios

Coming soon

## How to Prevent

- Sanitize user input, taking into the account the operations that will be performed on that input by the application.
- Educate business users on the risk of unsanitized user input. Platform cannot make this problem go away on their own. 

## References

- [A03:2021 – Injection, OWASP Top 10](https://owasp.org/Top10/A03_2021-Injection/)