---
title: Open Source Maintainer Guidelines
---

* Some terminology used may be GitHub-specific, but the concepts are applicable regardless of version control system or platform.
* README
    * Quick description of what the project is for
    * (Link to) documentation
    * make it clear where to ask questions
        * Issues
        * Stack Overflow (and whether to use a specific tag – http://stackoverflow.com/questions/tagged/SOMETHING)
        * chat
            * [Gitter](https://gitter.im/)
            * IRC (e.g. https://webchat.freenode.net/?channels=SOMETHING)
        * Mailing list
    * Include links to additional/alternative resources
        * Possibly explain how yours differs
* Documentation
    * Setup instructions
    * Usage examples
    * Method-level
        * especially if it's a library
        * Inline usage examples are great
        * display
            * [Docco](http://jashkenas.github.io/docco/)/[Rocco](http://rtomayko.github.io/rocco/)
            * [Read the Docs](https://readthedocs.org/)
            * [RubyDoc.info](http://www.rubydoc.info/)
    * Version it
        * Even easier if it's in the same repository as the code - changes can/should happen simultaneously
* Demos
    * Live, for app/frontend project
    * Example implementation
* coverage
    * automated tests
    * humans
        * someone to take the reins, in case you get hit by a bus
        * someone to bounce ideas off of
* Issues
    * make Issues public
        * issue tracker/roadmap that isn't publicly visible makes it difficult for others to dive in
    * Labels
        * "help wanted"
        * "beginner-friendly"
* [CONTRIBUTING](https://help.github.com/articles/setting-guidelines-for-repository-contributors/)
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
    * Instruct if you prefer commits be rebased
* license
    * http://choosealicense.com/
* Advertisement
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
* Resources
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
* Releases
    * [Semantic versioning](http://semver.org/) w/ corresponding tags
    * Changelog.md or [GitHub Releases](https://help.github.com/categories/releases/)
* Establish a consistent coding style, throughout the project or even the organization.
