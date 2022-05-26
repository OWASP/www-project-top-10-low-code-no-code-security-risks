# LCNC-SEC-08: Data Handling Failures

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## The Gist

No-code/low-code applications often store data or secrets as part of their "code" or on managed databases offered by the platform, which needs to be properly stored in compliance with regulation and security requirements.

## Description

No-code/low-code applications can store data as part of their "code" or on managed databases offered by the platform.
Data stored in databases managed by no-code/low-code vendors often includes sensitive data, including PII and financial data.
Application creators can decide how to store data, and administrators often lack visibility into such managed databases.
In many cases, sensitive data is stored unencrypted, data is moved between geo-locations without regulatory requirements in mind.

Furthermore, application creators have many opportunities to hard-code secrets into their "code".
Whether its through environment variables, configuration or code, applications can often rely on hard-coded secrets to access services.
Hard-coded secrets are available to all users with write permissions to the applications, and might also leak to application readers or anonymous users via client-side code.

## Example Attack Scenarios

Ideas to explore (TBD):
- Sensitive data stored unencrypted (e.g. credit card)
- Data moved between GEOs in a non-compliant way

### Scenario #1

TBD

### Scenario #2

TBD

## How to Prevent

- Educate business users on the compliance, private and security risks related to data storage.
- Monitor managed databases, environment variables and configuration provided by no-code/low-code vendors for sensitive data.
- Ensure security teams are involved with applications gain access to sensitive data. 

## References

- [Establishing a DLP strategy](https://docs.microsoft.com/en-us/power-platform/guidance/adoption/dlp-strategy)