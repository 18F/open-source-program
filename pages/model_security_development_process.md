---
title: "Model Security Development Process"
---


{AGENCY} Security Development Process


## Executive Summary

In order to obtain the most secure and well-written code possible, {AGENCY} develops code publicly by default subject to informal and formal security review at each point of significant increased risk. Clarifying examples are provided. A monthly meeting between {TEAM} engineers and {AGENCY} security experts will facilitate communication.

## A Basic Strategy

The basic {AGENCY} strategy is to avoid the danger that the code may be compromised, revealing vulnerabilities to bad actors, by insuring that code has low vulnerabilities by developing “Open-source by Default.” Developers write safer code when they do so in the light. A disgruntled employee cannot steal public code. This policy avoids rely on the secrecy of the source code itself, and concentrates the security effort into protecting a smaller number of secrets. Code is continually improved on a weekly basis.

In most projects, there are clear transitions that represent risk-increasing events. For example, a project that maintains data should be developed with security in mind from the beginning, but must be secure by the time it is in production and actually accepting data. Preparation for “go live” therefore represents a clear even in which the additional security scrutiny required by prudence and FISMA should be applied.

Often, a change the data model, a major feature, or a minor feature change to the authentication mechanism represents an event that should trigger {AGENCY} Security review. We call these security review events.

This document describes how security review events should be identified and handled.

## Processes for Vulnerabilities

By using GitHub for development, any repository may be made private instantaneously. This is the proper response to the suspicion of a code-based vulnerability, because it is cheap---the repository can also be made public again when it is deemed safe to do so.

A classic and fairly common mistake is to check in a password. This is best avoided by never committing configuration information to the source code (see Software Engineering Techniques below.) The proper response to this is to immediately change the password. Making the repository private does not help, because there is no record of who may have read the repository, and may even alert an attacker to a vulnerability. A better policy is to change the password first, make the repository private, fix the inherent flaw in including a password in the repository, and then make the repository public again.

A subtler example is the discovery of a vulnerability created by a badly written piece of code: for example,

## Software Engineering Techniques

A clear distinction will be made between code, which is sharable and reusable, and configuration and credentials, which is specific to deployment and should not be shared. Our basic process is not to commit configuration information to source code repositories at all, but to deploy configuration through non-code settings. This is perhaps the most immediately exploitable vulnerability of open-source development. It is imperative to respond to such mistakes as quickly as possible.

Generally, one must test and develop code on deployed sites before it can be placed in production. A fundamental technique is to protect such deployed, implemented, non-production sites is to limit access to these sites by firewalls and/or basic http authentication.

Particular caution is required by {AGENCY} in planning its development and test sites, due to the general habit of many developers of using internet-accessible cloud-hosting development servers. It is important that {AGENCY} understand that data can be stolen from a test site just as readily and from a “production site”. For the purpose of this document, it is more valuable to think of anything exposed beyond the {AGENCY} firewall to the internet-at-large to be “production”, whether it is promoted to half a dozen engineers and user acceptance testers or to every US citizen.

## Security Review Events that Always Require a Formal Security Review

We can easily identify a non-exhaustive list of events that should trigger preceding security review by the {AGENCY} Security staff. These include:
1. The transition from development into production.
2. Significantly increasing the number of users that have access to a system.
3. Deploying a new connection between two systems.
4. Making a change to access control mechanisms, such as adding “groups” to a system which did not have them previously.
5. Utilizing a new third-party software system in a system which is already in production.

Some example of events that do not increase risk include:
1. Creating a repository to begin exploring ideas which do not contain documents, data, or code that mention or access external systems.
2. Deploying test servers on a government issued laptop.
3. Making minor code changes which are not expected to change functionality. A typical example is a CSS styling issue. However, another example might be changing a search algorithm that delivers search results behind a well-defined API. Such a change may create bugs but is unlikely to change the security posture.
4. Utilizing a new third-party software system in a system which is not yet in production.

Examples of development milestones which fall in-between these clear-cut examples should be discussed in the monthly meetings, or whenever they arise, between team engineers and the security review staff.

## Invitation of Additional Analysis


By developing public code there is a sense in which security review is always invited. There is never anything stopping anybody from looking for vulnerabilities in our code. However, that statement is not a practical strategy for informing heavily employed {AGENCY} Security of projects they may wish to study outside of the formal triggers for security review outlined above.

A once-a month meeting between {TEAM} and the {AGENCY} Security office will allow clarity into the status of each project, a discussion of security risks, and a general understanding of upcoming issues. This meeting will also have the benefit of spreading knowledge of security best practices.

Additionally, {TEAM} invites scanning of the static code with tools such as Fortify(TM) at any time.

For those sites which are deployed other than on private, non-internet accessible machines, {TEAM} invites active web-scanning at anytime with 24 hours notice and will provide sufficient credentials and instructions to make this fruitful.

## Some Scenarios and Examples

#### Scenario 1: It is discovered that a project has checked in a password.

Let us suppose that in the normal course of coding, an engineer is reading code and notices that a password has been committed to a public repository. It cannot be known if this vulnerability has been exploited. The best policy is to immediately change the password, assuming this can be done quickly.

Only after this is done should the site be made private. When these two actions have occurred, the engineering staff and the security team can calmly assess how to improve the process to avoid this coding mistake in the future. When everyone is satisfied, the repository can be made public again.

#### Scenario 2: An {AGENCY} Security officer becomes concerned about a revealed exploit in a third-party software system employed by a production system

A project utilizes a free open-source library to save the taxpayer money. A security expert announces that he believe this package as an exploitable vulnerability. {TEAM} and the {AGENCY} Security staff consider the following actions:

1. Temporarily making the repository private that mentions the suspect system to obscure the fact that this vulnerability may exist.
2. Disabling the use of that library immediately and immediately deploy this code change to the live production site to maintain availability.
3. If necessarily, temporarily brining the site down until the fix can be resolved.

#### Scenario 3: A project is planning to make a connection to a API offered by a third party that will pass PII to and from the API.

The security staff learns of this in the monthly meeting and asks if it is really needed to accomplish the meeting. They ask how the data will be in transit, and if we are legally prepared to exchange this data with the third party and confident that they have sufficient controls in place to be trusted. Although there is no reason to stop development, the connection is not enabled until the security staff is satisfied.

#### Scenario 4: A web-site experiences an increase in invalid login attempts. The attacker does not appear to have been successful yet. These attacks appear more focused than those of automated “script-kiddie” attacks.

In addition to whatever actions the {TEAM} security staff takes, the development staff should analyze the attacks and see if they are based on some actual vulnerability in expressed in the code.

#### Scenario 5: In response to a Security Review Event, static security scans reveal significant vulnerabilities in a project.

As has been done on previous projects, {TEAM} will make the resolution of these vulnerabilities a high priority and they will be resolved before the risk-increasing event occurs.
