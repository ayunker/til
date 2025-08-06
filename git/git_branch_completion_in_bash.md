# Git Branch Completion in Bash

You can get git branch completion in bash. Sometimes this is configured out of
the box, but it didn't work for me using homebrew's `git`.

If you are using `git` installed via homebrew, `git-completions.bash` is
located at `/opt/homebrew/etc/bash_completion.d/git-completions.bash` (or
`$(brew --prefix)/etc/bash_completion.d/git-completions.bash` for reliability).
You just need to source it in your `.bashrc` or `.bash_profile` with:

```shell
test -f $(brew --prefix)/etc/bash_completion.d/git-completion.bash && . $_
```

*(This is a cool shorthand syntax to `test` that the file exists, and if it
does, source it. `$_` refers to the last argument in the previous command, in
this case the full path to `git-completion.bash`)*

Now you can auto-complete branch names in `git checkout`, `git rebase`, and
more!

via https://til.hashrocket.com/posts/mycwtzhuaj-git-branch-completion-in-bash
