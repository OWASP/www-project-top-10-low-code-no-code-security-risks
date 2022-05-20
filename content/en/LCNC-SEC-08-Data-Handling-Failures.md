# LCNC-SEC-08: Data Handling Failures

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| TBD | TBD | TBD | TBD |

## The Gist

No-code/low-code applications often store data or secrets as part of their "code" or on managed databases offered by the platform, which needs to be properly stored in compliance with regulation and security requirements.

## Description

No-code/low-code applications can store data as part of their "code" or on managed databases offered by the platform.
Data stored on databases managed by no-code/low-code vendors often includes sensitive data, including PII and financial data.
Application creators can decide how to store data, and admins often lack visibility into those managed databases.
In many cases, sensitive data is stored unencrypted, data is moved between geolocations without regulatory requirements in mind.

Furthermore, application creators have many opportunities to hard-code secrets into their "code".
Whether its through environment variables, configuration or code, applications can often rely on hard-coded secrets to access services.
Hard-coded secrets are available to all users with write permissions to the applications, and might also leak to application readers or anonymous users via client-side code.

## Impact

TBD

## How to Prevent

TBD

## Example Attack Scenarios

Sensitive data stored unencrypted (e.g. credit card)
Data moved between GEOs in a non-compliant way

### Scenario #1

TBD

### Scenario #2

TBD

## References

TBD