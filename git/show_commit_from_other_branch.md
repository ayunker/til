# Show Commit From Other Branch

I wanted to view a commit on a different branch without having to
checkout/switch to that branch. It turns out `git show` can do that!

Say I'm on `branch-a`, but I want to see the latest commit I made on
`branch-b`. It's actually really straightforward:

``` shell
$ git show branch-b
```

This follows a lot of the git norms, too! `git show branch-b~` will show the
previous commit on `branch-b` (and `git show branch-b~2` the commit before
that). To view a single file in that commit, `git show
branch-b:path/to/file.rb`!

via https://til.hashrocket.com/posts/bvwwbklmgj-show-commit-from-other-branch
