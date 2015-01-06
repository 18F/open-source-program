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

## Code documentation

For a library, at least part of code documentation will be targeted at users, while for other projects, it is for contributors. Make sure to:

1. Document parameters and returns for each public function or method. This should be done by standardized comments in the code.
1. Document the general purpose of each class, module. This should be done by standardized comments in the code.
1. Include a step by step document of the source code IF the code is very complex, will be used widely in the open source community, may not be reused directly/as-is but general concepts are modifiable, or is a general library that could be included in different types of projects.
1. Document through comments with the language’s standardized documentation standard, or the most popular standard.
	- JavaScript: [JSDoc](http://usejsdoc.org/)
	- Python: [reStructeredText](https://docs.python.org/devguide/documenting.html)
	- Ruby: [RDoc](http://ruby-doc.org/gems/docs/r/rdoc-4.1.2/RDoc/Markup.html)
		- [RubyDoc.info](http://www.rubydoc.info/)
	- [Read the Docs](https://readthedocs.org/)
1. Use a style guide for each language on a project.
1. Code reviews should maintain documentation standards.
	- Review that these standards are enforced.
	- Review that the specific style guide for the language or project are being enforced.

## Project documentation
### The README

Whether the "README" exists as a Markdown file in the repository or as a dedicated web page, project documentation is crucial to provide an entry point for potential users. It should contain the following:

* A quick description of what the project is for
* Instructions of how to use and run the code
	* Test to ensure these instructions work whenever the relevant code changes.
	* Include separate sections for using a project vs developing for it
	* Try to keep these instructions as simple as possible, meaning keeping the build process so its easy to execute.
* Name projects so they are easily consumable by the public.
	* Avoid acronyms
	* Use names that are descriptive of the project purpose
	* Check with your communications team before locking in a name - there may be political/agency/business considerations
* Include the various types of documentation, either as links, or if short, within the same document:
	* [Usage](#usage-documentation)
	* [Code](#code-documentation)
	* [Developer](#developer-documentation)
* Include contact information for receiving more information
* Make it clear where to ask questions
    * Issues
    * Stack Overflow (and whether to use a specific tag – http://stackoverflow.com/questions/tagged/SOMETHING)
    * chat
        * [Gitter](https://gitter.im/)
        * IRC (https://webchat.freenode.net/?channels=SOMETHING)
    * Mailing list
* Include links to additional/alternative resources
    * Bonus: explain how your project is different

### Usage documentation

* Setup instructions
* Usage examples
* Method-level
    * especially if it's a library
    * Inline usage examples are great
* Version it
    * If it's in the same repository as the code, changes can happen simultaneously

### Demos

* Live, for app/frontend project
* Example implementation

### Coverage

* automated tests
* humans
    * someone to take the reins, in case you get hit by a bus
    * someone to bounce ideas off of

### Issue tracking

* make Issues public
    * issue tracker/roadmap that isn't publicly visible makes it difficult for others to dive in
* Labels
    * "help wanted"
    * "beginner-friendly"

### Developer documentation

Part of your documentation should be guidelines targeted at (potential) contributors. This should include:

* [CONTRIBUTING.md](https://help.github.com/articles/setting-guidelines-for-repository-contributors/)
* Include any additional setup steps
* Include instructions for running the tests
* Explain requirements
    * Contributor License Agreement
        * [CLAHub](https://www.clahub.com/)
        * http://oss-watch.ac.uk/resources/cla
        * http://contributoragreements.org/
    * You can specify a specific coding style to adhere to, but generally contributors will match what they see within a project.
* sometimes ask before you make changes, sometimes don't
    * Encourage proposals before big changes
    * "Show me the code"
* WIP PRs are ok
* Instruct if you prefer commits be rebased, or if there's any other specific [style guidelines](#style) to be followed

### The license

* http://choosealicense.com/

### Advertisement

* This is marketing
    * Strong users are most likely to become contributors/maintainers, so take care of them
* Mailing lists
* Talks
    * [Meetups](http://www.meetup.com/) / user groups
    * Conferences
* Answers to related Stack Overflow questions
* GitHub profile pages (orgs especially) are not a great way to showcase projects
    * https://github.com/showcases/open-source-organizations
* Bounty programs
    * [List on Hacker Hours](http://hackerhours.org/resources.html#getting-involved-in-open-source)

### Resources

* 18F
    * https://18f.github.io/open-source-program/
    * https://github.com/18F/open-source-policy
* external
    * https://groups.google.com/forum/#!forum/government-open-source
    * http://srawlins.ruhoh.com/checklist-for-the-benevolent-open-source-maintainer/
    * https://github.com/blog/1184-contributing-guidelines
    * http://www.smashingmagazine.com/2013/12/27/open-sourcing-projects-guide-getting-started/
    * http://www.smashingmagazine.com/2013/01/03/starting-an-open-source-project/
    * http://ben.balter.com/open-source-for-government/
    * http://producingoss.com/
    * http://wiki.civiccommons.org/Open_Source_Development_Guidelines

### Releases

* [Semantic versioning](http://semver.org/) w/ corresponding tags
* Changelog.md or [GitHub Releases](https://help.github.com/categories/releases/)

### Style

* Establish a consistent coding style/conventions, throughout the project or even the organization.
