---
title: Open Source Maintainer Guidelines
---

*DISCLAIMER: This page is a work-in-progress. Feedback is very appreciated – just [open an issue](https://github.com/18F/open-source-program/issues/new).*

---

## Rationale

18f differs as an organization. Very much of the code is open source, so should be consumable and easy to use by the open source community. The code should therefore be easy to understand as well as easy to use and develop. The code is also meant to be very public. This means everything published on github is essentially making a public statement. All projects should take care to maintain a good public image that will reflect on 18f.

The organization also works on my different projects at the same time, meaning there are many different codebases. This requires an adherence to technical rules, defined by style guides. The style guides themselves should be broad to accommodate the many different projects. Projects and tools should be made general, so all of 18f can share code, reducing the cost and time of all programming projects.

There is a big difference between "throwing source code over the wall", and making a project that is amenable to contributions.

Some terminology used may be GitHub-specific, but the concepts are applicable regardless of version control system or platform.

## Documentation

### The README

Whether the "README" exists as a Markdown file in the repository or as a dedicated web page, project documentation is crucial to provide an entry point for potential users. It should contain the following:

* A quick description of what the project is for. Examples:
    * "An estimator for hourly rates on professional services contracts"
    * "Lightweight analytics reporting and publishing tool for Google Analytics data."
* Instructions of how to use and run the code
    * Test to ensure these instructions work whenever the relevant code changes.
    * Include separate sections for using a project vs developing for it
    * Try to keep these instructions as simple as possible, meaning keeping the build process so its easy to execute.
* Name projects so they are easily consumable by the public.
    * Avoid acronyms
    * Use names that are descriptive of the project purpose
    * Check with your communications team before locking in a name - there may be political/agency/business considerations
* The various types of documentation, either as links, or if short, within the same document:
    * [Usage](#usage-documentation)
    * [Code](#code-documentation)
    * [Developer](#developer-documentation)
* Contact information, possibly an email of somebody on the team.
* Where to ask questions, e.g.
    * Issues
    * Stack Overflow (and whether to use a specific tag – http://stackoverflow.com/questions/tagged/SOMETHING)
    * Chat
        * [Gitter](https://gitter.im/), a chat client that hooks in to a github repository.
        * IRC (https://webchat.freenode.net/?channels=SOMETHING).
    * Mailing list, Google Groups is a possibly resource to set this up.
* Links to additional/alternative resources
    * Bonus: explain how your project is different

#### Usage documentation

* Setup instructions. How to install or setup the project, for use not development.
* Usage examples. Code samples that explain different ways to use the software.
    * Inline usage examples are great
* Version it
    * If it's in the same repository as the code, changes can happen simultaneously

### Contributor documentation

Part of your documentation should be guidelines targeted at (potential) contributors. Documentation for contributers should be separate from the README usage documentation. If you're contributor documentation is brief, you can include it as a section in your README. Otherwise, your [CONTRIBUTING.md](https://help.github.com/articles/setting-guidelines-for-repository-contributors/) file should contain the following:

* Any additional setup steps specific for development.
* Instructions for running the tests.
* Requirements for contribution, if any, e.g.
    * A Contributor License Agreement
        * [CLAHub](https://www.clahub.com/)
        * http://oss-watch.ac.uk/resources/cla
        * http://contributoragreements.org/
    * If commits should be squashed
    * A specific [coding style](#style) to adhere to, but generally contributors will match what they see within a project
* Whether potential contributors should ask before they make significant changes
    * Encourage proposals before big changes
    * "Show me the code"
* Work-in-progress pull requests are ok


### Code documentation

For a library, at least part of code documentation will be targeted at users, while for other projects, it is for contributors. Make sure to:

* Document parameters and returns for each public function or method. This should be done by standardized comments in the code.
* Document the general purpose of each class, module. This should be done by standardized comments in the code.
* Include a step by step document of the source code IF the code is very complex, will be used widely in the open source community, may not be reused directly/as-is but general concepts are modifiable, or is a general library that could be included in different types of projects.
* Document through comments with the language’s standardized documentation standard, or the most popular standard.
    * JavaScript: [JSDoc](http://usejsdoc.org/)
    * Python: [reStructeredText](https://docs.python.org/devguide/documenting.html)
    * Ruby: [RDoc](http://ruby-doc.org/gems/docs/r/rdoc-4.1.2/RDoc/Markup.html)
        * [RubyDoc.info](http://www.rubydoc.info/)
    * [Read the Docs](https://readthedocs.org/)
* Use a style guide for each language on a project.
* Code reviews should maintain documentation standards.
    * Review that these standards are enforced.
    * Review that the specific style guide for the language or project are being enforced.

## Demos

Part of lowering the barrier to entry for a project is understanding what it is useful for, and what the experience of using it will be like. To give potential users an idea, a library could have an example integration can be created in a separate folder or repository, and a web app with a frontend can have a live demo (if the live version isn't publicly accessible already).

## Coverage

"Coverage" means having/providing assurances that your project will survive with high quality over time. Automated tests with good code coverage are an example of ensuring the functionality of the code itself. For the project as a whole, getting multiple maintainers means having someone available to bounce ideas off of, do code reviews, and take the reins in case you (the creator) moves on or loses interest in the project.

## Issue tracking

The best way for potential users or contributors to see outstanding bugs, planned features, and general activity of your project is through an issue tracker. You will want to:

* Make the project issue tracker public
* Add labels, especially ones that are useful to new contributors, e.g.
    * "help wanted"
    * "beginner-friendly"
* Make sure the outcomes of any back-channel conversations (face-to-face, chat, etc.) related to the project are documented somewhere.

## The license

For 18f or government based projects, use a Creative Commons CC0 Universal license. Include this as a document "LICENSE" in the main code repository. The full license can be see on the [CC site](http://creativecommons.org/publicdomain/zero/1.0/)

For information about licensing your project, see [choosealicense.com](http://choosealicense.com).

## Advertisement

* Strong users are most likely to become contributors/maintainers, so take care of them.
* Mailing lists
* Talks - bring you work to the public by talking about it to groups.
    * [Meetups](http://www.meetup.com/) / user groups
    * Conferences
* Answers to related Stack Overflow questions.
* GitHub profile pages (orgs especially) are not a great way to showcase projects.
    * https://github.com/showcases/open-source-organizations
* Bounty programs
    * [List on Hacker Hours](http://hackerhours.org/resources.html#getting-involved-in-open-source)

## Resources

* 18F
    * https://18f.github.io/open-source-program/
    * https://github.com/18F/open-source-policy
    * We also have an [Open Source Style Guide](https://pages.18f.gov/open-source-guide/) that details how to write READMEs, Issues, and Descriptions that are user-friendly and clear. The guide also contains [a checklist](https://pages.18f.gov/open-source-guide/github-repo-checklist/) which we recommend using to make sure you are publishing a user-friendly repository.
* external
    * https://groups.google.com/forum/#!forum/government-open-source
    * http://srawlins.ruhoh.com/checklist-for-the-benevolent-open-source-maintainer/
    * https://github.com/blog/1184-contributing-guidelines
    * http://www.smashingmagazine.com/2013/12/27/open-sourcing-projects-guide-getting-started/
    * http://www.smashingmagazine.com/2013/01/03/starting-an-open-source-project/
    * http://ben.balter.com/open-source-for-government/
    * http://producingoss.com/
    * http://wiki.civiccommons.org/Open_Source_Development_Guidelines

## Releases

* [Semantic versioning](http://semver.org/) w/ corresponding tags
* Changelog.md or [GitHub Releases](https://help.github.com/categories/releases/)
