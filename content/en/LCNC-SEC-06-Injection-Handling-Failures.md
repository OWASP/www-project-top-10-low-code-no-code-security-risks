# LCNC-SEC-06: Injection Handling Failures

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 2 | 2 | 2 | 2 |

## The Gist

No-code/low-code applications ingest user-generated data in multiple ways, including direct input or retrieving user-generated content from various services.

## Description

No-code/low-code applications ingest user-generated data in multiple ways, including direct input or retrieving user-generated content from various services.
Since applications often query data dynamically based on user input, they are exposed to a significant risk of injection-based attacks.
Moreover, since applications can use user-generated content in various ways including querying a database, parsing a document and more, protection from injection-based attacks must take into account the specific applications and its use of user data. 

## Impact

TBD

## Example Attack Scenarios

Ideas to explore (TBD):
- Improper input sanitation. Automations connecting various user inputs right into DBs. Very similar to the injection risk for Serverless Security.

### Scenario #1

TBD

### Scenario #2

TBD

## How to Prevent

- Sanitize user input, taking into the account the operations that will be performed on that input by the application.
- Educate business users on the risk of unsanitized user input. Platform cannot make this problem go away on their own. 

## References

- [A03:2021 – Injection, OWASP Top 10](https://owasp.org/Top10/A03_2021-Injection/)