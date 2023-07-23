---

layout: col-sidebar
title: "LCNC-SEC-06: Injection Handling Failures"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 2 | 2 | 2 | 2 |

## The Gist

Resources built using low-code/no-code development platforms ingest user-provided data in multiple ways, including direct input or retrieving user-provided content from various services. 
Such data can contain malicious payloads that may introduce risk to the application, automation, connection, workflow, bot, or integration.

## Business User Description

When user’s input data into a system, that data can be interpreted as “code to run” rather than “data to be stored or processed”.  

## Description

Low-code/no-code applications ingest user-provided data in multiple ways, including direct input or retrieving user-provided content from various services. 
Since applications often query data dynamically based on user input, they are exposed to a significant risk of injection-based attacks. 
Moreover, since applications can use user-provided content in various ways, including querying a database, parsing a document, and so forth, protection from injection-based attacks must consider the specific application and its use of user data.

## Example Attack Scenarios

### Scenario #1

A developer sets up an automation that triggers every time a new publication is made to an RSS feed and stores it into a SQL database. 
An attacker controlling the feed uses this flow to inject commands into the database that delete important records.

### Scenario #2

A developer creates an application that allows users to fill out forms. 
The app encodes form data as CSV files and stores them on a shared drive. 
Even though the platform sanitizes form inputs for SQL injection attacks, security teams need to think about and label all the different things that are inputting data into, which is likely to result in something being missed, like an Office macro attack. 
An attacker takes advantage of this and inputs a macro that gets written into the CSV file. 
A user opens the CSV file to analyze user forms, and the macro gets executed.

## Example Attack & Misuse Scenarios - Business Users

### Scenario #1

A user builds an online feedback form for an ecommerce store. A malicious user fills out the form using their knowledge of database commands that updates the prices of an item from $1,000 to $1. The hacker then buys the $1,000 item for $1, costing the company $999. 

### Scenario #2

A user builds a registration form for new users. A malicious user uses their knowledge of database commands to craft a specific input into the user field, which deletes all users from the database. Users with pending orders try to check on the status of their orders, to be told their account doesn’t exist.

## How to Prevent

- Sanitize user input, taking into account the operations that will be performed on that input by the application
- For database interaction via SQL, also use query parameterization, stored procedures, or escaping
- Educate business users on the risk of unsanitized user input. Platforms cannot make this problem go away on their own


## References

- [SOQL Injection](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/pages_security_tips_soql_injection.htm)
- [A03:2021 – Injection, OWASP Top 10](https://owasp.org/Top10/A03_2021-Injection/)
- [Robot Framework / RPA Framework SQL injection example & prevention](https://aabashkin.github.io/posts/rf_sqli#a-modern-example-with-a-low-code--rpa-platform)
