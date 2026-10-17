# git-sync-fork

Sync a fork with the repository it was forked from.

## Usage

Where the `upstream` remote does not exist yet, name the repository to fork from, either by its owner and repo on the same host as `origin`, or by its full URL:

```shell
git sync-fork owner/repo
git sync-fork git@host:owner/repo.git
```

It creates the `upstream` remote and syncs with it. Given an owner and repo, the URL takes `origin`'s host and form, so a fork cloned over HTTPS from GitLab gets its upstream over HTTPS from GitLab.

Where `upstream` already exists, no argument is wanted:

```shell
git sync-fork
```

It syncs with whatever `upstream` points at, fast-forwarding the default branch to that repository's and pushing it, with any tags, to `origin`. Where the fork's default branch has commits of its own, it cannot fast-forward, and it stops without pushing.

## Assumptions

- The remote is, or will be, called `upstream`.
- The upstream is on the same host as `origin`, unless a full URL is given.
