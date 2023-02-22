---

layout: col-sidebar
title: "LCNC-SEC-06: Injection Handling Failures"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 2 | 2 | 2 | 2 |

## The Gist

No-code/low-code applications ingest user-provided data in multiple ways, including direct input or retrieving user-provided content from various services. Such data can contain malicious payloads that may introduce risk to the application.

## Description

No-code/low-code applications ingest user-provided data in multiple ways, including direct input or retrieving user-provided content from various services.
Since applications often query data dynamically based on user input, they are exposed to a significant risk of injection-based attacks.
Moreover, since applications can use user-provided content in various ways, including querying a database, parsing a document, and so forth, protection from injection-based attacks must consider the specific application and its use of user data. 

## Example Attack Scenarios

### Scenario #1

A developer sets up automation that triggers on new publications to an RSS feed and stores them into a SQL database.
An attacker controlling the feed uses this flow to inject commands into the database that delete important records.

### Scenario #2

A developer creates an app that allows users to fill out forms.
The app encodes form data as CSV files and stores them on a shared drive.
Even though the platform sanitizes form inputs for SQL injection attacks, they are not sanitized for Office macro attacks.
An attacker takes advantage of this and inputs a macro that gets written into the CSV file.
A user opens the CSV file to analyze user forms, and the macro gets executed.

## How to Prevent

- Sanitize user input, taking into account the operations that will be performed on that input by the application.
- Educate business users on the risk of unsanitized user input. Platforms cannot make this problem go away on their own. 

## References

- [SOQL Injection](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/pages_security_tips_soql_injection.htm)
- [A03:2021 – Injection, OWASP Top 10](https://owasp.org/Top10/A03_2021-Injection/)