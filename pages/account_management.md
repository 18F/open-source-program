---
title: "Account Management at GitHub.com"
authors: "@benbalter and @daveloyall"

---

#### Organization or user

Agencies should be represented by [GitHub organizations](https://help.github.com/articles/what-s-the-difference-between-user-and-organization-accounts#organizations). Think of these as roughly analogous to a Facebook Page.  Organizations do not have their own login, but are administered by users. Organizations have their own, distinct online presence, can own repositories, and can have unlimited members and teams.

#### Teams

Within organizations, users are grouped into teams. Teams often reflect real-world groupings and organizational structure within your agency, or because users can belong to multiple teams, can be custom tailored to specific projects. Just like your agency, there might be a new media team, a internal tools team, etc. Organizations can have unlimited teams, and teams can have unlimited users.

Team membership not publicly disclosed and is often used to delegate access or permissions on three levels: administration access, read-only ("pull") access, and read-write ("push and pull") access. This way, a team, representing a subunit of your organization, can have complete control over their repositories.

For flexibility and ease-of-use, best practices suggest that whenever possible, prefer social or policy constraints over technical constraints when it comes to delegating repository ownership. Often agencies can have a better experience by liberally granting team permissions and culturally setting expectations as to ownership and access.

#### Publicizing Teams

By default, teams remain visible only to members of the organization. If you would like to create a public presence for each team, many private-sector GitHub users have, and government agencies are beginning to leverage the native GitHub Pages functionality to create a public presence which is fully customizable and brandable. Some great examples of this are http://twitter.github.io/, http://square.github.io/, and http://gsa.github.io/federal-open-source-repos/.

To begin, simply create a repository in your organization called `[username].github.io`, for example, if your organization is `agency`, the repository would be `agency/agency.github.io`. From there, you can push any static or Jekyll-enabled files to the `master` branch, and they will become visible at `agency.github.io`. You can even set up a redirect, such that `developers.agency.gov` displays the branch's content.

Like the examples above, it may be possible to leverage the GitHub API to dynamically display all your organization's teams or projects. For more information, see the [GitHub Pages ](https://help.github.com/categories/20/articles) and [developer](http://developer.github.com/v3/orgs/) help documentation.


#### Two-factor Authentication

As of 2013, GitHub allows for 2-factor authentication. This is a recommended extra step that can help organizations
secure it's assets and demonstrate access controls.

 - [Wikipedia: Multi-factor authentication](http://en.wikipedia.org/wiki/Multi-factor_authentication)
 - [GitHub blog post describing 2FA](https://github.com/blog/1614-two-factor-authentication)


#### Requiring users to establish purpose-specific accounts

In short, there should be a one-to-one relationship between each Github user account (a login) with one real-world person ("a human").  Just like each human at your agency has an e-mail address and a computer login, each individual should have their own GitHub login. Users can then join one or more Organizations, again just like in the real world. I can be a USDA employee, for example, (and thus a member of the USDA organization), and also be a member of the Under Water Basket Weaving Club. GitHub will can automatically disambiguate the context of my actions, and reflects that context in all URLs.

If an individual already has a GitHub account, they should add their government email address to their account (by design, users can have multiple email address per account), and if they're already using Git, configure Git on their work computer to use that email for those repositories. If they're a new user, they should create a new account using their (individual) government email address. This is strongly preferred over requiring government employees to create distinct `joe_abc_agency` accounts to distinguish their personal use.

GitHub's a social network. GitHub's passionate about the best way to build software so that's its a positive experience for everyone involved. The GitHub community feel that it should be a social experience, interacting with humans, not software. As users start to stretch community norms, that ideal workflow begins to deteriorate. As the TOS notes:

> One person or legal entity may not maintain more than one free account

That's not because too many accounts are hard on the servers or because developers want to make things harder on agencies. It's because we want a user to be a human, to have an identity. To be seen as a person. To be social. To interact. To grow communities around shared causes. That's what open source is all about, and when a user is not a person, but an anonymous icon, that get's a lot harder.

#### Gravatar

Account icons, for both users and organization are maintained by Gravatar, a third party service which simply correlates a profile images with an email address. Lots of website use Gravatar for their profile images, like WordPress, Hootsuite, Disqus, and Stack Overflow.

To set up your Gravatar, simply follow the instructions on your profile page. The email address you associate with your Gravatar need not be public, and need not be the same with which you receive notification or make commits.

#### Social Media Registry

If you're a US Federal Agency, be sure to add your organization account to the [US Social Media Registry](http://www.usa.gov/About/developer-resources/social-media-registry.shtml) for optimum discoverability.
