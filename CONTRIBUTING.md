# Contributing
We really appreciate your contributions! We are open source project and we need your help.
We want to keep it as easy as possible to contribute changes that get things working in your environment. There are a few guidelines that we need contributors to follow so that we can have a chance of keeping on top of things.
## Issues and bug reporting
Please report all bugs via Issue tab on GitHub webpage. It will help us to collaborate on issues more promptly. One of our gate-keepers (developers responsible for quality and repository) will review issue and assign one of few labels.

For example: _bug_, _enhancement_, _help wanted_ or _wontfix_.
## How to contribute
You can either file a bug, help fixing bug or propose new feature (or enhancement) and implement it yourself. If you want to contribute please:
* File a bug report in Issues tab of this repo to let us know there are problems with our code
  * Make sure your bug report contains simple description of the problem
  * Information about host computer configuration and OS / VM used 
  * Information about the version of used application. All application shoul;d have at least ```--version``` switch you can use to check version 
  * Copy-past useful console dumps, configuration files' content. Please use [fenced code blocks](https://help.github.com/articles/github-flavored-markdown/#fenced-code-blocks) to encapsulate code snippets etc.
* Create pull request with your changes (bug-fix, new feature or enhancement e.g. in documentation section, tests etc.)
* Give your feedback by posting your comments on existing pull requests and issues

Please remember we are using [GitHub’s pull request](https://help.github.com/articles/using-pull-requests/) to submit proposals for changes, both bug fixes and enhancements.
## Workflow
### Forking and cloning this repository
First [fork]( https://help.github.com/articles/fork-a-repo/) this repository in GutHub, and clone it locally with command:
```
$ git clone <repo-link>
```
Now you can create separate branches in forked repository and prepare pull requests with changes.
### Issues solving simple workflow
1. Issue is being filed (by any user)
2. Proper label is being assigned by gate-keeper to an issue
3. Bug-fixer forked and cloned this repository
4. Optional clarifications are being made using Issue tab comment section
5. Pull request with fix is being created 
6. Pull request is reviewed by others
7. All code review comments are handled accordingly
8. Pull request is accepted by gate-keeper
9. Pull request is merged successfully

### Code review
Code review process is designed to catch both style and domain specific issues. It is also designed to follow and respect definition of done.
Please make sure your code follow source code style you are modifying.
Each pull request should be reviewed by gate keeper before we can merge it to master branch.

## Enhancements vs bugs
Enhancements are:
* New features implementation
* Code refactoring
* Coding rules, coding styles improvements
* Code comments improvement
* Documentation work

Bugs are:
* Issues arose internally or externally by application users
* Internally (within ARM mbed team) created issues from Continuous Integration pipeline and build servers
* Issues detected using automation tools such as compilers, sanitizers, static code analysis tools etc.

## Testing and code coverage
Application should be unit tested (at least minimal set of unit tests should be implemented in ```/test``` directory). We should be able to measure unit test code coverage.
Application offer unit test suite runner:
```
$ cd <package>
$ python setup.py test
```
### Code coverage
To measure application code coverage for unit tests please use [coverage]( https://pypi.python.org/pypi/coverage/3.7.1) tool.
Example of test coverage analysis. This set of commands will locally create code coverage report for all unit tests in <package>.
```
$ cd <package>
$ coverage –x setup.py test
$ coverage –rm
$ coverage html
```
## Keep your GitHub fork updated
I want to fork a GitHub repo ```SOME_REPO/appname``` to ```USER/appname``` and want to keep it updated.

### Tracking changes
```
$ git clone git@github.com:USER/appname.git
$ cd appname
$ git remote add upstream git@github.com:SOME_REPO/appname.git
```

Verify with:
```
$ git remote -v
origin  https://github.com/USER/appname.git (fetch)
origin  https://github.com/USER/appname.git (push)
upstream  https://github.com/USER/appname.git (fetch)
upstream  https://github.com/USER/appname.git (push)
```

### Updating
Each time I want to update, from my local master branch I will do the following:
```
$ git fetch upstream
$ git rebase upstream/master
```
The goal of the rebase is to have a cleaner history if I have local changes or commits on the repo.

## Final notes
1. Please do not change version of package in setup.py file. Person or process responsible for releasing will do this and release new version.
2. Keep your GitHub for updated!
Please make sure you are [rebasing]( https://git-scm.com/book/en/v2/Git-Branching-Rebasing)  your local branch with changes so you are up to date and it is possible to automatically merge your pull request.
3. Please if possible squash your commits before pushing to remote repository.
4. Please as part of your pull request:
5. Update README.md if your changes add new functionality to the module.
6. Add unit tests to ```/test``` directory to cover your changes / new functionality.
