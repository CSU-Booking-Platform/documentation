# Standards and practices

List of all standards and practices agreed to by the development team.

_TODO:_ Table of Contents
 
### Commit Messages

#### What

All commit messages must use the following format, based on the[ Conventional Commits Standard 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/), where angle brackets `< >` denote **required** fields, and square brackets `[ ]` denote optional fields. 

```
<type>(#<issue>): <description>

[optional body]

[optional footer(s)] (Ex: Co-Authors)
```

A `body` should always be provided when the `<description>` line is too short for sufficient details about the commit.

#### Why

Using Convetional Commits will allow us to automate some release processes, notably auto-tagging new release versions & automatically generating changelogs for each version.

### Git Workflow

#### `application` Repository

The `application` repository will follow the [Forking Workflow](https://hackmd.io/gB2c1QOTQQGSmYg1LIT0hg), which can be sumarized as follows: 

1. A developer 'forks' an 'official' server-side repository. This creates their own server-side copy.
2. The new server-side copy is cloned to their local system.
3. A Git remote path for the 'official' repository is added to the local clone.
A new local feature branch is created.
The developer makes changes on the new branch.
New commits are created for the changes.
The branch gets pushed to the developer's own server-side copy.
The developer opens a pull request from the new branch to the 'official' repository.
The pull request gets approved for merge and is merged into the original server-side repository
