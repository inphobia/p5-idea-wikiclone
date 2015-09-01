Contributors are always welcome here, because it's a large project and one man physically can't do everything with a decent speed. 

Basically, we need three types of contributions:

# Testing
1. You may just use the plugin and report bugs or share your ideas of improvements. 
2. You may learn how to write tests for IDEA's plugins and write some tests, which are very necessary for collaborative work. Good point to start is here: http://www.jetbrains.org/intellij/sdk/docs/basics/testing_plugins.html

# Documentation
You could document some plugin features in Wiki or add some Perl documentation into the plugin's internal help system [NYI].

# Coding
If you got some Java experience and want to contribute with coding - you are really welcome. 

But...

Nobody will teach you how to write code for the plugin. We can direct you and give you a hint, but no teaching or re-writing your code. Contributors must be able to learn things. IDEA is very big and complicated platform and it's absolutely no possibility to teach everyone who thinks that he or she want to contribute (but actually might do nothing).

Good places to start:
* http://www.jetbrains.org/intellij/sdk/docs/basics/architectural_overview.html

With high probability, your first PRs (Pull Requests) will be declined and requires re-work, but it's a start. After you'll get some experience - things will become easier and faster. Be patient and diligent. I've spent 5 month of working (not full day) on the plugin to achieve my level of knowledge. And it's not very high. 

Basically: we need all-sufficient contributors, who can work by themselves with a little guidance.

For those who agree with rules above:

* One PR - one feature or bugfix. Every commit message should start with `hurricup/Perl5-IDEA#xxx` (where xxx is an issue number). If you are inactive for a week (or even less for critical bugs) someone else can take your issue.
* If you are a collaborator of the project - make a branch for your bugfix/feature and mention issue in a branch name like `issuexxx` and mention issue in every commit to this branch as a first line: `#xxx`, this will automatically link your commit to the issue (branch name is not working this way).
* To be released, your PR or branch must be up to date with current development branch. Merge last changes.
* No one merges anything into the master or dev branch. All merges being done by release manager (hurricup at the moment)
* Your bugfix must not break tests (when we'll have any). 
* Inactive rule: you must write tests for new features you are implementing. (This rule will come to life after we'll get some tests or will have many contributors. Learn how to do it anyway.)
* If something is wrong with your code from Java or IDEA perspective - we'll tell you what is wrong. No offenses, just pragmatic reasons. Do as it should be done.
* No partial bugfixes. If there is a big bug and it was not decomposed into several ones, you must fix it completely or soundly decompose original bug into several.
* Same for features: no partial implementation. Full solution or decomposition.
* As an original author I have some ideas about how things should be done. So, would be really nice if you'll contact me and we could discuss how specific feature should be implemented. I might have some architectural idea or plan which is not written anywhere.
* You may pick any of the issues to fix from the next version's milestone.

Good luck!