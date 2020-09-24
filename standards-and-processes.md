# Standards and practices

[![hackmd-github-sync-badge](https://hackmd.io/gB2c1QOTQQGSmYg1LIT0hg/badge)](https://hackmd.io/gB2c1QOTQQGSmYg1LIT0hg)


List of all standards and practices agreed to by the development team.

* [Commit Messages](#commit-messages)
* [Git Workflow](#git-workflow)
* [Code Coverage & Static Analysis](#code-coverage--sonarcloud-static-analysis)

 
## Commit Messages

### Why

Using Convetional Commits will allow us to automate some release processes, notably auto-tagging new release versions & automatically generating changelogs for each version.

### What

All commit messages must use the following format, based on the[ Conventional Commits Standard 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/), where angle brackets `< >` denote **required** fields, and square brackets `[ ]` denote optional fields. 

```
<type>(#<issue>): <description>

[optional body]

[optional footer(s)] (Ex: Co-Authors)
```

A `body` should always be provided when the `<description>` line is too short for sufficient details about the commit.

#### Controlling the application version with commit naming
_This section is paraphrased from the [git-mkver docs](https://idc101.github.io/git-mkver/usage)_


The next version number will be determined based on the commit messages since the last version was tagged. The commit messages that trigger different version increments are configurable but by default they are based on the Conventional Commit specification as follows:

Commits containing the following will increment the major version:

- `major:` or `major(...):`
- `BREAKING CHANGE`

Commits containing the following will increment the minor version:

- `minor:` or `minor(...):`
- `feat:` or `feat(...):`

Commits containing the following will increment the patch version:

- `patch:` or `patch(...):`
- `fix:` or `fix(...):`

Other conventional commits such as `build`, `chore`, `docs` will not increment the version number, which means that a new release will not be deployed. Do not use these commit prefixes when modifying code or otherwise making changes that need to be released.

All commit messages since the last tagged message are analyzed and the greatest version increment is used. For example if one commit is a minor change and one is a major change then the major version will be incremented.

## Git Workflow

### `application` Repository

The `application` repository will follow the [Forking Workflow](https://hackmd.io/gB2c1QOTQQGSmYg1LIT0hg), which can be sumarized as follows: 

1. A developer 'forks' the 'official' server-side repository. This creates their own server-side copy.
2. The new server-side copy is cloned to their local system.
3. A Git remote path for the 'official' repository is added to the local clone.
4. A new local feature branch is created.
5. The developer makes changes on the new branch.
6. New commits are created for the changes.
7. The branch gets pushed to the developer's own server-side copy.
8. The developer opens a pull request from the new branch to the 'official' repository.
9. The pull reuquest receives **at least 2 approving reviews**
10. The pull request gets approved for merge and is merged into the original server-side repository using the agreed-upon merge strategy

### `documentation` Repository

The `documentation` repository will follow the branching model, to facilitate collaboration on markdown documents using [HackMD.IO](https://hackmd.io). This flow can be sumarized as fllows: 

1. Documents not in HackMD (Skip if the document already exists):
    1. New Document
        1. Developer creates a new blank document
    1. Existing Document in GitHub
        1. Create a blank document & then select pull from GitHub.
        2. Use the UI to select the file from GitHub
1.  In the document, input required changes & commit changes when necessary by creating `versions` via the `Versions & GitHub Sync` menu. Ensure that your version/commit name follows commit naming conventions & **include the names of the persons who collaborated on that version.**
2.  When ready to submit changes back to the repo, select `Push to Github` or `Push` and enter a new branch according to the naming conventions below, and push the changes. 
3. Create a pull request & have it reviewed. If multiple people worked on the changeset, those persons cannot review this PR. 
9. The pull reuquest must receive **at least 2 approving reviews**
5. Merge the PR once approved using the agreed-upon strategy and delete the branch.

Branch naming conventions: `<source>/<document-name>/<task-name>` EX: `HackMD/standards/initial-documentation`

## Code Coverage & SonarCloud Static Analysis

_TODO: Define complete quality gate rules_

Code Coverage Target: `80%`