# git-syncfork

Sync a fork with the repository it was forked from.

## Usage

Where the `upstream` remote does not exist yet, name the repository to fork from:

```shell
git syncfork owner/repo
```

It creates the `upstream` remote and syncs with it.

Where `upstream` already exists, no argument is wanted:

```shell
git syncfork
```

It syncs with whatever `upstream` points at, rebasing onto that repository's default branch.

## Assumptions

- The remote is, or will be, called `upstream`.
- The upstream is hosted on GitHub.
