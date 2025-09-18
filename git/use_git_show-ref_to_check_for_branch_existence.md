# Use git show-ref to Check for Branch Existence

Today I learned how to check in git if a branch exists on my local repo. I
bounce between projects that use a `main` or `master` branch, and wanted to
automate away checking which to use.

`git show-ref` lists references in a local git repository. It can show any ref,
be it tag or branch or whatever. But we want to use it for branches:

``` shell
# let's say this repo has `main` branch, not `master`
$ git show-ref --branches master
$ git show-ref --branches main
2067645fb4d7b6ab07215c025dee95b872150db2 refs/heads/main
```

Note it's important to filter by branches, otherwise you can get false
positives from remotes or tags

``` shell
$ git show-ref main
2067645fb4d7b6ab07215c025dee95b872150db2 refs/heads/main
2067645fb4d7b6ab07215c025dee95b872150db2 refs/remotes/origin/main
```

You can use the existence of output from this command in scripts to, for
example, determine which branch to rebase against:

``` shell
#!/bin/sh

main_exists=`git show-ref --branches main`
if [ -n "$main_exists" ]; then
  branch="main"
else
  branch="master"
fi;

git rebase -i $branch
```

via https://til.hashrocket.com/posts/drhiqcuzmo-use-git-show-ref-to-check-for-branch-existence
