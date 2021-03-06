# :fa-github: Using GitHub

---

GitHub is the primary version control used for all Decred projects. This document provides some basic info on how we handle contributions and some basic info on how to contribute.

---

## General Model

With this process we are trying to make contributing simple while also maintaining a high level of code quality and clean history. Members of the Decred team must follow the same procedures as external contributors.

Our model for contributing in outline form is as follows. If any of this does not make sense, don't worry, it will be explained in more detail in the next sections.

1. Find an issue you want to work on. If there are none describing your issue, open one with what you are going to do.
1. Make changes on a branch.
1. Push these changes to your own forked GitHub repo.
1. When your changes are ready to be reviewed or when you just want input from other devs open a Pull Request (PR) on the main repo from the GitHub web page.
1. Add a comment on the PR that says what issue you are fixing. Put the text Closes # or Fixes # followed by the number of the issue on a single line. This will allow GitHub to automatically link the PR to the issue and close the issue when the PR is closed.
1. You can request a specific reviewer from the GitHub webpage or you can join the [Decred community](https://decred.org/community) and ask somebody to review.
1. ALL changes must be reviewed and receive at least one approval before they can go in. Only team members can give official approval, but comments from other users are encouraged.
1. If there are changes requested, make those changes and commit them to your local branch.
1. Push those changes to the same branch you have been working on. They will show up in the PR that way and the reviewer can then compare to the previous version.
1. Once your changes are approved, they can be merged into master. To keep history clean, we only allow non-fast-forward merges (that means we want a linear history). Most PRs also must be squashed to a single commit (although if there is reason to have it as multiple commits that can be considered on a case by case basis).
1. If your PR is a single commit (or can be squashed by GitHub automatically) and is caught up with master, the reviewer will merge your PR. If your branch was too far behind, you may be asked to rebase your commit. Once that is done and pushed, the reviewer will merge your commit.

---

## Creating a new feature pull request 
- Find or create an issue on the GitHub repo (the original, not your fork) for the feature you want to work on.
- Checkout a new feature branch to house the changes you will be making:

```bash
$ git checkout -b <feature_branch>
```
- Make whatever changes are necessary for the feature and commit them
- Push your feature branch to your fork:

```bash
$ git push <yourname> <feature_branch>
```
- With your browser, navigate to https://github.com/decred/dcrd
- Create a pull request with the GitHub UI. You can request a reviewer on the GitHub web page or you can join the [Decred community](https://decred.org/community) and ask somebody to review.

## Rebasing one of your existing pull requests 

Sometimes you will be requested to rebase and squash the pull request to the latest master branch.

- Make sure the master branch is up-to-date:

```bash
$ git checkout master
$ git pull
```
- Checkout the existing feature branch and rebase it with the interactive flag:

```bash
$ git checkout <feature_branch>
$ git rebase -i master
```
- Follow the directions presented to specify 's' meaning squash for the additional commits (the first commit must remain 'p' or 'pick').
- Write a single commit message in the editor that you have set to cover all the commits included.
- Save and close the editor and git should generate a single commit with the message you specified and all the commits you added. You can check the commit with the command ```git show```.
- Force push the branch to your fork:

```bash
$ git push -f <yourname> <feature_branch>
```

---

## Other Considerations 

Each GitHub repo has a LICENSE. Your new code must be under the same LICENSE as the existing code and assigned copyright to 'The Decred Developers'. In most cases this is the very liberal ISC license but a few repos are different. Check the repo to be sure.

If you have any questions for contributing, feel free to contact the [Decred community](https://decred.org/community).  Decred team members (and probably community members too) will be happy to help.
