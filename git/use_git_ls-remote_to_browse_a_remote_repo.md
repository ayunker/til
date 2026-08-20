# Use `git ls-remote` to Browse a Remote Repo

Today I learned about the `git ls-remote` command. I needed a way to see the
names of branches on my remote (origin), and `git ls-remote` saved the day.
`git ls-remote` lists references on a remote repository, including branches,
tags, notes and more.

You can filter to just branches with `-b` (or just tags with `-t`):

```
git ls-remote -b origin
```

You don't have to limit yourself to remotes you've named in your git config
either:

```
git ls-remote https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git
```

And you can filter further with patterns, if you want to find all branches
beginning with `feat`:

```
git ls-remote -b origin feat*
```

You can include more patterns separated by spaces, and will return any
references matching one or more of the patterns. The following will return any
reference starting with `feat`, or matching `main`:

```
git ls-remote -b origin feat* main
```

via https://til.hashrocket.com/posts/bamdynajz8-use-git-ls-remote-to-browse-a-remote-repo
