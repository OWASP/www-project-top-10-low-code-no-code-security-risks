---

layout: col-sidebar
title: "LCNC-SEC-02: Authorization Misuse"

---

## Risk Rating [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| Prevalence | Detectability | Exploitability | Technical Impact |
| --- | --- | --- | --- |
| 3 | 3 | 3 | 3 |

## The Gist

Connections are first-class objects in most low-code/no-code platforms. 
This means connections are made between applications, other users, and/or entire organizations and that if an application is deleted, the connection still remains ‘on’. 
Applications can also be shared with users who should not have access to the underlying data. 
In addition, the application may have a broader authorization scope than the use case demands.

## Business User Description

When writing an application, it’s critical to verify the identity of a user (Authentication), and define the level of access privileges a user has when using that application (Authorization). Authorization misuse occurs when the application incorrectly defines what a user can do in a system.

## Description

Low-code/no-code development does not happen in siloes. 
The impact is based on integrations across the organization’s stack through on-premise, SaaS, PaaS, and cloud platforms. 
Most low-code/no-code platforms come built-in with a large set of connectors, i.e., wrappers around APIs, which allow quick and easy connectivity.
Connectors and user credentials form connections, which are predominantly first-class objects in most low-code/no-codeplatforms. 
This means that connections can be shared among applications, with other users, or with entire organizations.

Many low-code/no-code platforms abuse OAuth authorization flows by querying and storing user refresh tokens, and re-using them at will to increase productivity and reduce time-to-deliver. 
This allows business users to quickly set up connections without thinking about secrets or permissions; at the same time, connections are embedded with user identities that are difficult to monitor or revoke. 
Even though OAuth refresh tokens are designed to be short-lived, they are most frequently valid for a few months or even years. 
Hence, a connection created by a business user in under a minute could persist in the low-code/no-code platform for an extended period and often get used by other users for different purposes than the original intention.

An authorization scope controls the access to resources and assets of an organization. 
Low-code/no-code developers prefer broad authorization scope for their applications to make them as generic as possible. 
For organizations, this allows quick and easy setup of applications, which they can later use for other use cases without needing another application. 
The broad authorization scope does come at the cost of unnecessary risk of authorization misuse.

## Example Attack Scenarios

### Scenario #1

A developer creates a connection to their corporate email account. 
They inadvertently click the “share with everyone” option, granting either usage permissions or full ownership. 
Every user in the organization, including contractors and vendors, gains access to their corporate email account. 
A malicious user triggers a “forgot password” flow and uses the connection to follow through with the process and gain control over the account.

### Scenario #2

A developer creates a simple application to view records from a database. 
The application is configured to ensure each user can only view related records. 
However, the application is configured in such a way that the underlying database connection is implicitly shared with its user. 
An application user can use the database connection directly, gaining full access to all records.

### Scenario #3

Admin connects an application to their source code management system (e.g., Bitbucket) using a service or application account. 
The provisioned service or application account has unrestricted access to all repositories to enable seamless integration. 
Any internal user can abuse this connection to access restricted repositories they usually don’t have access to.

### Scenario #4

A developer creates a simple application to submit forms from one platform to another. 
The application, however, is configured to require authorization to edit and delete form submissions when just creating form submissions should have been enough.

## Example Attack & Misuse Scenarios - Business Users

### Scenario #1

A developer is asked to automate the entry of expense items into a finance system, which automates the process of entry and approval. Finance processes should have privilege separation between the user entering the transaction and the user approving the actions. Because this automation was built with incorrect Authorization, any user running this process can perform both tasks.

### Scenario #2

In an insurance company, a developer is asked to build an application to simplify the intake process of a new Consumer Auto insurance policy.  The application is a big success, and users in the Commercial Auto line start using the application.   

The Commercial Auto process has additional validations that were not planned for in the build of this application, causing major pricing errors later in the process. 

The developer did not anticipate other departmental usage, and therefore never designed the application with appropriate Authorization settings. 

### Scenario #3

A Business Intelligence (BI) report is created to analyze the experience and salaries of employees across departments. This report is intended only for senior management but it has been set with a wide authorization scope, allowing anybody in any department to view detailed information about employees.

A senior manager shares it with their team, who now can see all salaries across the company, including their salary compared to each other.


## How to Prevent

- Disable or monitor the use of implicitly shared connections
- Adhere to the principle of least privilege when providing access to environments that can contain shared connections
- Monitor no-code/low-code platforms for over-shared connections
- Educate business users on the risks of connection sharing and its relation to credential sharing
- Explicitly refresh OAuth tokens on a regular basis by re-authenticating connections.
- Carefully review the scope an application requires and adhere to the principle of least privilege


## References

- [Credential Sharing as a Service: The Hidden Risk of Low-Code/No-Code](https://www.darkreading.com/dr-tech/credential-sharing-as-a-service-hidden-risk-of-low-code-no-code)
- [Low-Code Platforms Are the New Holy Grail for Hackers](https://www.zenity.io/blog/why-are-low-code-platforms-becoming-the-new-holy-grail-of-cyberattackers/)
