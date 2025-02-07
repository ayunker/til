# Count Commits within Time Range in Git

`git rev-list` lists commit objects in reverse chronological order, and as such
is an incredibly powerful tool for inspecting your repository.

For example, if you wanted to count all your commits, you can with `git
rev-list --count HEAD`.

You can also drill down to a specific time range with the `--before` and
`--after` options. To get the count of all commits during 2024, you can run:

```
git rev-list --count --after="2024-01-01" --before="2025-01-01" HEAD
```

There are [tons of other options](https://git-scm.com/docs/git-rev-list) you
can use to filter this down too, by author, committer, etc. 

via [Today I Learned](https://til.hashrocket.com/posts/tyr6ahoidx-count-commits-within-time-range-in-git)
