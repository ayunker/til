# Ignore Specific Commits in Git Blame

We've all been there before - you go to run `git blame` and find the commit
that caused the bug...and it's a massive formatting commit, and the bug lies
deeper. Wouldn't it be great if you could ignore those types of commits?

Turns out there are a couple of options to ignore commits. This isn't fully
automated, you will need to know the commits that you want to ignore ahead of
time.

If you need to do this on an ad hoc basis, you can use `--ignore-rev` and pass
in the SHA of the commit

``` sh
git blame --ignore-rev <rev>
```

That's going to get tedious if you want to ignore it every time you run `git
blame`. You can also add the revisions to a file (conventionally named
`.git-blame-ignore-revs`), one revision SHA per line. Then you can tell `git
blame` to use that file either as an argument or as a config:

``` sh
# as an argument 
git blame --ignore-revs-file <file>

# or add it to config
git config blame.ignoreRevsFile <file>
```

[Docs](https://git-scm.com/docs/git-blame)

via https://til.hashrocket.com/posts/leeyztrorn-ignore-specific-commits-in-git-blame
