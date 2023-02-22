---

layout: col-sidebar
title: "LCNC-SEC-08: Data and Secret Handling Failures"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## The Gist

No-code/low-code applications often store data or secrets as part of their "code" or on managed databases offered by the platform, which must be stored adequately in compliance with regulation and security requirements.

## Description

No-code/low-code applications can store data as part of their "code" or on managed databases offered by the platform.
Data stored in databases managed by no-code/low-code vendors often include sensitive data, including PII and financial data.
Application creators can decide how to store data, and administrators often lack visibility into such managed databases.
In many cases, sensitive data is stored unencrypted and moved between geo-locations without considering regulatory requirements.

Furthermore, application creators have many opportunities to hard-code secrets into their "code".
Whether it's through environment variables, configuration, or code, applications can often rely on hard-coded secrets to access services.
Hard-coded secrets are available to all users with write permissions to the applications and might also leak to application readers or anonymous users via client-side code.

Moreover, many native log streams mix application logs, metrics, and sensitive data being passed through the application.
In many platforms, logs will contain actual data points the application uses by default.

## Example Attack Scenarios

### Scenario #1

A developer creates a business application that asks users to fill out a form with sensitive data.
They use the managed database provided by the platform to store results.
Since the managed database is stored with every other developer by default, they all gain access to the sensitive data.

### Scenario #2

A developer creates an application using a custom API and hard-codes the API key in the code.
Other developers can access the API key directly.
Moreover, the API key might leak to the app's client code allowing users to gain direct access to the key.

## How to Prevent

- Educate business users on the compliance, privacy, and security risks related to data storage.
- Monitor managed databases, environment variables, and configuration provided by no-code/low-code vendors for sensitive data.
- Ensure security teams are involved with applications having access to sensitive data. 

## References

- [3 Ways No-Code Developers Can Shoot Themselves in the Foot](https://www.darkreading.com/dr-tech/3-ways-no-code-developers-can-shoot-themselves-in-the-foot)
- [Establishing a DLP strategy](https://docs.microsoft.com/en-us/power-platform/guidance/adoption/dlp-strategy)