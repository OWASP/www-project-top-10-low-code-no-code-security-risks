---
layout: col-sidebar
title: OWASP Top 10 Low-Code/No-Code Security Risks
site_side: true
tags: low-code no-code
level: 2
project: true
type: documentation
pitch: The primary goal of the "OWASP Top 10 Low-Code/No-Code Security Risks" document is to provide assistance and education for organizations looking to adopt and develop Low-Code/No-Code applications. The guide provides information about what are the most prominent security risks for such applications, the challenges involved, and how to overcome them.
---

## Overview
Low-code/No-Code development platforms provides a development environment used to create application software through a graphical user interface instead of traditional hand-coded computer programming. 
Such platforms reduce the amount of traditional hand coding, enabling accelerated delivery of business applications. 

As Low-Code/No-Code platforms proliferate and become widely used by organizations, there is a clear and immediate need to create awareness around security and privacy risks related to applications developed on such platforms.
<br>
<br>
The primary goal of the "OWASP Top 10 Low-Code/No-Code Security Risks" document is to provide assistance and education for organizations looking to adopt and develop Low-Code/No-Code applications. 
The guide provides information about what are the most prominent security risks for such applications, the challenges involved, and how to overcome them.
.

## The List (First Draft)

### Risk #1: Privilege Escalation
To boost innovation, low-code platforms have taken a shortcut to help makers build apps. Apps do not have their own identities, but instead use the identity provided by the maker. A security savvy maker might identify this pitfall and provide a service identity, but unfortunately the vast majority of low-code apps run with personal user credentials. This means that by gaining access to an app, a user gains access to its underlying credentials and in some cases can manipulate and use them however he wishes. This fact makes low-code apps the perfect bed for breaking authorization boundaries. If not careful, users can easily have access to resources they are not authorized to use, and they would access them with another user’s identity. The same mechanism allows attackers to elevate their privileges. Most low-code platforms have some notion of a default environment where connections to data sources are placed by default. These typically contain access to user accounts, cloud services, SaaS services and many more.

### Risk #2: Insecure Authentication
Low-code apps are not built in silos, they are built on top of the organization’s critical business data. Connections to data sources are defined by low-code makers, which are oftentimes not experts in authentication (e.g. citizen developers). This can result in connections that use HTTP rather than HTTPs, weak encryption ciphers and insecure transmission of secrets.

### Risk #3: Data Leakage
Low-code apps usually revolve around streamlining a business process or automating a task. Many times this is coupled with moving data from A to B or connecting operation C to operation D (if this then that). This also means that data can easily find its way outside of the organizational boundary. Typical examples include moving data to unauthorized services (i.e. shadow IT) and storing business critical data in the wrong place, for example on personal drives.

### Risk #4: Oversharing
To enable fast expansion within the enterprise, low-code platforms make sharing of apps, components and data extremely easy. You can share a connection to a data source, an application, automation, on-prem connection and many more. Sharing with the entire organization may sometimes even be a platform default. Oversharing can easily result in breaking the enterprise permission model.

### Risk #5: Data and Secret Handling Failures
Low-code/no-code applications typically connect to business-critical data. 
Due to common mistakes or lack of security expertise, connections are often set up insecurely using plaintext protocols or weak credentials.

### Risk #6: Misconfiguration
Low-code platforms provide a wide range of features, some of which control the balance between security and support of specific use cases. For example, Portal Apps by Power Platform allow creating self-service portals for unauthenticated users. However, misconfiguration of those apps could lead to these users having full access to data sources that underlie this app.

### Risk #7: Business Continuity, Resiliency and Ownership Failures
Low-code/no-code application are prone to be abandoned while remaining active. 
The ease of creating a new applications, their relatively low-maintenance costs and the fact that they often are managed by a SaaS services are all contributing factors. 
This means that the number of active applications in an organization tends to go up drastically, and that popular business applications can often find themselves without an owner.

### Risk #8: App impersonation
Because low-code apps are usually developed by the organization, users tend to trust them blindly. However, low-code platforms allow users to upload and deploy an application from an external source, including the platform marketplace. An attacker or a malicious insider could use this blind trust to impersonate a viable app and launch a consent phishing campaign within the organization.

### Risk #9: Dependency Injection
Low-code apps have grown to serve critical business needs, and thus they must be scalable and support many use cases. In order to do that while still being easy and intuitive to use, low-code apps rely heavily on a marketplace ecosystem where the platform and its users can share components, connectors and even ready-to-use apps with each other. This is very similar in nature to OSS (open source software) being used when building business applications with pro code. The security community has made huge strides in addressing the OSS dependency security concern, but unfortunately, these solutions do not cover low-code security vulnerabilities. Low-code platforms allow makers to use marketplace components from any source, including sources outside of the marketplace! This could easily lead to attackers gaining access to and manipulating the application, it’s underlying credentials and those of every user that connects to the application.

### Risk #10: Unmanaged Custom Code
Low-code/no-code applications often enable extendability through custom code. 
These pieces of code are embedded into the application, and in some cases are not held up to the same level of security vigilance as with other pro-code applications. 


## Getting Involved
You do not have to be a security expert or a programmer to contribute. 
Contact the project leader(s) to get involved, we welcome any type of suggestion and comments. Possible ways to contribute:
 * We are actively looking for organizations and individuals that will provide vulnerability prevalence data
 * Translation efforts (later stages)
 * Individuals and organizations that will contribute to the project will be listed on the acknowledgments page


## Project Sponsors
The OWASP Top 10 Low-Code/No-Code Security Risks project is supported by [Zenity](https://www.zenity.io/)
<br>
[![Zenity](assets/images/zenity-new-logo2.png)](https://www.zenity.io/)
