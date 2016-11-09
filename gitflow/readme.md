# On boarding guide to git flow used by Valor Software

## Overview

Most important thing you should take from this guide is an understanding that `git`, `Github` and `gitflow` is only a `tools` to achieve your/project goals!
  Goal of this guide is to explain `gitflow`, show pros and cons of this approach, and how to prevent possible issues.

If you are new to git or not confident enough in how it works, please, have a look at [Resources](#resources) section.

### Meaning

So the very important thing is to understand main concepts:
- `feature` - is a complete peace of functionality, it could be a new feature, hotfix, doc, test, refactoring, etc...
- `branches` - should serve to separate your work by type of goals you want to achieve or to react on issues in production, like `hotfixes`, with corresponding flows and actions
- `pull request` - is designed to share the knowledge of what you done with team, to take in count code review comments as a source of knowledge sharing,  and last and not least is to check that you did not forgot to add anything :)

### Pros and cons

Gitflow is a way to develop things in a team and has it strong and weak parts.

#### Pros:
* separation of concepts - each branch has clear purpose and flow how to work with it
* confidence - at any given point of time `master` and `release` branches are stable and ready for production
* isolation - you develop independent and isolated feature, so you can focus on problem
* continuous processes - continuous deployment and testing for feature branches, continuous integration for `master` branch
* code review - pull request allows to increase code quality and knowledge rotation in team, and as a consequence reduce "bus factor"

#### Cons:
* "scary merge" - well illustrated problem by Fowler, to avoid it keep semantic changes as separate branches(explained later)
* "afraid of refactoring" - semantic changes(refacroring, renaming) leads to "scary merges", so try to do it when code targeted by refactoring is not changed by any other branches
* dependencies(libraries) update - makes Pull Requests view polluted by library files and in general useless, so keep this updates as a separate branches

##Table of contents
1. [Required reading](#required-readings)
2. [Branches](#branches)
3. [Environments](#environments)
4. [Branch name conventions](#branch-name-conventions)
5. [Pull Requests](#pull-requests)
5. [Merging via Pull Request](#merging-via-pull-requests)
6. [Commits guideline](#commits-guideline)
7. [Initiate repository with main branches](#init-repository-with-main-branches)
8. [Feature branches flow](#feature-branches-flow)
9. [Hotfix branches flow](#hotfix-branches-flow)
10. [Release branches flow](#release-branches-flow)
11. [Resources](#resources)

## Required readings

Take attention to Feature Branching with Pull Requests

1. [Try github](https://try.github.io/levels/1/challenges/1)
2. [Atlassian git tutorial](https://www.atlassian.com/git/tutorials/setting-up-a-repository/ ) (except Migrate to Git from SVN)
3. [Feature branching classic by Martin Fowler](http://martinfowler.com/bliki/FeatureBranch.html)
4. [Closest to ours branching model by Vincent Driessen](http://nvie.com/posts/a-successful-git-branching-model/)
5. [Vincent Driessen git-flow cheatsheet](http://danielkummer.github.io/git-flow-cheatsheet/)
([ru](http://danielkummer.github.io/git-flow-cheatsheet/index.ru_RU.html))

### Supporting readings

1. [Semantic Versioning 2.0.0](http://semver.org/)
2. [Git cheat sheet](https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf)
3. [Github help: user collaborating](https://help.github.com/categories/collaborating/)

## Branches

- `master` - always **stable** and **release ready** branch
- `development` - default branch, contains latest **features** and **fixes**, on which developers should orient
- `feature-*` - branches for feature development and dependencies update
- `realese-*` - branches for release(production) version
- `hotfix-*` - branches for release `fixes`
- `refactor-*` - branches for semantic changes

## Environments

- `master` - production
- `development` - staging
- `release-*` - for history reasons or supporting several versions at production
- `feature-*` - continuous deployment to test environment
- `hotfix-*` - development (local)


## Branch name conventions

Branch names should contain only `lowercase letters`, `numbers` and `hyphens`,
regexp: `/[a-z0-9\-]+/`

**Important** : why not with slashes, like in git flow by Vincent Driessen? -
 because of continuous deployment to corresponding subdomain,
 for example: `feature-ui-auth` will be deployed to `ui-auth.project.com`,
 this is why we should use only symbols allowed for DNS names

## Pull Requests

* For each pull request it should be an issue (except documentation)
* *Note*: issue should answer on: what you should do and why?
* Pull Request must have a description, which should explain what was done and how it affects project
* *Note*: Pull request description should answer to: what you did and how it affects project
* Fixed issue has to be mentioned at the end of Pull Request Name: "`[fixes #123]`" (same for commit names)
* Pull Requests should be small and focused (see "Commits guideline")
* All pull request should satisfy Definition of Done(DoD) and Acceptance Criteria used by project's team
* Commits in pull request should follow to corresponding code conventions

**Important**: keep semantic changes(refactoring, renaming) and library updates as a separate pull requests

## Merging via Pull Requests

This flow will be used almost by any branch flow, so read it carefully

1. [Create](https://help.github.com/articles/creating-a-pull-request/) `PR` from `current` branch to `target` branch

  * *Note*: `current` and `target` branches depends on what you are doing, see branch flows below
  * *Note*: except `hotfix` branches, `target` branch is `development`
  * assign it to yourself
  * add corresponding labels

2. When you done with changes in branch:
  * *Optional*: you can reset your commits and arrange them in meaningful commits with interactive `git rebase -i`

  * Rebase your branch on top of `target` branch, usually `development`

    ```bash
    # checkout current-branch
    git checkout current-branch
    # fetch latest changes
    git fetch origin --prune
    # rebase on top of development branch
    git rebase origin/development
    ```

  * In case of merge conflicts - solve them :)
    * While rebasing

      ```bash
      # run merge tool
      git mergetool
      # clean up after merge
      find -name "*.orig" -delete
      # continue rebasing
      git rebase --continue
      # repeat this steps until all merging conflicts solved
      ```

    * Abort rebasing and use merge

      ```bash
      # abort rebase
      git rebase --abort
      # merge latest development into your branch
      git merge origin/development
      ```

  * Link to `PR` should be sent to your team chat with code review request (to make things move faster)

  *Sample*: "Please review my Pull Request: https://github.com/org/project/pull/1"

3. If there are some code review notes which should be applied, apply them and repeat from step `2`

4. When Pull Request was approved by at least 2 team members

  * *Note*: you can use :+1: as an approvement
  * *Note*: reviewer, who gave second approvement, can send a note to `PR` author, to make things go faster
  * When pull request got 2 approvements it should be merged by **code author**

<!--5. Feature branch should be deleted while merging `PR`-->

## Commits guideline
<!-- Copyright (c) 2013 Nicholas C. Zakas. All rights reserved. -->
**Important**:
* commits without task id (link for asana) are not allowed (except docs and libs version udpates)
* keep application version bump as a separate commits

Make the changes to the code and tests and then commit to your branch. Be sure to follow the commit message conventions.

Commit message summaries must follow this basic format:

```
Tag: Message [Action #1234]
```

The `Tag` is one of the following:
* `Fix` - for a bug fix.
* `Update` - for a backwards-compatible enhancement.
* `Breaking` - for a backwards-incompatible enhancement.
* `Docs` - changes to documentation only.
* `Build` - changes to build process only.
* `New` - implemented a new feature.
* `Upgrade` - for a dependency upgrade.

`Message` is short description of what have been done
`Action` - depends on used task tracking, but in general case:
* `refs` - link commit to task
* `fixes` - closes task, moving it to testing state
**Important**: use `fixes` only in Pull Request name

The message summary should be a one-sentence description of the change. The issue number should be mentioned at the end. If the commit doesn't completely fix the issue, then use `[refs #1234]` instead of `[fixes #1234]`.

Here are some good commit message summary examples:

```
Build: Update Travis to only test Node 0.10 [refs #734]
Fix: Semi rule incorrectly flagging extra semicolon [fixes #840]
Upgrade: Esprima to 1.2, switch to using Esprima comment attachment [fixes #730]
```

The commit message format is important because these messages are used to create a changelog for each release. The tag and issue number help to create more consistent and useful changelogs.

## Init repository with main branches

`master` branch should be in place for any repository by default.

Create `development` branch and make it as default for `GitHub`.

```bash
git checkout -b development origin/master
# switched to a new branch 'development'
git push origin development
```

At GitHub:
  * Open repository `Settings` -> `Options` -> `Settings` section
  * Set `developement` as default branch (it will ease Pull Request creation in future)

## Feature branches flow

  * `feature` branch should be started from `development` and merged back.
  * should not change version (version will be changed while creating release)

1. Create `feature` branch from `development` head

  ```bash
  # update your local repository with latest changes
  git fetch origin --prune
  # create feature branch from development head
  git checkout -b feature-you-will-do origin/development
  ```

2. Create a Pull Request when `feature` implementation done (see [DoD]() *...comming*)

3. Go through Pull Request review process

4. Cleanup local repository

  ```bash
  # origin/feature will be removed by Github
  git fetch origin --prune
  git branch -d feature-you-will-do
  ```

5. If automatic `PR` merging not available, merge `development` to `feature` branch locally and start from step `3`

  ```bash
  git fetch origin --prune
  git pull origin
  git checkout feature-you-will-do
  git merge development
  # if automatic merging of Pull Request is not available
  # it means that there are merge conflicts and we need to solve them locally
  git mergetool
  # remove trash after merge
  find -name "*.orig" -delete
  # merge commit will be auto-generated, no need for commit message
  git commit
  git push origin feature-you-will-do
  ```

6. Cleanup branches

  ```bash
  git fetch origin --prune
  git checkout development
  git pull origin development
  # delete remote branch
  git push origin :feature-you-will-do
  # delete local branch
  git branch -d feature-you-will-do
  ```

## Hotfix branches flow

* should be used only to fix bugs at production
* `hotfix` branch should be started from `master` and must be merged back to `master` and `development`
* `hotfix` branch may be started from `release` branch and than must be merged back to `release`, `master` and `development` branches
* **Important**: `hotfix` branch name contains full version number, sample: `hotfix-1.2.2` and **not** `release-1.2`
* **Important**: each `hotfix` should increase [PATCH](http://semver.org/) version of project

1. Create `hotfix` branch from `master` (or `release`)

  ```bash
  git fetch origin --prune
  # create hot fix brach
  git checkout -b hotfix-0.1.2 origin/master
  ```

2. Bump application version and make a separate commit for it

  ```bash
  # bump application PATCH version
  ./bumpApplicationVersion.sh "0.1.2"
  git commit -am "Bumped version number to 0.1.2"
  ```

3. Fix an issue, commit your changes and push to repository

  ```bash
  git commit -am "Fix: terrible production bug fixed [refs #123]"
  git push origin hotfix-0.1.2
  ```

4. Go through merging process via Pull Request to `master`
  * *Note*: in case of emergency, approvement and code review may be done later
  * *Note*: if `hotfix` was started from `release` branch it must be merged to `release` branch it was started

5. When pull request closed, merge `hotfix` branch to `development` and `master` (if `hotfix` was started from `release` branch)

6. Cleanup branches

  ```bash
  git fetch origin --prune
  git checkout development
  git pull origin development
  # delete remote branch
  git push origin :hotfix-0.1.2
  # delete local branch
  git branch -d hotfix-0.1.2
  ```

## Release branches flow

* should be used when all features required by next release already in `development` branch
* any `realese` branch should start from `development` branch
* starting `release` branch unblocks `development` for new features development
* merging `release` branch to `master` automatically means new release to production, and could be used as an event for continuous integration
* **Important**: all features planed for next release **should not** be merged in `development` until current `release` branch created
* **Important**: `release` branch name contains only MAJOR and MINOR version number, sample: `release-1.2` and **not** `release-1.2.3`. PATCH version of project has to be increased only by `hotfix` branches

1. Create `release` branch from `development` head

  ```bash
  # update local version of development to latest state
  git checkout origin development
  git pull origin development

  # create new release branch
  git checkout -b release-1.2 development

  # bump project version
  ./bump-project-version.sh 1.2

  # keep version bump commit as separate one
  git commit -am "Bumped version number to 1.2"

  # push your changes to Github
  git push origin release-1.2
  ```

2. Deploy to staging, test on real data, test on applience to Definirion of Done, Acceptance Criteria, Code conventions, etc...

3. When `release` fully tested and ready for production, start Pull Request to `master` brach
  * *Note*: if you have Continuous Integration, closing Pull Request will start deploy to production, so be ready for fun and choose proper time (not friday evening!)

4. Finish `release`
  * *Note*: could be merge conflicts

  ```bash
  # get latest master state
  git checkout master
  git pull origin master
  # add release tag to merge commit
  git tag -a 1.2
  # push tag to repositori
  git push origin master --tags

  # merge release back to development
  git checkout development
  git pull origin development
  git merge master
  git push origin development --tags
  ```

5. Delete `release` branch and use tags

## Use cases
### Remove all local branches
```bash
  git branch -l | egrep -v "^\*|master|development" | xargs -n 1 git branch -D
```

## Resources

1. [A Visual Git Reference](http://marklodato.github.io/visual-git-guide/index-en.html)