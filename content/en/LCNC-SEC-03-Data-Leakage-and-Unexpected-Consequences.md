# LCNC-SEC-03: Data Leakage and Unexpected Consequences

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| TBD | TBD | TBD | TBD |

## The Gist

No-code/low-code applications often sync data or trigger operations across multiple systems, which create a path for data to find its way outside the organizational boundary and operations in one system to have unexpected consequences in another.

## Description

No-code/low-code applications are often used to sync data between multiple systems or trigger operations on one system as a result of a change in another.
As data movers, no-code/low-code applications can easily cause data leakage by moving data outside the organizational boundary, to another organization or to a personal account.
As operation triggers, no-code/low-code applications can result in unexpected consequences by implicitly coupling an operation one with system with a change on another.
Furthermore, multiple applications can be connected to and triggered by a single data source, resulting in chained data movement or operation triggers which are difficult to predict or fully map.

## Impact

TBD

## How to Prevent

TBD

## Example Attack Scenarios

Email forwarding
Shadow vendors - data moving outside the org boundary
Several hidden automations chain together two seemingly unrelated systems

### Scenario #1

TBD

### Scenario #2

TBD

## References

TBD