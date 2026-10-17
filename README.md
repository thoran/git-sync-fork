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

It syncs with whatever `upstream` points at, fast-forwarding the default branch to that repository's and pushing it, with any tags, to `origin`. Where the fork's default branch has commits of its own, it cannot fast-forward, and it stops without pushing.

## Assumptions

- The remote is, or will be, called `upstream`.
- The upstream is hosted on GitHub.
