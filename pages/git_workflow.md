---
title: "Git Workflow"
---


<p class="lead">This section explains how we use Git. See the bottom of this page for the Git Cheat Sheet and
useful free resources for learning Git.</p>

If you've never used Git before, you should know two things:

- It has a learning curve.
- Once you get it, your work will be much better, and you'll insist on using it for every coding project you work
on.

Git is a revision control system. It lets multiple people work on a code project without stepping on each other's
toes. It also saves every previous version of your files, so if something breaks, reverting is easy.

The basic workflow for Git goes something like this:

- You tell Git that you're going to work on a certain project, or "repository".
- You make your own copy of that project.
- You make whatever changes to the code you like and test them in your repository.
- When you're ready to have those changes reflected in the live code (```master```), you update your copy so
that it reflects any changes made by others in the time since you initially made the copy.
- You commit your changes to master.

Here's that workflow as written in Git. If you're ever in doubt about whether you're doing things in the right
order, this simple workflow will keep you straight:

{% highlight console %}
$ git checkout master
$ git pull
$ git checkout -b feature-A
{% endhighlight %}

This last line creates a new branch (called ```feature-A```) in your copy. A branch is a way of saying, "I'm going
to work on this bug," or "I'm going to code a new feature." You should ALWAYS create a new branch, no matter how
mundane your changes are going to be.

Once you are done with your changes and are ready to commit them back to ```master```:

{% highlight console %}
$ git commit -am "I just added a new feature"
$ git checkout master
$ git pull
$ git merge feature-A
$ git push
{% endhighlight %}

In order, these lines:

The first line commits your changes to your branch. The next two lines ensure your ```master``` copy is up to date
with the TRUE ```master```, or "```origin master```". The next line moves your ```feature-A``` branch changes into
your ```master``` branch, and the final line moves those changes onto ```origin master```.

It may differ slightly from project to project and may require some experimentation and refactoring. That said,
here are some guidelines to follow:


## People: Developers & Maintainers

Simply, a _Developer_ is a person or roles who writes software. A _Maintainer_ controls what is allowed to be in
the central reposisitory. A person may be _both_ a Developer and a Maintainer, but preferably not on the same code.

**Developers** write code in their repo and do not have commit access to the {{site.data.meta.org_name}} master branches.

**Maintainers** own and are accountable for the {{site.data.meta.org_name}} master branches. They ensure that any code there adheres to
all defined criteria. Additionally, they determine the version (tag) of each repository.


----

## Branching and Merging

### Terms:

- **Fork** &ndash; A clone of a GitHub repository that was created using the
<img src="http://i.imgur.com/SMr70.png" alt="Fork" align="absmiddle" /> feature. A fork allows you and the
maintainer to use GitHub pull requests and lists the developer in the maintainer's network. This is very useful in
larger projects with many committers.
- **Integration branch** &ndash; a branch that is only used to merge work in from other branches. ```master```,
for example, should be an integration branch. In most cases, it's a bad idea to code directly on {{site.data.meta.org_name}}'s master
branches.
- **```origin```** refers the main remote repository (production).
- **Tracking branch** &ndash; a local branch that is set up to track a branch in some remote repository.
- **Topic branch** &ndash; a short-term branch used to address a feature or bug.
- **Long running branch** &ndash; a branch that could take a while to complete.
- **Issue** &ndash; a bug or a feature.
- **Pull Request** &ndash; When a developer is ready to have her or his changes integrated, they use the
[pull request](https://help.github.com/articles/using-pull-requests/) feature in GitHub to merge their work into
the main/live/production distribution.

### The Gauntlet

- ```therepo/origin/master``` is *always* deployable. If it's in ```master```, it can go to production. Period.
The end.
- Never code on ```origin/master```, because it's an integration branch. Code on some other branch in your own
repository and make pull requests.
- Create a remote in your repo that points to the {{site.data.meta.org_name}} repo you're working on:

{% highlight console %}
$ git remote add org_remote git://github.com/{{site.data.meta.org_name}}/[reponame].git
$ git fetch {{site.data.meta.org_name}}
{% endhighlight %}

- _Merge early and often_, that is, keep your work in sync with {{site.data.meta.org_name}}/origin.

{% highlight console %}
$ git pull --all org_remote
{% endhighlight %}

- Always branch from ```therepo/origin/master``` when starting something new.
- A new branch should be tied to something in GitHub's issue tracking
- Keep your working directory clean. (There should be no un-staged files when committing. Everything should be
staged or ignored.)
- Name your branches something meaningful (e.g., ```encoding-bug``` or ```notifications-feature```). If working on
a release with many features and people, use your name or initials in the branch name. For example:
```bill/bug-123```, ```ross/kb-search```, etc.

- Delete branches once they have been merged:

{% highlight console %}
$ git branch -d bug-123
$ git push :origin/bug-123
{% endhighlight %}

The first command deletes the local branch and the second one removed the remote branch.

- Tag releases:

{% highlight console %}
$ git status
        # On branch master
        nothing to commit (working directory clean)
$ git tag -a v1.0.6
$ git push -tags
{% endhighlight %}


The tag command generates and annotated tag in the local repo, but you will also want to push this tag to the
remote. This is done with the last command.

- Be generous with your commit messages (see below). Avoid ```$ git commit -m``` for big commits, and opt for
```$ git commit```, which will drop you into vim or whatever editor you told Git you like.

- Maintainers and pull requests:
  - **Do real code reviews on pull requests!**
  - Ask questions and leverage GitHub's code review features.
  - Run tests before _and_ after merging into master.
  - Do NOT simply click the merge button.  Enter a commit message and/or a comment that explicity states you have read
    the code and find it acceptible.
  - Own quality and deployment.
  - Tag the release when it's ready to go to production. Deployments can pull by tag &ndash; we should do this.


### Remote branches and local branches

- To Do: Explain a long-running branch in the remote vs. local.


### Example workflows

- ```-``` is a time line.
- ```*```  is a commit.
- ```/``` and ```\``` are pulls and pushes that result in a merge commit or a new branch.


#### Basic Topic Branch Flow

    feat-A:  --------------------------/----*----*---*                   /----*----*---*  
    master:  *----------*--------*---*----------*                 *-----*   (ship)
    bug-1:   --------------------------------------\----*--------/


Ross is working on a feature (```feat-A```) and is a very happy programmer. But along comes a bug. Ross is no
longer happy. He's angry and starts to cry, but then realizes he can stash his changes to ```feat-A``` and create
a _new_ branch to fix the bug (```bug-1```). Ross creates a ```bug-1``` branch, fixes the bug, all tests pass, he
merges to ```master```, pushes to his GitHub repo, and makes a pull request. The maintainer pushed the fixes to
production. He then removes the ```bug-1``` branch (```git branch -d bug-1```). He then checks out ```feat-A```,
pulls from ```master``` to get the bug fix. Let's look at this in detail:

{% highlight console %}
$ git status
  # On branch feat-A
  # Changes to be committed:
  # (use "git reset HEAD [file]..." to unstage)
  #
  #  modified:   awesome.py
  #
  # Changes not staged for commit:
  # (use "git add [file]..." to update what will be committed)
  #
  #  modified:   models.py
{% endhighlight %}

At this point, Ross can commit his changes and checkout ```master```, or he can stage his changes, stash them, and
then re-apply his stash once he's finished his fix in ```master```. The commit workflow is simple and well known;
let's look at the more involved ```stash``` workflow:

{% highlight console %}
$ git stash
$ git stash list
  stash@{0}: WIP on feat-A: c8702a5 Coding all the features
$ git checkout master
$ git pull origin master
$ git checkout -b bug-1
{% endhighlight %}

Ross's new ```bug-1``` branch, based on ```master```, is ready for fixin'. Ross creates unit tests to confirm he
can replicate the bug, he fixes the bug, his tests go green. Ross commits his fixes to ```bug-1``` and merges.

{% highlight console %}
$ git add .
$ git commit
  # Good commit message goes here
$ git checkout master
$ git merge bug-1
$ git branch -d bug-1
$ git push :origin/bug-1  #if he  had pushed this branch to his remote
$ git push origin master
{% endhighlight %}

Ross now submits his pull request. He's ready to get back to `feat-A`. If Ross had previously committed all his
work, he'd simply need to re-checkout his `feat-A` branch. However, he decided to ```stash``` instead of
```commit```, so he does this instead:

{% highlight console %}
$ git status
  # On branch master
  nothing to commit (working directory clean)
$ git fetch org_remote
$ git checkout feat-A
$ git pull
$ git stash apply --index
{% endhighlight %}

Ross is happy again.


#### Long Running Branch Flow

    other work:          ------*---------*--------\
    other work:        /---*--*---\----*-\          \
    master:    -*-----*-------------*------*---------* -----------------------------* (ship)
    major-1:     \-------------*-----------------------*--------*--------------* /
    mb1:           \-----*----/                      /   \--*--/               /
    mb2:                          \------*---*---*-/----*-*-------*-\--*----*/


A team has been assembled to build a major release (```major-1```). It's based on ```origin/master``` and is
treated as an integration branch. ```mb1``` and ```mb2``` can be branches worked on by different team members.
When they agree their work can be integrated, they commit to ```major-1```. The maintainer(s) ensure that all
branches and features have been merged and tested, they merge ```mb1``` and ```mb2``` into ```master```, and push
to origin/master.


#### Topic branches vs. Long running branches:

Ask yourself how long it will take and what else is going on with that project. Come up with a quick integration
plan.


----

## [Commit messages](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html):  

From the above link, a model commit message:

    Capitalized, short (50 chars or less) summary

    More detailed explanatory text, if necessary. Wrap it to about 72
    characters or so. In some contexts, the first line is treated as the
    subject of an email and the rest of the text as the body. The blank
    line separating the summary from the body is critical (unless you omit
    the body entirely); tools like rebase can get confused if you run the
    two together.

    Write your commit message in the present tense: "Fix bug" and not "Fixed
    bug." This convention matches up with commit messages generated by
    commands like git merge and git revert.

    Further paragraphs come after blank lines.

    - Bullet points are okay, too

    - Typically a hyphen or asterisk is used for the bullet, preceded by a
      single space, with blank lines in between, but conventions vary here

    - Use a hanging indent

Note that git allows you to create _commit templates_. We may want to consider this.



## Changing the GitHub Enterprise favicon

Currently, GitHub Enterprise does not support modifying the favicon, leading to difficulty distinguishing browser
tabs from our GHE and github.com. To remedy this, you can use a Chrome extension:

1. Fork or clone `https://github.com/marcesher/github-enterprise-change-favicon-color.git`
1. Open the manifest file and change the `matches` to: `"https://github.{{site.data.meta.org_name}}.gov/*"`
1. In Chrome, go to `chrome://extensions`
1. Check the `Developer Mode` checkbox
1. Click `Load Unpacked Extension`
1. Navigate to your `github-enterprise-change-favicon-color` directory and click through to install
1. When the Extensions screen shows your new extension, click the "Options" link and choose your color.
1. Reload a `github.{{site.data.meta.org_name}}.gov` URL and your icon should appear as a different color
1. If the size is wrong (i.e. it shrinks, or it's chopped off), go back to the options page and choose a different
   image size


## Keep tabs with GitHub RSS

If you want to keep up on what others are working on, one fast way is to use GitHub's RSS. Here I'll describe using
the Chrome RSS Live Links extension to do so. Obviously if you have a preferred RSS feed reader, use it.

1. Add the
   [RSS Subscription Extension](https://chrome.google.com/webstore/detail/rss-subscription-extensio/nlbjncdgjeocebhnmkbbbdekmmmcbfjd?hl=en)
   to Chrome.
1. Go to github.com and click on the "News Feed" icon in the URL bar. The resulting URL will be something
   like `https://github.com/yourhandle.private.atom?token=longhash`.
1. On the Feeds screen, click the "Add" button and add that copied URL.
1. Rinse and repeat for any other feeds you want. For example, I have feeds specifically for repos I'm interested
   in, such as all commits on the Handbook. To add a feed for commits, follow this format:
   `https://github.com/organization/reponame/commits/gh-pages.atom`, e.g.:
   `https://github.com/organization/handbook/commits/gh-pages.atom`
1. If you want the firehose, add a feed for the public timeline: `https://github.com/timeline.atom`.
1. To get more items into your personal timeline, watch more people / repos in GitHub.

Once added, those feeds should now show up in Live Links (or your reader). Live Links will notify you whenever new
items appear.


----

## References

- <http://scottchacon.com/2011/08/31/github-flow.html>
- <http://nvie.com/posts/a-successful-git-branching-model/>
- <http://progit.org/book/ch5-1.html>
- <http://zachholman.com/talk/how-github-uses-github-to-build-github>
- <http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html>
- <http://git-scm.com/book/en/Git-Tools-Stashing>
- <http://architects.dzone.com/articles/useful-git-post-checkout-hook>
